**JMES Whitepaper Pre-launch v1.0**


# 1 Introduction

JMES is an open-source Application-Specific Cryptocurrency created to power JMES World, a decentralized community for art, with the goal of becoming the world's largest decentralized art ecosystem.

Based on the Cosmos SDK and connected to Cosmos Hub (IBC), a validator-based blockchain secured using Tendermint consensus powers the native JMES token (symbol: JMES) for use as a currency for art.

JMES functions as a global decentralized brand, through the implementation of a decentralized core team offering solutions to the network for the overall management and funding of the contributors developing and working on the project.

A business layer enables anyone to kickstart new ideas to grow JMES using funding from the blockchain, as well as the option to act in an official capacity, by creating DAOs (Decentralized Autonomous Organizations) within the governance and funding system.

JMES is designed to address the problem of centralization in the art industry by providing an economic solution. The goal is to create a fully incentivized ecosystem where art consumers and producers can participate in a circular economy. Within this ecosystem, JMES enables individuals to secure ownership, incentives, and rights to all artworks, both physical and digital.

This is needed to enable JMES to scale as a decentralized global application using free-market principles to explore and deliver the right incentive and business models to grow its userbase.

JMES has a max supply of 1,000,000,000 tokens, a blocktime of around 5 seconds, an initial block reward of 17.92 JMES, and a reduction schedule of ~12.6% every 12 months.

The JMES blockchain is governed by a set of System Smart Contracts detailed below.


# 2 Consensus Layer

The Consensus Layer is the base layer of the platform consisting of a native JMES cryptocurrency implemented as a proof-of-stake (PoS) blockchain secured by an incentivized peer-to-peer (P2P) Validator network employing the Tendermint consensus algorithm.


## 2.1 Validators

To ensure fairness and security of the JMES protocol, a PoS consensus algorithm determines the weight of validators in the P2P network by the amount of staked JMES used as collateral.

To be a validator candidate, the operator needs to broadcast a specific create_validator message to the network. The selection of the active validators is then made based on the weight of their stake. The active validator set is limited to 100 validators at the protocol level and chosen by the largest amount of stake (including delegated stake). Losing staked coins and falling out of the top 100 rank or being disconnected from the network sets the validator to inactive causing it to lose its spot in the active set, no longer participating in consensus or earning rewards.

Each new block validates the transaction and mints new JMES tokens in the form of a block reward.

Half of the block reward goes to the validators and delegators, with the other half distributed directly to the wallets of the granted DAOs. Unused DAO allocation is burnt.

The selected validator produces the next block in the blockchain and earns a bonus reward of up to 4% of the validator and delegator rewards.

Note that in terms of distribution, at no time are newly created coins held in custody either by an individual wallet or a smart contract. Rather, newly created coins are always distributed directly to the recipient.


## 2.2 Delegation

Any holder of JMES can delegate their JMES to a running validator, by bonding an amount of JMES in their own wallet, then referred to as bJMES. The block reward is split proportionally across all delegators, with the coins created whenever those delegators redeem them individually.

For the cost of running the validator, the validator operator can define a commission rate that would be charged to delegators.

A validator can also self-delegate.


## 2.3 Tokenomics

JMES has a max supply of 1,000,000,000 coins. The average blocktime is 5 seconds and the initial block reward is 17.92 JMES, with a reduction schedule of ~12.6% every 12 months. We refer to the unit of division of a JMES to 6 decimal places as a Nils, meaning there are 1 million Nils per JMES coin, for example 0.000001 JMES.

A total premint of 104,000,000 JMES, or 10.4% of maximum supply, is created via transactions in the genesis block. These premint coins are locked against spending and voting in the protocol initially, then gradually unlocked with each consecutive block by an amount in proportion to the intended total premint % of max supply, i.e., 10.4%. For example, with the initial block reward of 17.92 JMES per block before the first block reward reduction period, 2.08 of the JMES locked in the premint wallets are also unlocked per block, in proportion to the wallets share of the total premint, meaning the effective total addition to circulating supply was 20 JMES in that block. After the first reduction, when the block reward is reduced to ~15,658 JMES per block, the total unlocked premint reduces to ~1,817 JMES per block for that period, and so forth.

The unlocked coins can be spent and voted with but are still locked against staking in the premint address, to avoid a situation where the 10.4% is exceeded by the premint holders, which would break the intention of the premint agreements. This approach combined means that the maximum percent of circulating supply that is issued to preminters does not exceed the intended 10.4% allocation.

The purpose of the premint is to provide fixed long-term incentives for the initiators who see JMES as their life's work to build up the world's largest decentralized ecosystem for art.


## 2.4 Initial Distribution Period

The Initial distribution of JMES is achieved with a fair launch where anyone can setup a validator to compete to mint JMES.

