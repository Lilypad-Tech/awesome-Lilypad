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

### Lilypad Team Modules

Modules created by the Lilypad team are listed in the [Lilypad docs](https://docs.lilypad.tech/lilypad/lilypad-modules/modules-intro) under "Lilypad Modules".

| Module | Run Command | Arguments |
| -------- | -------- | -------- |
| [lilysay](https://github.com/Lilypad-Tech/lilypad-module-lilysay) | `lilypad run lilysay:0.5.2` | `-i Message=""` |
| [cowsay](https://github.com/lilypad-tech/lilypad-module-cowsay) | `lilypad run cowsay:v0.0.4` | `-i Message=""` |
| [Stable Diffusion Turbo Pipeline](https://github.com/noryev/module-sdxl-ipfs) | `lilypad run github.com/noryev/module-sdxl-ipfs:main` | `-i prompt=""` |
| [DeepSeek R1 1.5B](https://github.com/narbs91/lilypad-ollama-deepseek-r1-1-5b) | `lilypad run github.com/narbs91/lilypad-ollama-deepseek-r1-1-5b:main` | `-i Prompt=""` |
| [Phi 4 14B](https://github.com/DevlinRocha/lilypad-phi4-14b) | `lilypad run github.com/DevlinRocha/lilypad-phi4-14b:v0.0.0` | `-i prompt=""` `-i temperature="0.7"` `-i max_tokens="2048"` |
| [Llama 2](https://github.com/noryev/module-llama2) | `lilypad run github.com/noryev/module-llama2:main` | `-i PROMPT=""` |

### Lilypad Community Modules

Modules from the community have not been tested by the Lilypad team. Run these modules at your own risk.

| Module | Run Command | Arguments |
| -------- | -------- | -------- |
| [DeepSeek R1 7B](https://github.com/rhochmayr/ollama-deepseek-r1-7b/tree/1.0.0) | `lilypad run github.com/rhochmayr/ollama-deepseek-r1-7b:1.0.0` | `-i Prompt=""` |`
| [Llama 3.2 3B](https://github.com/rhochmayr/ollama-llama3.2-3b/tree/1.0.0) | `lilypad run github.com/rhochmayr/ollama-llama3.2-3b:1.0.0` | `-i PROMPT=""` |
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

