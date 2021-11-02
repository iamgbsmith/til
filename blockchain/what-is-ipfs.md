# What Is IPFS

__Category: Blockchain__

Interplanetary File System (IPFS) is a public, distributed, peer-to-peer network for storing and retrieving files. There is no central server that can be shutdown and anyone can participate in the network. A typical use of IPFS is for storing of digital assets such as non-fungible tokens (NFTs) with metadata being stored on-chain.

### IPFS Characteristics

* IPFS addresses files using a cryptographic hash called a Content Identifier (CID). By default, the hashing algorithm is SHA-256. If a file changes, the address (CID) to that file will change. This differs from the traditional web which uses HREF location based addresing.
* Content cannot be removed from IPFS if a network participant chooses to make it available, irrespective of whether that person is the original author or not. 
* Nodes advertise that they have CIDs available for other nodes to use through publicly viewable distributed hash tables (DHTs).
* Content that needs to be available more permanently can be "pinned" which saves it locally and makes it available on the IPFS network until a decision is made to unpin it.

### IPFS Security Considerations

* Traffic between nodes is encrypted however metadata that nodes publish to the DHT is public.
* Nodes announce a variety of information essential to the DHT's function, including their unique node identifiers (PeerIDs) and the CIDs of data that they are providing. 
* Information about which nodes are retrieving and/or reproviding which CIDs is publicly available.
* Sensitive content should be encrypted prior to being stored on IPFS.
* It is possible to run a private IPFS network to prevent public monitoring although this requires operational overhead which may negate any usage benefits.

See [IPFS concepts](https://docs.ipfs.io/concepts/) for more details.
