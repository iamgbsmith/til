# Ethereum Node Types

__Category: Blockchain__

A node is any instance of Ethereum client software that is connected to other computers also running Ethereum software, forming a network. 

Ethereum node types can be one of the following:

* Full node - stores all blockchain data and participates in block validation, verifying all blocks and states.
* Light node - downloads block headers containing summary information about the contents of blocks. Any other information required by the light node gets requested from a full node. Light nodes enable users to participate in the Ethereum network without needing the hardware or bandwidth to run a full node.
* Archive node - stores everything in a full node and builds an archive of historical states. Typically used for services like block explorers, wallet vendors, and chain analytics.

Clients that sync in light or full mode will store pruned blockchain data. Nodes can also sync against Mainnet or a Testnet.

See [Nodes and Clients](https://ethereum.org/en/developers/docs/nodes-and-clients/) for more details.
