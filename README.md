# awesome-Lilypad - examples, use cases, and more!

![lilypad](https://github.com/user-attachments/assets/251033c7-189c-4bb4-97d9-876343dec587)

[Lilypad](https://lilypad.tech) is developing a serverless, distributed compute network that enables internet-scale data processing, AI, ML & other arbitrary computation from blockchains, while unleashing idle processing power & unlocking a new marketplace for compute.

## General

- [FAQs](https://docs.lilypad.tech/lilypad/faqs)
- [Lilypad docs](https://docs.lilypad.tech/lilypad)
- [Quick Start](https://docs.lilypad.tech/lilypad/lilypad-milky-way-testnet/quick-start) - Lilypad "Hello World"
- [Module Boilerplate](https://github.com/Lilypad-Tech/lilypad-module-boilerplate) - A boilerplate for getting started with building a Lilypad module
- [Lilypad Discord](https://lilypad.team/discord) - Come ask questions!

## Resource Providers

- [Hardware Requirements](https://docs.lilypad.tech/lilypad/hardware-providers/hardware-requirements) - Hardware requirements for running a Lilypad node
- [Running a Lilypad node](https://docs.lilypad.tech/lilypad/hardware-providers/run-a-node) - Instructions on how to run a Lilypad node
- [Running a Lilypad node video](https://www.youtube.com/watch?v=YmOtqOIBQ0k) - A short video walkthrough on how to run a Lilypad node
- [Lilypad Discord](https://lilypad.team/discord) - Join the Discord and ask questions in the "General" or "i-need-help" channels
- [WindowsResourceProvider app](https://github.com/Lilypad-Tech/WindowsResourceProvider) - Open-source/experimental. PR's and issues welcome
- [WSL Resource Provider setup](https://github.com/rhochmayr/lp-wsl-native-rp) - Open-source/experimental. Feedback welcome!

## Developers

- [Lilypad Modules Intro](https://docs.lilypad.tech/lilypad/lilypad-modules/modules-intro)
- [Local JS CLI Wrapper API](https://docs.lilypad.tech/lilypad/developer-resources/js-cli-wrapper-local) - Run jobs on the Lilypad network with a locally hosted API.
- [Smart contract jobs](https://github.com/Lilypad-Tech/lilypad/blob/main/docs/smart-contract-jobs.md) - Trigger jobs on the Lilypad network from a smart contract
- [Run Lilypad on a client](https://blog.lilypadnetwork.org/setting-up-your-lilypad-front-end) - Integrate Lilypad into a frontend to run a SDXL module to generate images

## Modules

A list of modules that can run on the Lilypad Network, provided by the Lilypad team and community.

> The [Lilypad CLI](https://docs.lilypad.tech/lilypad/lilypad-testnet/install-run-requirements) is required to run a module.

### API Compatible Modules

Modules supported by the Lilypad API are also compatible with our CLI.

| Module                                                                    | Model               | Repo                                                                                      |
| ------------------------------------------------------------------------- | ------------------- | ----------------------------------------------------------------------------------------- |
| [DeepSeek R1 7B](https://github.com/DevlinRocha/lilypad-deepseek-r1-7b)   | `"deepseek-r1:7b"`  | `github.com/DevlinRocha/lilypad-deepseek-r1-7b:3334fe0d8329c516898a67be0ef656c7492a9d79`  |
| [Mistral 7B](https://github.com/DevlinRocha/lilypad-mistral-7b)           | `"mistral:7b"`      | `github.com/DevlinRocha/lilypad-mistral-7b:a551c957f4e7e36e7f63c085f3cd3fe742b6e9dc`      |
| [Phi-4 14B](https://github.com/DevlinRocha/lilypad-phi4-14b)              | `"phi4:14b"`        | `github.com/DevlinRocha/lilypad-phi4-14b:adf49d85cf9825a2386d91eccd910dbfe44e2499`        |
| [Llava 7B](https://github.com/DevlinRocha/lilypad-llava-7b)               | `"llava:7b"`        | `github.com/DevlinRocha/lilypad-llava-7b:2ee3bf637ce19eff52aa2bd79ad449d70e092119`        |
| [DeepScaleR 1.5B](https://github.com/DevlinRocha/lilypad-deepscaler-1.5b) | `"deepscaler:1.5b"` | `github.com/DevlinRocha/lilypad-deepscaler-1.5b:226a58eba382de7df176ea51eb2b8317973be49c` |
| [OpenThinker 7B](https://github.com/DevlinRocha/lilypad-openthinker-7b)   | `"openthinker:7b"`  | `github.com/DevlinRocha/lilypad-openthinker-7b:0504f41d60f7cff74d3568557a998bd1b7d6205f`  |

<details>
  <summary>Use With Our API</summary>

1. Replace `YOUR_API_KEY` with your API key from the [Anura website](https://anura.lilypad.tech/).
2. Replace the `model` field value of your request object with the "Model" column from our modules table below.

```sh
curl -X POST "https://anura-testnet.lilypad.tech/api/v1/chat/completions" \
-H "Content-Type: application/json" \
-H "Accept: text/event-stream" \
-H "Authorization: Bearer YOUR_API_KEY" \
-d '{
  "model": "MODEL_NAME:MODEL_VERSION",
  "messages": [{
    "role": "system",
    "content": "you are a helpful AI assistant"
  },
  {
    "role": "user",
    "content": "what order do frogs belong to?"
  }],
  "temperature": 0.6
}'
```

</details>

<details>
  <summary>Use With Our CLI</summary>

1. Replace `GITHUB_USERNAME/MODULE_REPO:TAG` with the "Repo" column from our modules table below.
2. Replace the `model` field value of your request object with the "Model" column from our modules table below.

> When using our CLI, make sure that you Base64 encode your request.

```sh
lilypad run github.com/GITHUB_USERNAME/MODULE_REPO:TAG \
-i request="$(echo -n '{
  "model": "MODEL_NAME:MODEL_VERSION",
  "messages": [{
    "role": "system",
    "content": "you are a helpful AI assistant"
  },
  {
  "role": "user",
  "content": "what order do frogs belong to?"
  }],
  "temperature": 0.6
}' | base64 -w 0)"
```

</details>

#### Request Fields

| Field      | Description                                                                 | Type     |
| ---------- | --------------------------------------------------------------------------- | -------- |
| `model`    | Model ID used to generate the response (e.g. deepseek-r1:7b). **Required**. | `string` |
| `messages` | A list of messages comprising the conversation so far. **Required**.        | `array`  |

<details>
<summary>Optional Fields</summary>

##### Optional Fields and Default Values

Our API modules support the following optional fields for the request.

- [Create chat completion](https://platform.openai.com/docs/api-reference/chat/create)

| Field               | Description                                                                                                                                                                                                                                                                                                 | Default |
| ------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------- |
| `frequency_penalty` | Number between `-2.0` and `2.0`. Positive values penalize new tokens based on their existing frequency in the text so far, decreasing the model's likelihood to repeat the same line verbatim.                                                                                                              | `0`     |
| `max_tokens`        | The maximum number of tokens that can be generated in the chat completion.                                                                                                                                                                                                                                  |         |
| `presence_penalty`  | Number between `-2.0` and `2.0`. Positive values penalize new tokens based on whether they appear in the text so far, increasing the model's likelihood to talk about new topics.                                                                                                                           | `0`     |
| `response_format`   | An object specifying the format that the model must output. [Learn more](https://platform.openai.com/docs/api-reference/chat/create#chat-create-response_format).                                                                                                                                           |         |
| `seed`              | Makes a best effort to sample deterministically, such that repeated requests with the same `seed` and parameters should return the same result. Determinism is not guaranteed, and you should refer to the `system_fingerprint` response parameter to monitor changes in the backend.                       |         |
| `stop`              | Up to 4 sequences where the API will stop generating further tokens. The returned text will not contain the stop sequence.                                                                                                                                                                                  | `null`  |
| `stream`            | If set to true, the model response data will be streamed to the client as it is generated using server-sent events.                                                                                                                                                                                         | `false` |
| `stream_options`    | Options for streaming response. Only set this when you set `stream: true`. [Learn more](https://platform.openai.com/docs/api-reference/chat/create#chat-create-stream_options).                                                                                                                             | `null`  |
| `temperature`       | What sampling temperature to use, between `0` and `2`. Higher values like `0.8` will make the output more random, while lower values like `0.2` will make it more focused and deterministic. We recommend altering this or `top_p` but not both.                                                            | `1`     |
| `top_p`             | An alternative to sampling with `temperature`, called nucleus sampling, where the model considers the results of the tokens with `top_p` probability mass. So `0.1` means only the tokens comprising the top 10% probability mass are considered. We recommend altering this or `temperature` but not both. | `1`     |
| `tools`             | A list of tools the model may call. Currently, only functions are supported as a tool. Use this to provide a list of functions the model may generate JSON inputs for. A max of 128 functions are supported. [Learn more](https://platform.openai.com/docs/api-reference/chat/create#chat-create-tools).    |         |

</details>

### Lilypad Team Modules

Modules created by the Lilypad team are listed in the [Lilypad docs](https://docs.lilypad.tech/lilypad/lilypad-modules/modules-intro) under "Lilypad Modules".

| Module                                                                         | Run Command                                                           | Arguments       |
| ------------------------------------------------------------------------------ | --------------------------------------------------------------------- | --------------- |
| [lilysay](https://github.com/Lilypad-Tech/lilypad-module-lilysay)              | `lilypad run lilysay:0.5.2`                                           | `-i Message=""` |
| [cowsay](https://github.com/lilypad-tech/lilypad-module-cowsay)                | `lilypad run cowsay:v0.0.4`                                           | `-i Message=""` |
| [Stable Diffusion Turbo Pipeline](https://github.com/noryev/module-sdxl-ipfs)  | `lilypad run github.com/noryev/module-sdxl-ipfs:main`                 | `-i prompt=""`  |
| [DeepSeek R1 1.5B](https://github.com/narbs91/lilypad-ollama-deepseek-r1-1-5b) | `lilypad run github.com/narbs91/lilypad-ollama-deepseek-r1-1-5b:main` | `-i Prompt=""`  |
| [Llama 2](https://github.com/noryev/module-llama2)                             | `lilypad run github.com/noryev/module-llama2:main`                    | `-i PROMPT=""`  |

### Lilypad Community Modules

Modules from the community have not been tested by the Lilypad team. Run these modules at your own risk.

| Module                                                                               | Run Command                                                      | Arguments      |
| ------------------------------------------------------------------------------------ | ---------------------------------------------------------------- | -------------- |
| [DeepSeek R1 7B](https://github.com/rhochmayr/ollama-deepseek-r1-7b/tree/1.0.0)      | `lilypad run github.com/rhochmayr/ollama-deepseek-r1-7b:1.0.0`   | `-i Prompt=""` |
| [Llama 3.2 3B](https://github.com/rhochmayr/ollama-llama3.2-3b/tree/1.0.0)           | `lilypad run github.com/rhochmayr/ollama-llama3.2-3b:1.0.0`      | `-i PROMPT=""` |
| [Qwen 2.5 Coder 7B](https://github.com/rhochmayr/ollama-qwen2.5-coder-7b/tree/1.0.0) | `lilypad run github.com/rhochmayr/ollama-qwen2.5-coder-7b:1.0.0` | `-i Prompt=""` |

## Use Cases

- [Lilypad Node Monitoring](https://github.com/rhochmayr/lilypad-rp-monitoring) - Node Monitoring with Uptime Kuma and Telegram Notifications
- [Waterlily.ai](https://github.com/Lilypad-Tech/Waterlily) - An ethical generative AI-Art dApp leveraging FVM smart contracts and decentralized edge compute platform Bacalhau
- [Defikicks](https://github.com/md0x/defikicks) - A decentralized, community-governed Data DAO on Filecoin that democratizes DeFi data aggregation and TVL calculations
- [Lilypad Kamu](https://github.com/polus-arcticus/lilypad-module-kamu/blob/main/lilypad_module.json.tmpl) - Custom Lilypad module for SQL streaming through kamu.dev
- [Project C](https://github.com/0xgoldenlion/project-C) - Personalized course generation using Lilypad
- [AI Capwyn](https://github.com/jeytuan/OpenDataHackathon_Lilypad) - ML tooling for security audits
- [Lilypad Hub](https://github.com/oBLAZERo2001/lilypad-hub) - Hub for Lilypad modules
- [Obsidian Lilypad](https://github.com/polus-arcticus/obsidian-lilypad) - Pull Desci nodes, stream together external apis and more
- [Decenter AI](https://github.com/orgs/DeCenter-AI/repositories) - PaaS infrastructure for training cost effective AI models through decentralized parallel training methods
- [Lilylatte](https://github.com/Caruso33/LilyLatte_OpenDataHack) - DataDAO focused on web3 market research
- [TinyHops](https://github.com/zcstarr/tiny-hops) - A workflow specification and runner for executing Lilypad enabled jobs in sequence
- [Saturn Observatory](https://github.com/cronian-tech/saturn-observatory) - Monthly analytical reports using historical data from the Filecoin Saturn network
- [Lilypad JavaScript Wrapper](https://github.com/only4sim/lilypad-javascript-wrapper) - JavaScript wrapper for interacting with the Lilypad CLI using Node.js
- [Lilywrite](https://github.com/Khwahish29/lilywrite) - AI generated poems using Lilypad
- [Rejuvenate AI](https://github.com/orgs/open-data-hack/repositories) - Community blockchain based project built to promote healthy living and achieve healthy locations
- [GreenBadge](https://github.com/priyanshur66/greenbadge) - Onchain funding platform
- [Gadus CLI](https://github.com/The-Extra-Project/Gadius-CLI) - CLI package for running 3D surface reconstruction
- [Deehr Market](https://github.com/Cabal-Labs/deehr-market-client) - Provides patients with ownership of their electronic health records
- [CréditDécentrale](https://github.com/solity-research/ETHGlobalParis2023) - Decentralized credit score system using zkSNARKs, Decentralized Computation and Storage
- [Cypher Deposit](https://github.com/Alice-s-Deposit) - Secure crypto withdrawals via anonymous transfers
- [LLMBench](https://github.com/codethazine/llmbench) - Verifiable on-chain Large Language Models drift benchmarking
- [Uncensored GPT-5](https://ethglobal.com/showcase/uncensored-gpt-5-blockchain-15did) - Uncensored 100% decentralized GPT AI chat running on the blockchain
- [ZK Microphone](https://github.com/Miyamura80/ZKMicrophone) - Trusted audio using zk-SNARKS
- [CarpAI](https://devpost.com/software/carpai-fmecgh) - Fastchat LLM inference module for Lilypad v1
- [Brian](https://github.com/brian-knows/brian-fine-tuning) - Decentralized web3 AI assistant for executing onchain transactions via prompt
- [Avasoul.ai](https://github.com/mr-spaghetti-code/lilypad/tree/main) - Private-Model Generation and Service Platform
- [EasyCraft AI](https://github.com/BigTava/easycraft) - AI and blockchain based supply chain management implementation matching factory capacity with customer orders for economic efficiency
- [Decentralized Yield Data Collector](https://github.com/aaytuncc/HackFS-2023) - Decentralized yield data aggregator
- [Pensieve](https://github.com/ahsueh1996/Pensieve-) - Decentralized file storage
- [Daggle](https://github.com/leostelon/daggle) - A swiss knife for Bacalhau, everything you need in an easily accessible dashboard
- [InferAI](https://github.com/Shubhamai/hackfs2023) - Single click deployment for ML models on a decentralized compute and storage powered by Filecoin Virtual Machine, Bacalhau & Libp2p
- [TENTAI](https://github.com/debuggingfuture/tentai) - SDK for AI models running on decentralized computing
- [Rock Paper Ninja](https://github.com/tonynacumoto/rock-paper-ninja) - A web3 take on the classic game of Rock Paper Scissors
- [Dogtoken ai erc404](https://github.com/lucasespinosa28/dogtoken) - ERC404 token with custom Lilypad stable diffusion to generate unique images for holders
- [Filecoin ML Engine](https://github.com/Prajjawalk/filecoin-ML-engine) - Onchain ML engine to create dApp ML agents on top of Filecoin
- [NexTown](https://github.com/DogukanGun/hackfs24-ai-marketplace) - A decentralized AI computation and storage platform allowing users to run AI models via LilyPad
- [CipherCraft](https://github.com/Shubham-Rasal/CipherCraft) - A decentralized hub for federated model training on access controlled private datasets