The code for JMES is fully open source under MIT/Apache2 license and will be published on GitHub ready for anyone to compile and instantiate the first validator that will then mint the first block and effectively launch the JMES Network.

During the first ~28 days (483 840 first blocks), JMES will be in the Initial Distribution Period setup. This period allows validators to be created, be included in the active validator set and to withdraw rewards and commission without any required stake or fee.

Validators within the active set compete to be the block proposer. 

Based on the proposer selection weighting mechanism, the selected proposer is entitled to a 4% reward.

The ability to mint is given to a maximum of 100 validators. If the active set drops below 100 (i.e. if validators drop out of the set), new non-active validators will enter the set. 

After the initial distribution period ends, a stake is required to join the set, meaning if the number of validators in the set drops below the limit of 100, validators outside of the set without a stake won't be allowed into the set.

Validator's commission will only activate at the end of this 483,840 blocks period (resulting in a 0% effective commission rate for the first 28 days).

As a Cosmos compatible blockchain, JMES can be exchanged for other cryptocurrencies using existing Cosmos compatible DEXs (decentralized exchanges). The initial JMES source code developers will not provide any direct exchange services. 3rd party exchange services exist that can be integrated into the client wallet if the DAO decides to pursue this option after launch.

During this initial distribution period of 483 840 blocks, the 50% DAO reward portion of block rewards aren't sent to DAOs, as DAOs can only be created when that period ends. Instead, these coins are allocated to Validators, meaning that validators earn 100% of the block rewards during this period, from the genesis block until block 483,841.

Note that there is no facility at the base layer to engage in any kind of brokerage between JMES tokens and other assets.


# 3 Business Layer

The Business Layer is a novel way to bridge real-world entities to the Consensus Layer through incentivized decentralization.

Comprising a collective of DAOs (Decentralized Autonomous Organizations) created and governed by the community, it represents and funds tangible businesses and organizations via the blockchain, with DAOs able to effectively receive up to 50% of block rewards.

DAOs stimulate user growth and economic activity in JMES by providing valuable services as per community needs, including tokenization of real-world assets, artist management, event hosting, software development, and strategic brand management.

The Business Layer is implemented as a suite of System Smart Contracts. These smart contracts are integrated into the Consensus Layer, enabling its core Identity, DAO, and Governance services.


## 3.1 Identities

Identities are the core construct in the Business Layer representing users who will engage with the system as individuals or as a group (as Directors of a DAO), implemented via a System Contract called the Identity Service within the Business Layer.

The Identity Service provides the ability to register validated, human-readable names for User Identities and DAO Identities. Both Identity types share the same namespace to protect impersonation attacks.

Identities can be resolved via bi-directional lookup: A wallet address can be resolved into a name and a name can be resolved into a wallet address. It also allows you to retrieve a paginated list of all existing DAOs.


### 3.1.1 User Identities

To facilitate social interaction in JMES and prevent spoofing, users can create their own User Identities. This allows anyone to sign up with a unique username on the blockchain.


### 3.1.2 DAO Identities

DAO Identities are special Identities that any User Identity can create, the instances of which are known as DAOs in JMES, that represent real-world businesses and organizations that are funded from the blockchain via the Governance System.

A name for the DAO must be provided on creation that is unique across the shared DAO Identity and User Identity namespace, to make it easier to identify and find them in the network and prevent spoofing via a duplicate DAO name.


## 3.2 DAOs

DAOs are the instances of DAO Identities described above and are the only entities that can raise Governance Proposals via the Governance System.

Creating a DAO involves collecting the cryptographic addresses of the User identities that will control the DAO's wallet, known as the Directors, and assigning a voting power to each address and a threshold that is required to pass a DAO Proposal. Up to 9 Directors can be defined. This key-value pair list gets sent to the DAO System Smart Contract which then instantiates a copy of the DAO code and assigns the new DAO its own multisig contract address.


### 3.2.1 Directorship

The list of Directors can be modified by a DAO Proposal itself.


### 3.2.2 DAO Proposals

DAO Proposals enable the Directors to poll decisions, vote on spending of DAO funds, and vote on raising Governance Proposals from the DAO to the wider Governance System, within the Director set.

DAO Proposals can be raised by any Director, then each address can vote on the proposal according to their voting power, and the proposal will pass or fail according to the threshold specified in the DAO's Director setup.

Funds in the DAO Identity cannot be spent without a DAO Proposal that passes authorizing the spend.


### 
3.2.3 Official Features

Official Features are special features available within the Business Layer that can be awarded to any DAO that requests them via a Governance Proposal that is passed by voting bJMES holders.

Generally, Official Features provide the framework for producers and consumers of art to interact and exchange value and intellectual property in ways that satisfy the compliance, quality and standards that the community deems necessary to officially represent the JMES ecosystem.

