# Peer to peer credentials through NOSTR 

**Authors:** Imad El Aouny & Frederic Martin

# **Abstract**:

Nostr is a simple, open protocol that enables global, decentralized, and censorship-resistant social media.

This paper explains how DID holders can securely :
- establish end to end encrypted communication channels
- send and receive credentials
- publicly expose selected credentials in a public profile
- ask for a specific verifiable presentation of a public profile

We'll illustrate this article with real-life examples :
- as a student, you want to send a soft skill credential to another student
- as a volonteer want to obtain a proof of involvement from a certified organizer
- you want to select these two credentials to publicly show 

This can be extended to text messages exchanges but out of scope here. 

# **Peer to peer credentials**:

Peer to peer Credentials use cases are often neglected and understimated but will probably be the most numerous verifiable credentials in the end, as people will use them to build their e-reputation and public profile with recommandations from their friends/collegues and certifications of their communities.

Note: Peer to peer recommandations can be mixed with more traditionnal vertical credentials : you can recommend another peer as someone with a standard credential   (cf OB V3 endorsement)

# **Why peer to peer messaging**:

Standard and more vertical Credentials are usually linked to centralized endpoints and platforms to request, obtain and show these credentials.

When you build solution for people to be able to communicate on a more horizontal level and exchange peer to peer credentials, you can be tempted to leave this charge to end-users who will need to send credentials through email or other personal accounts on existing instant messaging services. This is usually a bad idea for many reasons : breaking user experience inside your application/service, adding correlation of different identities, opening new communication channels that could be abused in the future (spam, attacks...).

We did not want to involve DIDCOMM specification here (even if transport layer agnostic) because we'd like something more optimized to this special use case and we did not want to use cryptographic keys related to DID for the encryption (and we wanted to easily create numerous one to one droppable encrypted channels)
 
That's where small neutral messaging services like Nostr can be usefull.
Nostr servers are getting a lots of attention and innovation, are freely available in many places and you can easily create your own public or private server. 

# **why NOSTR: messaging protocol based on public relays**:

A quick reminder about what Nostr can and can not do.

NOSTR means Notes and Other Stuff Transmitted by Relays.
It is a simple protocol to exchange messages between clients / users using the same relay.

## Nostr basics:

Nostr is based on two components: clients & relays (servers). 
- Each user runs a client. 
- Anyone can run a relay.
- Relays don't talk to one another, only directly to users.
- Clients fetch data from relays of their choice and publish data to relays of their choice.
- Every post is signed. Every client validates these signatures.

Every user is identified by at least a public key but you need to know the relay server where this key is used. 

In the end, Nostr users can be contacted through their "Nostr Public ID" (a ECC public key) on the relay servers of their choice.

## Nostr constraints:

By default, all messages are public and old relayed messages are stored and available.

**To assure deletion of messages:**

You must use NOSTR servers (like nostr-rs-relay [1]) with the common "NIP-09 Event Deletion" feature [2]. 

Deletion support inside relays is mandatory for evident privacy reason and for GDPR compliance

**To assure privacy:**

We propose here to use ECIES encryption.
An even better solution (with Resilience, Forward security and Break-in recovery) will be to implement double Double Ratchet Algorithm [3]

"NIP-04 Encrypted Direct Message" feature could be used too.  

**To limit metadata analysis and corellation:**

We propose here to use unique channels between actors, meaning that each side create a nostr ID dedicated to the communication.

Actors can take profit of NIP06 to derivate several Nostr IDs' keys from a BIP39 seed [4]

*TBD: insert "spaghetti diagram" for 1 to 1 channels illustration*

real start : scan QRcode or click link that trigger the DID wallet that will use nostr as a communication channel

# Communication

*TBD: introduce following steps*

## 1 Creating a Unique Channel for VC Exchange

### Public NostrID
Each user has a public NostrID, a kind of unique identifier on the Nostr platform.

### Initiating the Contact Request
To create a unique communication channel, the initiating user (the sender) uses their public NostrID to send a contact request. This request can contain the following information:

- NostrID for the new channel: A unique identifier for the new channel that both parties will create.
- DID (Decentralized Identifier): Another form of decentralized digital identifier.
- MSG (Message): Personal information, VCs, or other necessary data for the exchange.
- Proof using DID: To enhance the authenticity of the request.

**ContactRequest data**

```
{
  "type": "ContactRequest",
  "message": {
    "text": "Salut, créons un canal sécurisé pour échanger des verifiable credentials.",
    "verifiableCredentials": [
      {
        VC
      }
    ]
  },
  "proof": {
    "type": "ECDSA",
    "created": "2023-09-20T14:30:00Z",
    "proofPurpose": "contactInitiation",
    "verificationMethod": "did:user:example_did#contactProof_1",
    "proofValue": "proof_value_here"
  }
}

``` 
### Request Encryption
The request's information is encrypted using ECIES (Elliptic Curve Integrated Encryption Scheme) based on the public NostrID. This encrypted request is then sent via the "NostrID for the new channel."

