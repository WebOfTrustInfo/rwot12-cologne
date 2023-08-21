# Deepkey: A Fully P2P Key Management Framework

By:

* [Arthur Brock](arthur.brock@holo.host), Co-Founder of Holochain
* [Collin McClain](collin.mcclain@holo.host), Writer and Researcher at Holochain

## Context

This is the first of three papers outlining the digital identity building blocks provided within the Holochain ecosystem. You could think of each of the three papers as discribing an implementation responding to each of the three corners of Zooko’s triangle. In this case, each corner has its own independent functionality and integrity from the other two corners. This approach to digital identity allows for a range of dynamic composition of identity solutions instead of a one-size-fits-all approach. This paper focuses on the non-human-friendly digital identifiers which are self-authenticating cryptographic keys.

## The Problem of Key Management: Sloppy Binding to other IDs

Typically, digital identity solutions which provide key management attempt to weave together digital identifiers, human-friendly identifiers, and some security criteria for binding those two types of identifiers together. The conflation of these functions and/or the lack of some of these function, are frequently the points of weakness in an identity soloution.

### Examples of the Problem:

**SSL Certificates:** Certificate with encryption keys, domain name bound to those keys, and finally the certificate issuer’s criteria for proving ownership of the domain such that they will sign your certificate giving you a valid chain of authority. Certificates expire and can be rotated or renewed by the people who proved ownership (typically via centralized login credentials).

**PGP Keys:** Self-issued public key, an email address to use with that key, and a variety of self-published, unreliable and confusing methods for people to try to determine which key is used by which email address. Since everything is self-published, you can rotate your keys whenever you want to, but it can be difficult to notify past parties of new keys.

**Blockchain Wallets:** Your wallet address is your public (self-authenticating) key, there is no inherent human-friendly identity bound to it, and no key management available to rotate or revoke your keys.

