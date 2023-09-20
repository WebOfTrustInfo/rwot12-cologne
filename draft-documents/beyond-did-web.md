# Beyond did:web

## Abstract


![](https://imgs.xkcd.com/comics/standards.png)

This paper will explore enhancing the did:web method, compare existing did:web like/enhancing methods (such as did:webplus and did:webS), and propose solutions to elevate its functionality and security. We also aim to provide a phased roadmap for the development of a secure did:web* method, if needed.


To begin, we will evaluate the current did:web specification. We will use our shared experiences implementing did:web and published articles to create an exhaustive list of the feature set and known gaps or security implications. Understanding business requirements and use cases is important. This paper explains the practical applications and  of businesses needs that did:web aims to fill. A detailed discussion on the features of did:web is presented, drawing from experiences with existing working code and real-world applications.


Additionally, we explore other did:methods that might operate under different names but offer similar functionalities, particularly those that resolve via DNS and incorporate key rotation features. Our focus remains on non-DLT based approaches, ensuring a broader applicability. We also dive into the related standardization activities undertaken by Trust over IP (ToIP) and IETF, highlighting their contributions and guidelines that shape the future of did:web.


Lastly, if needed, we hope to provide a cursory feature set to make the new did:web* the best it can be!


## Introduction

Why are we writing this paper?
- free food

Brief overview of the did:web method and its significance.
Background and Current State


## Why are organizations using did:web?

As organizations navigate the evolving landscape of identity management, decentralized identifiers (DIDs) are emerging as a promising solution to enhance security, privacy, and user control. Among the various DID methods available, 'did:web' serves as a practical starting point for those venturing into this decentralized realm. Easy to implement and compatible with existing web infrastructure, 'did:web' enables organizations to familiarize themselves with the core concepts of decentralized identities before diving into more complex and specialized DID methods. Below, we explore the key advantages of starting with 'did:web'.

**Ease of Use**: 'did:web' is often considered simpler to understand and implement. It operates over standard HTTPS protocols and can be easily managed with familiar, widely available and cheap web server technology.

**No Specialized Infrastructure**: Unlike some other DID methods that require special nodes or decentralized networks, 'did:web' works on existing web infrastructure.

**Low Cost**: Unlike ledger based did methods, 'did:web' does not have an associated cost other than maintaining a web server.

**Interoperability**: 'did:web' identifiers can be easily mapped to existing HTTPS URLs, making it straightforward to integrate with current web architectures.



## Feature requests: What is did:web lacking

Attacks/Failure scenarios

### Recover a did if the private key has gone bad

In case a private key gets
- lost, i.e. is no longer available to the legitimate owner but likely also not to anybody else
- compromised, i.e. accessible by an unauthorized actor
- out dated, e.g. because the key length or, more generally, the algorythem used are no longer considered secure enough

a did needs to be associated with a new key pair. Such that

- Signatures by the did before the private key went bad remain valid
- Signatures by the did's bad key after it went bad are to be considered invalid
- The did can still signe (with a new key)

This applies in particular for VCs issued by the did, but also to e.g. presentations signed by the did.


### Add/change/delete a service endpoint to a did document

Service endpoints provided by a did might change over time, hence a typical did document update not related to cryptografic material is changing the list of published service endpoints


### Practical business applications and feature requirements of businesses in relation to did:web.


### DID:web auditability 
**Carsten**
Potential benefits and challenges of integrating GIT with did:web.
Enhancing Security in did:web


## Solving Problems
*Dan, *Sebastian**
Proposed solutions and methods to enhance security.
Recommendations and Roadmap


### Key Rotation

When [the private key of a did becomes unusable](#Private-Key-gone-bad), the did document needs to be updated to publish a new public key. In order to fulfill the [requirements listed above](#Private-Key-gone-bad), the old private key must still be accessible, but it must be made clear signatures from which time period are still to be considered valid and from where they are to be considered invalid.

Having a version history of keys inside a did document with published validity intervals is a perfectly valid solution to this problem and could be achieved by simply adding `valid-from` and `valid-until` time stamps to the did documents verification methods. (See [did core specification of verification methods](https://www.w3.org/TR/did-core/#verification-methods))

However, since key rotation is only one reason to change a did document, we conclude that rather than coming up with a way to only having a version history of keys, we would rather have [versioned did documents](#Did-Document-Versioning).

### Did Document Versioning

The best:tm: approach to versioning is what is nowadays known as a "micro ledger", i.e. hash linked data blocks which would also be the data structure in a block chain.

- did:webs uses KERI to have this micro ledger in form of an event log.
- did:web2.0 has the backward links as resolvable did URIs, including the hash (id), directly in the did document in a new `"previous"` field.


## Comparison of what Jen thinks are worthy did methods

**Jen**

Challenges and limitations.
Comparative Analysis of Existing Methods

Insert Content from
https://hackmd.io/@piafdZMCQwuxBfxK92zZhA/BJViZQuya/edit



## Compatibility of did:webXX wth did:web

**Mirko**

### did:webs

from https://trustoverip.github.io/tswg-did-method-webs-specification/ :
> The did:web version of the DIDs are the same (minus the s) and point to the same did.json file, but have no knowledge of the did.keri file.

### did:webplus
### did:web2.0
- uses a new verification relationship "recover"
- self cerififying is covered via the hash value, instead of using the [hashlink](https://www.w3.org/TR/did-core/#content-integrity-protection)
- new field to point to the previous field. This feature seems not to be relevant for an case (personal opinion)

Why are there new did methods?

how can we just improve did:web without making a new did method?
- the deletion/deactivation method of the current did:web forces you to delete the did.json file. In case the user only wants to deactivate the key, but still allow the public key to be available for signature verification, the deactivate status has to be requested via the documented metadata. The did core specification is [mentioning](https://www.w3.org/TR/did-core/#did-document-metadata) that when a did document is revoked, the `revoked` value in the document metadata should be set to `true`. This can only be achived when the `did.json` file is served dynamically, otherwhise we are not able to fetch the metadata.



## Results from testing DID:webplus working Rust codebase


## Concrete suggestions for the evolution of did:web.
A phased plan detailing short-term and long-term goals.
Conclusion

## Reiteration of the importance of evolving did:web.
Future prospects and the potential impact on the decentralized identity landscape.
References


## References

