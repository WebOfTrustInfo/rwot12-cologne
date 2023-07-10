# Nostr Verifiable Presentation Protocol (NVP)

**Authors:**  
Imad El Aouny (myDid) <imad.elaouny@mydid.com>,  
Frederic Martin (myDid) <frederic.martin@mydid.com>

This should become a future NIP (Nostr Implementation Possibilities)  
https://github.com/nostr-protocol/nips

# **Introduction**:

The Nostr Verifiable Presentation Protocol (NVP) is a secure and scalable solution designed to facilitate the exchange of Verifiable Credentials (VCs) and Verifiable Presentations (VPs) within the Nostr ecosystem. NVP leverages the decentralized and censorship-resistant nature of the Nostr platform, ensuring the integrity, privacy, and trustworthiness of the exchanged data.

# **Protocol Overview**:

NVP provides a standardized framework for requesting, generating, and verifying VPs. It enables users to securely present and verify digital credentials, proving their identity and attributes to verifiers in a reliable manner. The protocol follows a series of steps to ensure a seamless and trusted exchange:

**VP Request**: Verifiers initiate a VP request, specifying the type of VC they require, along with an associated challenge. The VP request is sent to the intended holder.

**Holder Preparation**: Holders receive the VP request and gather the necessary information to prepare the VP. They access the relay service URL provided in the request for further processing.

**VP Encryption**: Holders encrypt the VP using the verifier's public key obtained from the Nostr Verifier's public key repository.

**VP Transmission**: The encrypted VP is securely transmitted from the holder to the verifier via the Nostr relay service.

**VP Decryption**: Verifiers retrieve the encrypted VP and decrypt it using their private key, ensuring confidentiality.

**VP Verification**: The decrypted VP is verified using the holder's public key obtained from the Nostr Verifier's public key repository. This step ensures the authenticity and integrity of the VP.

# VP Request Example:
Here's an example of a VP request JSON structure:
```
  {
  "query": [
    {
      "type": "VPRequest"
    }
  ],
  "challenge": "unique-challenge-id",
  "relay": "https://relay.nostr.com/xyz",
  "nosterPubKey": "ECC_PUBLIC_KEY_HERE",
  "context": {
    "type": "msg type",
    "message": "message"
  },
  "proof": {
    "type": "ECDSA",
    "created": "2023-06-26T10:08:27.989Z",
    "proofPurpose": "assertionMethod",
    "verificationMethod": "did:mydid:zeb8iho6uuFKmfWxpG5Sawu1F3wvw7tE8RMzMg567hWWT#ASSR_4",
    "proofValue": "zMbXgtjZ6ZYqzwaP2Sw9E8Koh2ce3KJv2aFF1mEeBPVbJTNZVw7euk8k16WKHkXKp4q71tXzYMFBXyX6a4XYbt2XaJ"
  }
}

```

# **Benefits**:
The Nostr Verifiable Presentation Protocol offers several key benefits:

**Security**: End-to-end encryption and cryptographic verification mechanisms ensure the confidentiality and tamper-proof nature of VPs.

**Decentralization**: NVP leverages the decentralized nature of the Nostr platform, providing resistance to censorship and centralized control.

**Scalability**: The protocol is designed to handle a large number of users, enabling efficient exchange of VCs and VPs at scale.

**Permanent Records**: Nostr maintains a permanent record of VCs, ensuring ongoing accessibility even if VC issuers become unavailable.

**Interoperability**: NVP adheres to open standards, enabling seamless integration with various systems and applications.

# Use Cases:
The NVP protocol is versatile and finds applications in various scenarios, including:

**Identity Verification**: NVP facilitates secure identity verification processes for activities like account openings, employment applications, and rental agreements.

**KYC/AML Compliance**: The protocol assists with Know Your Customer (KYC) and Anti-Money Laundering (AML) compliance, ensuring reliable identity verification.

**Access Control**: NVP can be employed for managing access control to restricted resources, such as buildings or computer systems.

# Conclusion:
The Nostr Verifiable Presentation Protocol (NVP) empowers the Nostr ecosystem with a robust and secure framework for exchanging VCs and VPs. By leveraging decentralized principles and cryptographic techniques, NVP establishes trust, privacy, and reliability in the exchange of verifiable credentials. The protocol opens doors to a wide range of applications, driving seamless identity verification and secure data exchange within the Nostr platform.