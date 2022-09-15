# Blockchain Dev Roles (post on Github)

# Introduction
This document describes several developer roles used in a blockchain environment as well as their skill sets and links to applicable EOS related documentation. EOS related content is located [____________] and is currently under construction.

EOS related content topics are tagged with these developer roles and can be directly accessed from the content portal (under construction) for developer journeys through the EOS related content.

## Community Contribution
Interested in contributing? That's awesome! [Here are some guidelines to get started quickly and easily](https://github.com/eosnetworkfoundation/welcome/blob/main/CONTRIBUTING.md).

All comments and suggestions are welcome and appreciated. Please feel free to add your comments, changes, and updates to this documentation through Github.

# App Developer
|  | **Description** | 
| --- | --- |
| Objective | * Create a PoC
* Create a releasable app
* Application Management and various project management tasks
* Application development lifecycle
 * Planning and Design
 * Development and Testing
 * Deployment and Support
* Troubleshooting and Debugging
* Monitoring, updates, and security
* End User support and training
* Project Management, Collaboration, and Communication | 
| Skill Set | * Web and mobile development languages, such as JS, TypcScript, JHava, C#, Python, Swift, etc.
* May not have C++ experience | 
| Doc Needs | * Community resource info
* Example apps and reference architectures
* Error handling/messaging and troubleshooting guide
* Getting Started Guide
* Examples and sample code
* Best practices
* Protocol Guides | 

Notes:
* Google “Blockchain App Development Tutorial” for ideas
* Apps for Mobile and Android
* Gaming Apps
* [Application Developer Job Description](https://www.betterteam.com/application-developer-job-description)
* [Mobile app developer job description](https://www.glassdoor.com/Job-Descriptions/Mobile-Developer.htm)
* [Roles and Responsibilities of application developers](https://www.bmc.com/blogs/application-developer-roles-responsibilities/)

Here are 10 examples of important mobile app developer skills to help you be successful:
* Programming language skills. ...
* Computer proficiency. ...
* Back-end computing. ...
* User interface (UI) design. ...
* Cross-platform development skills. ...
* Cybersecurity skills. ...
* Product management skills. ...
* Internet of things (IoT) skills.

# Block Producer
|  | **Description** | 
| --- | --- |
| Objective | * Block producers play a key role in the operation of the network. Block producers verify transactions on the EOSIO networks by collecting transaction data and storing that information in blocks. Once a block is prepared, block producers broadcast the block to the network for verification.
* In the Antelope ecosystem, block production and block validation are performed by special nodes called "block producers". Producers are elected by Antelope stakeholders. Each producer runs an instance of an Antelope node through the nodeos service. For this reason, producers that are on the active schedule to produce blocks are also called "active" or "producing" nodes.
* Select transactions and gather transaction data to build a new block
* Propose the next state of the new block by creating a different staged ledger to cover both the account ledger, and transactions that have yet to be proven
* Generate blockchain proof to validate the new state, and create a delta transition chain proof to verify the validity of the block within an acceptable network delay time frame (as defined by the network)
* Apply the proof to the new state
* Broadcast and disseminate the new block to other block producers.
* Submit new blocks to the network for reward after verification is completed | 
| Skill Set | * Collect and store transactions in blocks for validation
* Upload transaction data to the blockchain
* Expected to produce, achieve consensus, and broadcast the generated blocks within a specific time defined by the network consensus parameters | 
| Doc Needs | *  | 

* [https://learn.bybit.com/glossary/definition-block-producer/](https://learn.bybit.com/glossary/definition-block-producer/)

## Node Operator
|**Fields**  | **Description** | 
| --- | --- |
| Objective | <li>Node Operators run the blockchain's software, certifying transactions as they are entered into the chain by writing new blocks and broadcasting them to the network. They process blocks based on transactions that follow the blockchain's protocol rules. <li>Node operators participate within [decentralized networks](https://docs.chain.link/docs/architecture-decentralized-model), allowing engineers to [fetch external data](https://blog.chain.link/apis-smart-contracts-and-how-to-connect-them/) in a secure and reliable manner. They operate the crucial infrastructure responsible for ensuring [smart contracts](https://chain.link/education/smart-contracts) across every [blockchain](https://blog.chain.link/what-is-a-blockchain-and-how-can-it-impact-the-world/) have access to the [real-world data](https://blog.chain.link/understanding-how-data-and-apis-power-next-generation-economies/) they need to execute properly. |
| Skill Set |<li>Async developer<li>Error handling<li>APIs<li>OPS<li> Modules | 
| Doc Needs | <li> Node setups<li> Node configuration | 

**Notes:**
* [https://www.blockchainecosystem.io/ask/what-does-it-mean-to-be-a-blockchain-node-operator-are-there-any-blockchains-out-there-that-don-t-have-node-operators](https://www.blockchainecosystem.io/ask/what-does-it-mean-to-be-a-blockchain-node-operator-are-there-any-blockchains-out-there-that-don-t-have-node-operators)

# Front End Developer
|  | **Description** | 
| --- | --- |
| Objective | * Develops new user-facing features, determines the structure and design of web pages, builds reusable codes, optimizes page loading times, and uses a variety of markup languages to create the web pages.
* Translate wireframes from designers into fully realized user interfaces by creating the buttons, images, links, and pages that all need to function efficiently, accurately, and quickly in order for the user to carry out a particular task | 
| Skill Set | * Uses web languages such as HTML, CSS, and JavaScript that allow users to access and interact with the site or app | 
| Doc Needs | *  | 

# Smart Contract Developer (C++)
|  | **Description** | 
| --- | --- |
| Objective | Smart contracts are programs stored on a blockchain that run when predetermined conditions are met. They typically are used to automate the execution of an agreement so that all participants can be immediately certain of the outcome, without any intermediary’s involvement or time loss. They can also automate a workflow, triggering the next action when conditions are met.
* An accessible and effortless way to interact with the blockchain
* Develop, deploy and manage smart contracts on a public blockchain (EVM or WASM).
* Explore design implications around smart contracts and their interactions with each other.
* Work with the Product team to explore feasibility and design of the decentralization of various processes.
* Take ownership from the ideation phase to deployment and management. | 
| Skill Set | Cleos or other 3rd party library to deploy to the blockchain

* participants must determine how transactions and their data are represented on the blockchain, agree on the “if/when...then…” rules that govern those transactions, explore all possible exceptions, and define a framework for resolving disputes. | 
| Doc Needs | * Need to understand core vs system layer
* Support for other languages (or links to resources)
* Debugging tools/support
* Testing tools/support
* Performance tuning best practices
* Cost optimization best practices | 

Notes:
* [Smart contract definition](https://en.wikipedia.org/wiki/Smart_contract)