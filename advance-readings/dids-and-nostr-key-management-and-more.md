# DIDs and Nostr &mdash; Key Management and More

- by [Stevan Eraković](mailto:stevan.erakovic@danubetech.com), Danube Tech
- Version 0.1.0

---

# The Protocol

[Nostr](https://github.com/nostr-protocol/nostr) (Notes and Other Stuff Transmitted by Relays) is a simple, open protocol that defines the communication between clients and relays using Events (of various kinds: metadata, recommended relay, text notes, etc.). The users are identified by their public key. They create notes, and send them to one or more relays. “Following a user” means being subscribed to receive messages associated with a particular public key.

# The Problem

Public key ≡ Identity ⇒ One key for all clients (native, web..), with no option to change keys in case of compromise, and, at the same time, keep the user profile.

Current solution &mdash; Delegated Event Signing ([NIP-26](https://github.com/nostr-protocol/nips/blob/master/26.md)) “defines how events can be delegated so that they can be signed by other keypairs”. The problem with this is, in the words of the protocol author:

> The idea is that someone will generate a very safe key on a hardware device and guard it as their most precious treasure without it ever touching the internet, and use it just to sign delegation tags. (…) This breaks the previous expectations I had for NIP-26 entirely, as now these keys become faceless entities that can’t be associated with anything *except their “master” key* (the one that is in cold storage). So in a world in which most Nostr users are using NIP-26 for everything, clients that do not implement NIP-26 become completely useless, as all they will see is a constant stream of random keys. They won’t be able to follow anyone or interact with anyone, as these keys will not identify any concrete person on their back, they will vanish all the time and new keys will show up and the world will be chaotic. So now every client must implement NIP-26 to become usable at all, it is not *optional* anymore [^1].

# DIDs &mdash; a natural fit

DIDs &mdash; persistent, decentralized, cryptographically verifiable identifiers that resolve to machine-readable documents &mdash; can be used to discover the public key of a Nostr user, or any other verification method and metadata needed for secure communication. The fact that the DID Document can be updated facilitates easy exchange of the underlying cryptography systems.

At the same time, DIDs can be used to discover the user’s list of recommended relays, and any other information specific to Nostr.

A variety of DID methods means we can choose the set of (privacy, decentralization, etc.) properties we want to implement.

A [Version Service](https://docs.godiddy.com/en/apis/version-service) offers to look up historical versions of DID Documents, thus enabling insight into all the keys associated with the DID.

# Resources:

[^1]: _Why I don’t like NIP-26 as a solution for key management_, https://fiatjaf.com/4c79fd7b.html, accessed 5 July 2023

[NIP-01: Basic [Nostr] protocol flow description](https://github.com/nostr-protocol/nips/blob/master/01.md)

TBD's `did:nostr` DID method https://github.com/TBD54566975/did-nostr
