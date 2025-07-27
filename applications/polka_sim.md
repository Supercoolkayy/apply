# Polka Sim: Interactive Substrate Simulator

## Project Overview

**Tagline:**  
*A GUI-based Substrate blockchain simulator for developers to explore, test, and learn without setup.*

**Brief description:**  
Polka Sim is a lightweight, graphical blockchain simulator that allows developers to quickly explore and interact with local Substrate-based chains without complicated setup. With Polka Sim, users can launch an instant blockchain environment directly from a visual interface, without any complex setup, Rust code, or using a terminal.

For example, a developer could visually test token transfers between predefined accounts, explore how transactions appear in newly created blocks, or select runtime features (pallets) at startup (genesis) to observe their immediate effects. Under the hood, the desktop app packages a local Substrate dev node to produce blocks and uses the polkadot-js API; a Smoldot light client may be used where appropriate to connect and verify headers. (Chopsticks/live-chain forks can follow in a later phase.)

The tool will be delivered as both a desktop application (built with Tauri or Electron) and a browser-based web version, accessible anywhere. The web app connects to a local desktop node or to a temporary hosted sandbox for workshops.

**Relation to Polkadot (SDK) / Kusama:**  
Polka Sim integrates directly with the Polkadot SDK (Substrate framework) using the polkadot-js API for JSON-RPC communication. The desktop app packages a local Substrate dev node for block production; Smoldot may optionally be used as a light client for header verification.

**Team Motivation:**  
As Polkadot Blockchain Academy (PBA) alumni and through feedback from the WebZero Hackathon (Consensus Toronto), we identified significant barriers in Polkadot/Substrate developer onboarding, including complex node compilation, Rust macros, CLI tooling, and manual explorer setups. Polka Sim directly addresses these challenges, aligning perfectly with our mission at Dapps over Apps: creating accessible, intuitive blockchain tooling to accelerate developer adoption.

---

### Project Details
<img width="1124" height="677" alt="image" src="https://github.com/user-attachments/assets/8a9554bd-732d-46b6-bb82-6cc0f636171b" />

**Technology Stack:**  
- **Frontend:** React or Vue  
- **Desktop:** Tauri (~10–25 MB) or Electron (~100–180 MB)  
- **Blockchain Execution:** Packaged local Substrate dev node (desktop app); optional Smoldot for header verification  
- **JSON-RPC Layer:** polkadot-js API  
- **Data Storage:** IndexedDB (web), app data folder (desktop)

**Core Components & Architecture:**  
- Unified Desktop/Web UI (Explorer, Wallets & Tx-builder, Runtime Configurator, Snapshot Manager)  
- JSON-RPC bridge (polkadot-js API: `author_submitExtrinsic`, `state_getStorage`)  
- Execution: Desktop-packaged Substrate dev node producing blocks; Smoldot optionally verifies headers  
- Feature Panels: Dev wallets, visual transaction builder, runtime config at genesis, snapshot export/import, real-time block explorer

**Prior Research:**  
- Validated through Polkadot Blockchain Academy and WebZero Hackathon (Consensus Toronto) experiences.  
- Technical feasibility confirmed via polkadot-js API and local Substrate node integration.  
- UI/UX mockups and architecture diagrams completed.

**Mockups/UI Designs:**  
- Architecture and UX flow diagrams available (to be included in repo/docs).

**Data Models & APIs:**  
- JSON-RPC calls via polkadot-js API: `author_submitExtrinsic`, `state_getStorage`, `chain_getBlock`  
- Dev accounts via `@polkadot/keyring`

---

### Ecosystem Fit

**Fit into the Polkadot/Kusama Ecosystem:**  
Polka Sim is a GUI-first Substrate sandbox designed explicitly to facilitate visual learning, developer onboarding, and rapid prototyping. It complements existing CLI/testing tools by focusing on intuitive usability.

**Target Audience:**  
- New blockchain developers (especially Web2 devs transitioning to Web3)  
- Educators and workshop/hackathon facilitators  
- Parachain/dapp developers needing rapid prototyping and reproducible demos

**Needs Met:**  
- Eliminates complex Rust/CLI setup barriers  
- Provides immediate visual feedback loops  
- Enables reproducible blockchain states for collaborative testing and education

**Identification of Needs (evidence):**  
- Direct feedback from WebZero Hackathon (Consensus Toronto)  
- Personal experience as Polkadot Blockchain Academy alumni
- Acknowlwdgement from devrel teams in Polkadot. 

