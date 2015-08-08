# Hyperboria/docs

## What is Hyperboria?

Hyperboria is test network built of cjdns nodes.

## What is cjdns?

Cjdns is an experimental, cryptographic mesh networking suite.

## What is notable about cjdns? Why should I use it?

Cjdns builds an end-to-end encrypted IPv6 mesh network that utilizes the fc00::/8 address space.

### Encryption

Cjdns provides an encrypted tunnel which utilizes a private/public keypair to encrypt everything that passes through it with the SALSA20 stream cypher, which affords the user perfect forward secrecy.

### Address Allocation

The ipv6 assigned to the TUN interface is composed of the first 16 bytes of the SHA512 hash of the SHA512 hash of your public key. Keypairs are generated via a brute force method until a corresponding address is found with a starting byte FC. The FC00::/8 address space has been allocated as a Unique Local Address space, and so these addresses should not conflict with ICANN assigned IPv6 addresses or any other conventional internet operation.

### Hybrid topology

Cjdns was designed to be used with a friend of a friend topology. It builds an overlay network which traverses NAT (Network Address Translation), exposing all ports of every node to every other node within the network. Those who are used to relying on NAT to protect their devices may find this troublesome.

At one point it was expected that each person who peered would do so with only trusted friends. You need not trust relaying nodes with the confidentiality or integrity of your packets, however, if you wish to restrict access to certain services, it is your responsibility to implement effective access control rules.

Links between nodes may be established over deliberate UDP links across the internet, or over deliberate or automatic connections across Ethernet, Wireless access points, Ad-hoc connections, or various system-specific transmission and addressing protocols.

### Cryptographic verification and routing

Establishing a link between two nodes includes a cryptographic authorization process, after which other nodes within the network can establish a connection with the new node.

Due to the relationship between each node's public key and its ipv6, and the fact that this relationship is verified upon connecting to a node, a user can be sure that if it connects to an IPv6 address and receives a response then the node that responded possesses the requisite private key to decrypt the response.

If you are able to connect at all over cjdns, then you can be quite sure that the node you connected to possesses the private key that corresponds to the IPv6.

## How can I get involved?

See our [contributing](contributing.md) document.