Specifically, Official Features assign permissions for DAOs that obtain them to call specific System Smart Contracts that perform the actions the feature enables, which will often be to mint certain non-fungible token-representing assets that are officially sanctioned by the Governance System, which represents the JMES community as a whole.

It's possible to verify assets produced by DAOs with Official Features by proving the origination from the DAO who minted them, and that they had the Official Feature in question permissioned via the relevant Governance Proposal at the time.

Initially, the only Official Feature is for the DAO to act as an Art Dealer, giving them permission to mint Official Artwork NFTs.

Each DAO can be awarded with multiple Official Features at any time, so that DAOs themselves are not considered Official as a whole, only in the use of specific features that they take.


### 3.2.4 Core DAOs

The protocol allows for 3 DAOs to be elected into Core Slots via a Governance Proposal, enabling them to work together to provide Core functions for the JMES ecosystem, but at the same time be removable or replaceable at all times.

Known collectively as the Core DAOs, the DAOs occupying the Core Slots form essentially a decentralized version of the Core Team found in other cryptocurrencies.

The three Core Slot positions available in the protocol are named to represent the functions the DAOs that occupy the slots will perform:



1. Brand, Marketing & Communications
2. Community Engagement
3. Technology

Core DAOs must have at least 3 Directors and no more than 9. A minimum of 2 Directors are required to pass the proposal threshold. Provided the identities are real individuals, this helps prevent attacks and key loss while also promoting a basic level of decentralized control over network funds within the DAO.


## 3.3 Governance System

In JMES, governance involves DAOs requesting funding and official features from the Business Layer through governance proposals. These proposals are created by DAOs and voted on by bJMES holders. The voting takes place within a recurring ~4-week voting/posting governance cycle. The votes are tallied, and the governance proposals either pass or fail based on the results.


### 3.3.1 Governance Proposals

Any DAO can create a Governance Proposal by burning an amount of 10 JMES to send the proposal to the Governance System Contract (GSC). Once a proposal has passed the voting threshold and the voting period has ended, anyone can pay the fee to conclude the proposal and execute attached messages.

There are five types of Governance Proposal that any DAO can create:


#### 
3.3.1.1 Text Proposal

A Text Proposal is the most basic type of Governance Proposal, consisting of a Title and a Description, and an optional attachment of a Funding Request.

Without a Funding Request, Text Proposals enable DAOs to take a survey in the network on a topic that may relate to the DAO or anything outside the DAO.

With a Funding Request attached, the Text Proposal can be used as the basic element to fund DAOs from the blockchain. An example could be the commissioning of an art piece.


#### 3.3.1.2 Request Feature Proposal

A Request Feature Proposal allows a DAO to request permission to use an Official Feature from the set of available Official Features within the System Smart Contracts maintained on the Business Layer by the currently elected Technology Core DAO.

This type of proposal also requires the DAO who creates it to attach a Funding Request, with the period of the funding used to revoke the permission to use the feature when the funding period expires, if the proposal passes. Note that the funding amount can still be specified as zero, but the period must be specified.


#### 3.3.1.3 Core Slot Proposal

A Core Slot Proposal is a Governance Proposal that enables any DAO to request to occupy a Core Slot, enabling it to perform functions as part of the decentralized Core Team.

Each DAO can request to be assigned to occupy one of the Core Slots via a Core Slot proposal, but each DAO can only be in one of the Core Slots at any given time.

If a Core Slot is taken, a new DAO can apply for the same Core Slot in the first week of any governance cycle's posting window. The occupying DAO can challenge the revocation at any stage of the same posting window.

If two or more DAOs apply for the same Core Slot in the same voting period, the DAO with the highest net YES vote count wins and takes the Core Slot.

After a core slot proposal has passed the voting threshold and the voting period is over, anyone can pay the fee to conclude it and assign the core slot to a DAO address. Ideally, the proposal with the highest net "yes" votes should be executed. However, if a competing proposal with lower net "yes" votes is concluded first, that DAO will temporarily occupy the core slot until the winning DAO's proposal is concluded, at which point it will replace the current core slot.

A Funding Request must be attached to each Core Slot Proposal, so that the period can be used to revoke the Core Slot on expiry. However, the amount in the Funding Request may be specified as zero.

A Core DAO can be verified as occupying a Core Slot if if they have a passed and non-expired Core Slot proposal existing, with no subsequent Core Slot proposals by another DAO for the same Core Slot was passed, and no subsequent Revoke Core Slot Proposal for the DAO's Core Slot that passed.

