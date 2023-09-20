# Exchanges through NOSTR for DID Holders

**Authors:** Imad El Aouny & Frederic Martin

# **Abstract**:

Nostr is a simple, open protocol that enables global, decentralized, and censorship-resistant social media.

This paper explains how two DID holders can securely :
- establish end to end encrypted communication channels
- exchange credentials
- send and receive text messages
 
We will provide a simple protocol with partial implementation source code  to ensure this seamless and trusted exchanges.

The protocol follows a series of steps to ensure a seamless and trusted exchange through encrypted messages :
- Request, issue and receive Verifiable Credentials 
- Request, issue and verify Verifiable Presentations

# **NOSTR: messaging protocol based on public relays**:

NOSTR means Notes and Other Stuff Transmitted by Relays.
It is a simple protocol to exchange messages between clients / users using the same relay.

Nostr is based on two components: clients & relays (servers). 
Each user runs a client. 
Anyone can run a relay.
Relays don't talk to one another, only directly to users.
Clients fetch data from relays of their choice and publish data to relays of their choice.
Relays don't talk to one another, only directly to users.
Every post is signed. Every client validates these signatures.

Every user is identified by at least public key but you need to know a relay server where this key is used. 

In the end, the full reference to a Nostr user si done through two elements : a publickey and a relay server info (web url).

Nostr constraints : All messages are public.
