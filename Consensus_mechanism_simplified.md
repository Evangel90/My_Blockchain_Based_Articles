# Consensus Mechanism Simplified

Blockchains utilize different mechanisms to achieve consensus (agreement). However, to understand these mechanisms, we must first grasp the need for consensus.

In a system where anyone is welcome to participate, such as in public blockchain networks, there must be a way for participants to agree on the state of the blockchain.

The state of the blockchain is altered by transactions, which are then packed into blocks that are cryptographically connected to the already agreed-upon chain (canonical chain).

If a participant alters the state of the blockchain without the agreement of others, it is said that there is no consensus.

What happens in situations where groups of participants in the network agree on a particular state of the blockchain while other groups disagree?

The consensus mechanism determines how different blockchains decide which group prevails and what the correct state of the blockchain is.


## Using Bitcoin and Ethereum as Case Studies

Bitcoin and Ethereum are both public blockchains where anyone is welcome to participate, with a caveat: not every participant is allowed to alter the state of the blockchain.

> Remember, consensus is needed when there is an attempt to alter the state of the blockchain. 

### Bitcoin
The only nodes that can alter the state of the Bitcoin blockchain are those with sufficient computational power to solve the mathematical puzzle posed by the Bitcoin network when attempting to make those state changes. 

This process is known as **proof-of-work (PoW)**.

When a node is successfully able to solve the mathematical puzzle, it broadcasts the new block to other participating nodes, which then perform the necessary verifications before adding the block to their individual chains.

The canonical chain is determined after this process has occurred multiple times. Through cryptography, a node can ascertain that other nodes have the same chain, hence achieving consensus.

In the case of divergent chains, where different groups of nodes seem to be working on different chains, Bitcoin uses the longest chain rule.

The longest chain rule implies that the chain with the highest proof-of-work is the canonical chain.

> Hence, the consensus mechanism in Bitcoin is a combination of what I will call a "pre-consensus process," i.e., PoW, and the main consensus mechanism, which involves the verification and addition of blocks to the individual node chains and the longest chain rule.

This whole process, pre-consensus + main consensus process, for Bitcoin is known as **Nakamoto's consensus**.

### Ethereum
In order for a node to be able to propose a change of state to the Ethereum blockchain, that node must have at least **32 ETH** staked on the Ethereum network, known as **proof-of-stake (PoS)**.

Unlike Bitcoin, the nodes that propose the next block are chosen randomly from a group of eligible nodes and are known as validators. 

Consensus is determined in Ethereum by a group of validator nodes that attest to the proposed block by the chosen block proposer and then broadcast to the network whether the block has been validated or not. Every node still validates the block before adding it to their respective chains. 

> Here, the canonical chain is determined by a committee of validators. Other nodes follow, though they still perform validation individually and refuse to add blocks to their chain if malicious activity is detected.

Validators use a consensus mechanism known as Gasper to determine the canonical chain in the event of a divergence. Gasper determines the rules of consensus that every Ethereum node follows.

[Gasper](https://ethereum.org/developers/docs/consensus-mechanisms/pos/gasper/) is a combination of Casper-FFG and LMD-GHOST fork choice algorithm. 

Together, these components form the consensus mechanism securing proof-of-stake Ethereum. Casper is the mechanism that upgrades certain blocks to "finalized" so that new entrants into the network can be confident that they are syncing the canonical chain. The fork choice algorithm uses accumulated votes to ensure that nodes can easily select the correct one when forks or divergences arise in the blockchain.

## Conclusion

While Bitcoin and Ethereum employ fundamentally different consensus mechanisms, one based on computational work, the other on economic stake, both achieve the same ultimate goal: enabling a decentralized network of participants to agree on a single, canonical version of the blockchain.

Bitcoin's Nakamoto consensus prioritizes openness and resistance to coordinated attacks through computational difficulty, making it harder for any single entity to control the network through sheer power. Ethereum's Gasper consensus, conversely, leverages economic incentives and committee-based validation, enabling faster finality and lower energy consumption.

The choice of consensus mechanism reflects each blockchain's design philosophy: Bitcoin emphasizes absolute decentralization and immutability through proof-of-work, while Ethereum prioritizes scalability and sustainability through proof-of-stake. Understanding these mechanisms is essential for grasping how blockchains maintain security and trust without central authority.


