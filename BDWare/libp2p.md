# Overview

**libp2p** is a modular system of *protocols*, *specifications* and *libraries* that enable the development of peer-to-peer network applications

What problems can libp2p solve?

- Transport

  At the foundation of libp2p is the transport layer, which is responsible for the actual transmission and receipt of data from one peer to another. 

- Identity

  libp2p uses *public key cryptography* as the basis of peer identity,

  - [PeerId](https://docs.libp2p.io/reference/glossary/#peerid)

- Security

  securely encrypted channel. 

- Peer Routing

  Peer routing is the process of discovering peer addresses by leveraging the knowledge of other peers. 

  The current stable implementation of peer routing in libp2p uses a [distributed hash table](https://docs.libp2p.io/reference/glossary/#dht) to iteratively route requests closer to the desired `PeerId` using the [Kademlia](https://en.wikipedia.org/wiki/Kademlia) routing algorithm.

- Content Discovery

  libp2p provides a [content routing interface](https://github.com/libp2p/interface-content-routing) for this purpose, with the primary stable implementation using the same [Kademlia](https://en.wikipedia.org/wiki/Kademlia)-based DHT as used in peer routing.

- Messaging/Pubsub

  libp2p defines a [pubsub interface](https://github.com/libp2p/specs/tree/master/pubsub) for sending messages to all peers subscribed to a given “topic”.

# Concepts

## Transport

- In libp2p, we call these foundational protocols that move bits around transports, and one of libp2p’s core requirements is to be ***transport agnostic***.

- Transports are defined in terms of two core operations: **listening** and **dialing**

   in libp2p share the same programmatic interface

- ***multiaddr***, an example includes a PeerId

  `/ip4/7.7.7.7/tcp/6543/p2p/QmcEPrat8ShnCph8WjkREzt5CPXF2RwhYxYBALDcLC1iV6`

- **switch**: responsible for composing ***multiple transports*** into a single interface

## NAT Traversal

- Automatic router configuration

- Hole-punching(STUN)

  an external peer can can tell us what address they observed us on, we can then take that address and advertise it to other peers in our *peer routing network* to let them know where to find us.

- AutoNAT

- Circuit Relay(TURN)

  allows peers to communicate indirectly via a helpful intermediary peer

## Secure Communication

## Circuit Relay

## Protocols

## Peer Identity

## Content Routing

## Peer Routing

## Addressing

## Security Considerations

## Publish/Subscribe

## Stream Multiplexing