**Enveloped Request**
```
{
  "envelope": {
    "encryption": {
      "algorithm": "ECIES"
    },
    "data": {
    
    << ENCRYPTED ContactRequest data >>
      
    }
  }
}

```

### Signed Event
The encrypted contact request is encapsulated in an event signed by the "NostrID for the new channel." This ensures the integrity of the request during transit.

```
{
  "id": <32-bytes lowercase hex-encoded sha256 of the serialized event data>,
  "pubkey": NostrID for the new channel,
  "created_at": <unix timestamp in seconds>,
  "kind": 420,
  "tags": [
        ["p", "public NostrID"],
    ...
  ],
  "content": <Enveloped Request>,
  "sig": <64-bytes lowercase hex of the signature of the sha256 hash of the serialized event data, which is the same as the "id" field>
}
```

## Reception, Acceptance
The person receiving this contact request can accept it by sending similar information, including the "NostrID for the new channel" and the DID. Additional messages can be included as needed.


Once both parties have exchanged their information, they can start using the "NostrID for the new channel" to securely send requests, VCs, VPs, and other data.

## 2 Simple example : Sending VC

**VC**
```
{
  "@context": [
    "https://www.w3.org/2018/credentials/v1",
    "https://www.example.com/contexts/custom-vcs-v1.jsonld"
  ],
  "id": "urn:uuid:eb6c0b6e-4e3a-4c78-af24-9337ea7a4c27",
  "type": ["VerifiableCredential", "StudentCredential"],
  "issuer": "did:university:issuer_id",
  "issuanceDate": "2023-09-21T12:00:00Z",
  "expirationDate": "2024-12-31T23:59:59Z",
  "credentialSubject": {
    "id": "did:user:example_did",
    "name": "John Doe",
    "studentID": "12345",
    "university": "Example University"
  },
  "proof": {
    "type": "Ed25519Signature2018",
    "created": "2023-09-21T12:00:00Z",
    "proofPurpose": "assertionMethod",
    "verificationMethod": "did:university:issuer_id#key-1",
    "jws": "eyJhbGciOiJFZERTQSJ9..."
  }
}
```

**enveloped VC**

```
{
  "envelope": {
    "encryption": {
      "algorithm": "AES"
    },
    "data": {
    << ENCRYPTED VC >>
  }
}

```

### Signed Event containing VC
The encrypted VC is encapsulated inside an event signed by the "NostrID for the new channel." This ensures the integrity of the request during transit.

```
{
  "id": <32-bytes lowercase hex-encoded sha256 of the serialized event data>,
  "pubkey": NostrID for the new channel,
  "created_at": <unix timestamp in seconds>,
  "kind": 420,
  "tags": [
        ["p", "public NostrID"],
    ...
  ],
  "content": <Enveloped Request>,
  "sig": <64-bytes lowercase hex of the signature of the sha256 hash of the serialized event data, which is the same as the "id" field>
}
```

## 3 More complex example with VP request  

```
{
  "type": "VPRequest",
  "query": [
    {
      "vcType": "StudentCredential",
      "issuer": "did:university:issuer_id"
    }
  ],
  "challenge": "unique-challenge-id",
  "relay": "https://relay.nostr.com/api/v1/auth/vp",
  "endorsements": [
    {
      "type": "VerifiableCredential",
      "issuer": "did:teacher:teacher_did",
      "claim": {
        "teacherStatus": true,
        "name": "Professor John Doe"
      },
      "proof": {
        "type": "ECDSA",
        "created": "2023-06-26T10:08:27.989Z",
        "proofPurpose": "teacherAssertion",
        "verificationMethod": "did:teacher:teacher_did#TeacherProof_1",
        "proofValue": "Proof_Value_Here"
      }
    }
  ],
  "proof": {
    "type": "ECDSA",
    "created": "2023-06-26T10:08:27.989Z",
    "proofPurpose": "assertionMethod",
    "verificationMethod": "did:professor:prof_did#ASSR_4",
    "proofValue": "zMbXgtjZ6ZYqzwaP2Sw9E8Koh2ce3KJv2aFF1mEeBPVbJTNZVw7euk8k16WKHkXKp4q71tXzYMFBXyX6a4XYbt2XaJ"
  }
}

```


---

[1] https://git.sr.ht/~gheartsfield/nostr-rs-relay
[2] https://github.com/nostr-protocol/nips/blob/master/09.md
[3] https://signal.org/docs/specifications/doubleratchet/
[4] https://github.com/nostr-protocol/nips/blob/master/06.md