Since a DAO can only hold one core slot at a time, a DAO currently holding a core slot has to manually resign that slot during the voting period in anticipation of their passing proposal for a different core slot. If their passing proposal has the fee paid to be concluded (which can be done by anyone) and the DAO still holds their old slot, it will forfeit the new slot even though the proposal has passed the voting threshold. 


#### 3.3.1.4 Improvement Proposal

Improvement proposals implement code migration changes to the System Smart Contracts and can be raised by the Core Tech DAO.

If the proposal is passed, the code upgrade will automatically be performed upon conclusion of the proposal. If they are not approved, the code update will not be executed.

An Improvement Proposal cannot have funding attached.


#### 3.3.1.5 Revoke Core Slot Proposal

A Revoke Core Slot proposal can also remove any DAO that's occupying a Core Slot, which if passes, leaves the Slot empty and stops the funding for the DAO.


### 3.3.2 Funding Requests

DAOs may include a Funding Request as an attachment to any Governance Proposal type, except Revoke Core-Slot and Improvement Proposals. This requests permission to issue new coins to themselves within their own wallet, from within the 50% of total block rewards available across all winning DAO proposals, if the Governance Proposal passes.

The request for funding must include an amount of JMES and a number of months over which the JMES will be paid, which is converted to number of blocks by the GSC, using the average block time of 5 seconds and the assumption of 2,629,745 seconds in a month.

For example, a DAO wants to be able to allocate themselves 100,000 new JMES tokens over 3 months: The 100.000 JMES will be paid to the DAO address over the next 1,577,847 blocks (rounded down) at 0.063377 JMES (equals 6,3377 Nils) per block.

This means if the proposal is concluded at block 50,000,000, the DAO will have received 50% (= 50,000) of its requested JMES token at block 50,788,923 and 100% (=100,000) within rounding constraints, of the JMES token at block 51,577,847.

The maximum funding that each DAO can request in a cycle is 25% of the total DAO budget.

Note that the percentage of the total budget for Core DAOs is capped at 50% of the total available DAO budget (so 25% of total block rewards). This means that if the combined ask (amount requested in proposals) of the Core DAOs exceeds the 50% cap on the total DAO budget, the Core DAO proposals with the lowest votes that exceed that amount won't be funded.

JMES Distribution Example:




![image info](./pictures/dist.png)



### 3.3.3 Governance Cycle

The Governance Cycle is the recurring period of DAOs raising Governance Proposals followed by JMES holders voting on those proposals. It is split into two weeks of raising Governance Proposals, followed by two weeks of voting on those proposals, at which point votes are tallied and the cycle loops. This means that a minimum of 15 days is required to create a proposal and have it voted in.

The Governance Cycle starts after launch so that new proposals can be raised in the first two weeks after the blockchain is launched and voting in weeks three and four, meaning that the first DAO proposals will be tallied 4 weeks after the genesis block. The cycle continues from that point.

Note that the Governance Cycle periods are calculated based on time, with 607126.1538 seconds in a week (this is an average considering the leap years in the following 10 years). Once a proposal is passed, the funding is paid out linearly according to the blockheight.


### 3.3.4 Voting

Any JMES holder is eligible to vote on any Governance Proposal.

Voting requires the JMES to be bonded for a validator in the user's own wallet, meaning those JMES are marked with a special status making them unspendable and only usable for the purpose of tallying them for voting and derivation of staking rewards from the validator they're bonded to.

Bonded coins remain in the owner's wallet at all times and are never transmitted or under the control of another wallet.

Unbonding JMES has a delay of 21 days during which time they can't be used for voting or earning staking rewards, however, bonding is instant, and instantly gives voting rights.


### 3.3.5 Tallying

Votes on Governance Proposals are tallied at the end of the voting cycle and a determination is made on which proposals pass or fail via the protocol as follows:

Governance Proposals pass when the net total of YES votes is equal to or greater than 10% of total possible votes at the end of the voting period. This means that after NO votes are subtracted from YES votes, the number of YES votes remaining must be equal to or greater than 10% of all bonded JMES at the time the vote is tallied.

For Governance Proposals that pass with non-zero Funding Requests, on each block during the funding period of the request, the decision to allow funding is calculated by ordering all Governance Proposals with Funding Requests eligible at the time of the current block in order of YES minus NO votes. This means that the more popular Governance Proposals get priority within the available block rewards allocated to the DAO budget, and once the first eligible proposal's entitlement would exceed that request, it and any less popular proposals following it are not paid.

When Governance Proposals ask for tokens and they are approved, the decision to give them funding is determined by comparing the number of "yes" votes minus the number of "no" votes. This calculation is done for each block during the funding period. The proposals are then ranked based on this result. The more popular proposals are given priority for the available funds in the DAO budget. However, if the first eligible proposal's funding exceeds the available amount, it and any less popular proposals that come after it will not receive any tokens.