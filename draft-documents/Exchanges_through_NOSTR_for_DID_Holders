# Exchanges through NOSTR for DID Holders

**Authors:** Imad El Aouny & Frederic Martin

# **Abstract**:

Nostr is a simple, open protocol that enables global, decentralized, and censorship-resistant social media.

This paper explains how two DID holders can securely :
- establish end to end encrypted communication channels
- request, issue, present and verify credentials
- send and receive text messages
 
We will provide a simple protocol with partial implementation source code  to ensure this seamless and trusted exchanges.

The protocol follows a series of steps to ensure a seamless and trusted exchange through encrypted messages:

**VP Request**: Verifiers initiate a VP request, specifying the type of VC they require, along with an associated challenge. The VP request is sent to the intended holder.

**Holder Preparation**: Holders receive the VP request and gather the necessary information to prepare the VP. They access the relay service URL provided in the request for further processing.

**VP Encryption**: Holders encrypt the VP using the verifier's public key obtained from the Nostr Verifier's public key repository.

**VP Transmission**: The encrypted VP is securely transmitted from the holder to the verifier via the Nostr relay service.

**VP Decryption**: Verifiers retrieve the encrypted VP and decrypt it using their private key, ensuring confidentiality.

**VP Verification**: The decrypted VP is verified using the holder's public key obtained from the Nostr Verifier's public key repository. This step ensures the authenticity and integrity of the VP.