**[ENS](https://docs.ens.domains):** A smart contract grants control of resolving a registered name to the wallet address or other key of the purchaser of the name. This allows for redirection of the name to different addresses over time, but doesn’t provide key management for the controlling key or any other keys.

## How DeepKey is Different: Keys Managed only by Cryptography

DeepKey enables rotation and revocation of self-authenticating cryptographic keys relying only on signing by other such keys, without any unreliable bindings to human-friendly names or logins. This means validation of key management actions within DeepKey rely only on cryptography, not on KYC processes or other arbitrary bindings to human identity.

When someone starts running DeepKey, they declare a new KeySet using a one-time throwaway keypair to authorize their first DeepKey agent who can register new keys to this space. They also establish the initial management rules by identifying the first set of M of N keys with the authority to manage keys within the keyset.

Keys can be rotated and rules can be updated by the M of N authorized keys. Anyone can check `key_state((Key, Timestamp))` as a part of validating any action taken with that key.

DeepKey provides reliable key management, via a peer-to-peer distributed application, with no centralized authority, no human-friendly names, and no insecure bindings to those names.

By securing this one corner of Zooko’s triangle independently and without reliance on the others, it provides a stable foundation enabling the composition of these cryptographic IDs with names using a variety of verifiable claims as the secured bindings.

## Implementation:

What are the steps in key management? And how do they constitute an unbroken chain of cryptographically verifiable actions?

The following describes how DeepKey is implemented within Holochain, but these same principles should be useful in other implementations. We are hoping to explore how DeepKey can be extended to provide the same sorts of cryptographic guarantees and key management to Identity systems outside the Holochain ecosystem.

DeepKey is a Holochain application, so it is set up to run on top of the cryptographic guarantees that Holochain provides. It also provides its own cryptographic guarantees in the key management process. The following steps assume that you’ve already installed Holochain and Deepkey. They demonstrate that there are no weak or arbitrary bindings to other types of human-friendly identifiers, and that DeepKey’s management of keys can be validated by cryptography alone.

### First Stage: Establish a Key Management “Umbrella” along with its Management Rules

1. We use a throwaway keypair to declare a new KeySetRoot authorizing a First DeepKey Agent (for registering keys into the Management Umbrella) and the first ruleset. The significance of using a throwaway keypair is that the private key literally never leaves the secured memory of the cryptographic function. It is never persisted anywhere.
2. The KeySetRoot is essentially an SOA (Start of Authority) or Root Certificate for new keys to be registered and managed by the current set of rules for that space.
3. The initial default M of N management rules define one authorizing key, and requires that one signature to change keys. This 1 of 1 pattern functions as if there is a single revocation key under which all key registration, replacement, or revocation must happen. Alternately, these rules can be configured so that any M number of signatures from a list of N authorized keys is needed to manage keys. This should be differentiated from Shamir secret sharding.

### Second Stage: Registering Keys

1. Once the signing key for appending entries to the agent’s DeepKey append-only hash chain has been bound to the chain, it provides a clear ordering of events in a peer-to-peer system with no clock authorities.
2. New key registrations can be added under this management umbrella by appending them to DeepKey’s local, append-only hash chain.
3. These keys are used as the keys for signing actions to the append-only hash chains that record local state changes to run/operate other Holochain Applications. (We may later explore extending the functionality of DeepKey to register and manage other keys (e.g. SSL certs, PGP certs, etc.)
4. The content of agent’s hash chains is shared across a graphing DHT for shared visibility of state, and read-only references required for cryptographic validation of actions by other peers on the network/DHT. This allows other applications to reference DeepKey, find the data for a particular agent’s hash chain, and confirm key validity.

### Third Stage: Using and Verifying Keys

1. The most common function call within DeepKey is a check to see if the key of another agent is currently valid (to establish a connection or perform an interaction with someone), or to verify that a key was valid when it performed an action. This is done through `key_state((Key, Timestamp))` passing in the key in question and the relevant timestamp or NOW as the time.
2. Time in distributed systems is normally an extremely complicated issue, however, because there is a single authority appending actions to a hash chain, it is easy to check their chain to know when a key was registered, replaced, or revoked. Theirs is the only clock that matters. Conveniently, the keys being used for actions on that same device, will operate under the same system clock.
3. Holochain prevents significant backdating of actions by ensuring that the timestamps on the append only log can only move forward in time. If someone has been using their device, they can’t modify the system clock to attempt to backdate an action that would precede actions already appended to their hash chain.

### Fourth Stage: Replacing and Revoking Keys / Changing the Rules

1. When replacing or revoking a key that was previously registered, a new entry is appended to the DeepKey chain referencing the prior key registration record, and deleting that key (in the case of revocation) or updating the key record (in the case of rotating or replacing a key).
2. These entries which modify an existing registration must sign the new action with the 1 of 1 revocation key that was set up by default.
3. Any or all network peers can validate the signature(s) confirming the rights to update the key (according to the current management rules).
4. Also, the rules can be replaced by adding a new rules entry to the chain identifying the (N) authorizers and the threshold of how many signatures are required (M). These rules must be validly signed according to the previous management rules.
5. Note: M of N signatures in this case do not involve special multi-sig functions, they are merely an array of signers and signatures.

### Other Complexity: Inviting Other DeepKey Agents into this Management Umbrella/KeySpace

1. Each running instance of DeepKey starts by declaring its own keyset management umbrella, but it can abandon managing its own key space and accept an invitation from another DeepKey instance. This enables multiple devices to be managed together under one unified set of revocation key(s) and management rules.
2. The invitation is signed to the inviting instance’s append only hash chain by the inviter, and the acceptance is signed to the accepting instance’s hash chain. This mutual signing process ensures it can only be done by the people controlling the private keys of each instance, and creates a clear cryptographically signed chain of authority for management of the registered keys.

### TL;DR:

All key management is performed by chaining together a sequence of cryptographic operations. Since _a chain is only as strong as its weakest link_, relying only on cryptographic signing and hashing makes for a much stronger management framework than identity tools which lean on email, text message, or other forms of weak verification of identity to grant control for key management.

## Conclusion

In most digital identity frameworks, if they have key management at all, it is usually not directly controlled by the end user, but rather must be managed through some third party. More so, bindings between a key or claim and a human-friendly name are often totalizing solutions, bound up with the key management process, and thus uncustomizable across domains. By sticking only with cryptography to enable key management, Holochain has nailed down the first corner of Zooko’s Triangle.

We take a similar approach to provide independent integrity for the other two corners. Then we provide some real power and freedom for applications to compose those functional components into appropriate configurations for their use cases.

For greater technical detail as well as visibility into the code, please see [DeepKey’s Github repo](http://github.com/holochain/deepkey/).