**Similar Projects in Polkadot Ecosystem:**  
- **Chopsticks**: CLI-based state-forking, advanced but non-visual  
- **sc-simnode**: Rust-based integration testing library, no GUI

Polka Sim is distinct in providing a GUI-based, intuitive onboarding tool targeting newcomers and educators rather than advanced code-based testing scenarios.

**Similar Projects Elsewhere:**  
- Ethereum: Foundry Anvil  
- Solana: Solana Playground

---

## Team

- **Team Name:** Dapps over Apps  
- **Contact Name:** Abdulkareem Oyeneye  
- **Contact Email:** team@dappsoverapps.com  
- **Website:** www.dappsoverapps.com

### Team Members & LinkedIn Profiles:
- **Bolaji Ahmad (Full Stack Engineer, PBA Alumni)**  
  https://linkedin.com/in/bolajahmad
- **Abdulkareem Oyeneye (Project Lead)**  
  https://linkedin.com/in/abdulkareem-oyeneye
- **Emmanuel Charles (Blockchain Developer & QA Engineer)**  
  https://linkedin.com/in/emmanuel-charles-0b0023250
- **Kushimo Bashir (Blockchain Engineer)**
 https://www.linkedin.com/in/kushimo-bashir/
- **Gospel Ifeadi (Smart Contract Engineer)**  
  https://x.com/gospel70800

### Team Code Repos of Past Works:
- https://github.com/RegionX-Labs/Coretime-Notifier  
- https://github.com/r0gue-io/pop-cli  
- https://github.com/dappforce/subsocial-parachain  
- https://github.com/dappforce/grillchat  
- https://github.com/paritytech/polkadot-sdk

### Team's Relevant Experience:  
Dapps over Apps specializes in Web3 developer tooling and education. Our Polkadot-specific experience includes significant contributions to RegionX Labs, Pop CLI, Subsocial, Grillchat, and the Polkadot SDK. Our practical experience as Polkadot Blockchain Academy alumni and participation in multiple hackathons informs our focus on accessible onboarding and effective developer experiences.

---

## Development Status  
Early stage (planning, initial prototyping). Validated via Polkadot Blockchain Academy and WebZero Hackathon (Consensus Toronto). UI/UX and architecture planning completed.

---

## Development Roadmap

### Overview
- **Estimated Duration:** 3 months  
- **Full-Time Equivalent (FTE):** ~1.5 FTE  
- **Total Costs:** $30,000 USD  

### Milestones & Deliverables

| Number | Deliverable | Specification |
| -----: | ----------- | ------------- |
| 0a. | License | Apache-2.0 (GUI & custom tooling); Smoldot (if used) GPL-3.0-or-later as separate bundle. |
| 0b. | Documentation | Inline docs, quick-start tutorial (launch app, send transfer, explore blocks, genesis pallet selection, snapshots). |
| 0c. | Testing & Guide | Unit & integration tests, E2E (Cypress), detailed guide. |
| 0d. | Docker | Dockerfile for running UI & connecting to local sandbox, desktop packaging instructions included. |
| 0e. | Article/Workshop | Public article/workshop on Polka Sim’s practical use for onboarding, hackathons, bootcamps. |
| 1. | Core Sandbox + Explorer & Transactions | Desktop app with packaged Substrate dev node, GUI connects via polkadot-js API; wallets, transactions, live explorer. |
| 2. | Runtime Config, Snapshots & Release | Pallet selection at genesis, snapshot import/export, docs, tutorials, IPFS/GitHub deployment. |

### Budget Breakdown  
| Task | Total |  
| --- | --- |  
| Dev node & blockchain integration | $8,000 |  
| UI: Explorer & transactions | $7,000 |  
| Runtime config & snapshot tools | $7,000 |  
| Docs, tutorials, Docker, release | $4,000 |  
| Maintenance & updates (6 months) | $4,000 |  
| **Total** | **$30,000** |

---

## Future Plans  
- Short term: Promote in hackathons, workshops; iterate on feedback.
-  Maintenance: Included 6-month support for SDK compatibility, OS packaging.  
- Long term: Future grant proposal for Chopsticks, multi-node setups, XCM support.

---

## Additional Information  
- Validated via Polkadot Blockchain Academy & WebZero Hackathon (Consensus Toronto).  
- Exclusive funding submission to Web3 Foundation.
