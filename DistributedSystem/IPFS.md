# Concepts

IPFS is a distributed system for storing and accessing files, websites, applications, and data

- Decentralization

- Content addressing

- Particiopation

  Today's World Wide Web is structured on *ownership* and *access*

  IPFS is based on the ideas of *possession* and *participation*, where many people *possess* each others' files and *participate* in making them available.

## A modular paradigm

The IPFS ecosystem gives **CIDs** to content and links that content together by generating **IPLD Merkle DAGs**. You can discover content using a **DHT** that's provided by **libp2p**



## CONTENT-ADDRESSED DATA

### Content addressing and CIDs

IPFS uses *content addressing* to identify content by what's in it rather than by where it's located, every piece of content has a *content identifier* (CID)

### Immutability

To manage *immutable* files in a *mutable* system, we need to add another layer(IPNS) that sits on top of CIDs.

### Persistance

- Garbage Collection
- Pinning



## PEER-TO-PEER SHARING

### DHTs

the fundamental component of the content routing system

 It maps what the user is looking for to the peer that is storing the matching content.

A *distributed* hash table is one where the table is split across all the peers in a distributed network. To find content, you ask these peers. In order to get to content, use libp2p to query the DHT twice:

1. which peers are storing each of the blocks that make up the content you're after
2. the current location of those peers (*routing*)

- Kademlia (k=20)

  three system parameters：

  1. An *address space*, all of the peers can be uniquely identified
  2. A *metric* to order the peers
  3. A *projection* that will take a *record key* and calculate a position in the address space where the peer or peers most ideally suited to store the record should be near.

- Dual DHT

  | DHT  | Path                  |
  | ---- | --------------------- |
  | WAN  | `/ipfs/kad/1.0.0`     |
  | LAN  | `/ipfs/lan/kad/1.0.0` |

  WAN DHT nodes switch from client to server mode based on whether they are publicly dialable, LAN DHT nodes are always servers unless the `dhtclient` option has been set

- Routing Tables

  - qualification
  - peer buckets
  - refreshing/dropping peers

### Merkle DAGS

A Merkle DAG is a DAG where each node has an identifier, and this is the result of hashing the node's contents

IPFS lets you give CIDs to content and link that content together in a *Merkle DAG* 

- To build a Merkle DAG representation of your content, first splits it into *blocks*, 
- The properties of the hash function ensure that no cycles can exist when creating Merkle DAGs.
- Parts of different Merkle DAGs can reference the same subset of data, means two similar files can share parts of the Merkle DAG

### Bitswap

Bitswap is a core module of IPFS for exchanging blocks of data. It directs the requesting and sending of blocks to and from other peers in the network.

A `want-list` is a list of CIDs for blocks a peer wants to receive

### IPLD

--

### IPNS

A *name* in IPNS is the hash of a public key. It is associated with a record containing information about the hash it links to that is signed by the corresponding private key.

### Libp2p

--

### File systems

- Mutable File System

  MFS is a tool built into IPFS that lets you treat files like you would a regular name-based filesystem

- Unix File System

  UnixFS is a protobuf-based format for describing files, directories, and symlinks in IPFS. This data format is used to represent files and all their links and metadata in IPFS. UnixFS creates a block (or a tree of blocks) of linked objects.

## INTERRATING WITH THE WEB

### IPFS Gateway

IPFS gateways provide an HTTP-based service that allows IPFS-ignorant browsers and tools to access IPFS content.

### DNSLink

DNSLink uses *DNS TXT* records to map a domain name to an IPFS address. Because you can edit your DNS records, you can use them to always point to the latest version of an object in IPFS

## Privacy

Information about which nodes(PID) are retrieving and/or reproviding which CIDs is publicly available.

IPFS protocol itself does'nt explicitly have a "privacy layer", but still have some approaches to enhance privacy:

- Controlling what you share
- Using a public *gateway*
- Using *Tor*
- Encrypting content transported via IPFS
- Creating a private network

## Glossary

https://docs.ipfs.io/concepts/glossary/



# WhitePaper





