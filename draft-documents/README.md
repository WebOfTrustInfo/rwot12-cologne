# Draft Papers (RWOT12)

This directory contains our RWOT12 papers as they were as we closed out the workshop on September 22. Papers will continue to be updated until they are finally published to the final-documents folder in the coming months.

But take a look at what we've done so far!

## [**Beyond DID:Web**](https://github.com/WebOfTrustInfo/rwot12-cologne/blob/main/draft-documents/beyond-did-web.md)

* Mirko Mollik, Hans Boone, Dan Carez, Jen Schreiber, Dr. Sebastian Schmittner, Dr. Carsten Stoeker

This paper will explore a few recent suggestions for enhancing the did:web method, in particular did:webplus and did:webs. Shortcomings of did:web are analyzed and a list of necessary features to overcome real problems is assembled. We strive to avoid the problem mentioned in the above comic and answer the question, whether the did web method can be improved without creating yet another (few) did methods.

## [**Composing Self-Sovereign Identity for Web3 Applications**](https://github.com/WebOfTrustInfo/rwot12-cologne/blob/main/draft-documents/decent_id_composer_and_threats.md)

* Arthur Brock, Collin McClain

This paper outlines the digital identity tools that Holochain provides. These tools are built to support our ecosystem of applications, giving them important tools for managing identities both within and between application spaces. Beyond that, we are developing standards, gateways, and other tools for connecting to other Web2 and Web3 systems. We believe that these tools could also be used as individual components in other digital identity systems, extending their capacities.

## [**The Ecosystem Coordinator’s role in SSI ecosystem management**](https://github.com/WebOfTrustInfo/rwot12-cologne/blob/main/draft-documents/ecosystem-management.md)

* Christiane Wirrig, PhD

The analysis builds on a draft piece of work from RWOT11 that developed an Enterprise SSI stakeholder map to improve our understanding of which components in an SSI ecosystem need to be engaged to make a technical solution work commercially. The project aims to assess the role of the Ecosystem Coordinator in more detail based on real-world observations. What does an Ecosystem Coordinator need to be and do to make their respective ecosystem work? In which way is a service provider's business model influenced by the nature and operations of the Ecosystem Coordinator? Which barriers and accelerators exist in the ecosystem?

## [**Exchanges through NOSTR for DID Holders**](https://github.com/WebOfTrustInfo/rwot12-cologne/blob/main/draft-documents/Peer_to_peer_credentials_through_NOSTR)

* Imad El Aouny & Frederic Martin

Nostr is a simple, open protocol that enables global, decentralized, and censorship-resistant social media.

This paper explains how two DID holders can securely:

- establish end to end encrypted communication channels
- exchange credentials
- send and receive text messages

## [**Leading with a Different Pitch: Data Portability, Rather Than Privacy**](https://github.com/WebOfTrustInfo/rwot12-cologne/blob/main/draft-documents/a-different-pitch.md)

* Ankur Banerjee & Jack Gretsch

To be clear, this paper is not proposing that self-sovereign identity or its end-goals of improving individuals’ data autonomy and privacy should be abandoned. We celebrate the massive gains the SSI community has won against the current, entrenched models of technology & data. At the same time, the paper explores topics that could pragmatically improve adoption of SSI in the next 1-5 years.

## [**Mind the Gap**](https://github.com/WebOfTrustInfo/rwot12-cologne/blob/main/draft-documents/uncanny-gap.md)

Digital systems wrestle with the same question that mankind always has: "what is truth?" From a philosophical perspective, many acknowledge the limits of what is fundamentally knowable. However, many digital identity advocates pursue the goal of determining one's "true identity" as a precondition for providing services. The issue with this goal is that it conflates what is "true", as in what exists in objective reality, with the perceptions and beliefs of an individual person or system. We call this phenomenon "the uncanny gap": the insurmountable difference between physical reality and its perception, interpretation, or representation in information systems. Instead of trying to close this gap, digital systems should be designed to establish a sense of truth that is good enough for its needs.

## [**Multibit Status List Tradeoffs**](https://github.com/WebOfTrustInfo/rwot12-cologne/blob/main/draft-documents/multibit.md)

* Joe Andrieu & Manu Sporny

Status Lists are used with Verifiable Credentials to provide a privacy-enabling mechanism for revocation and suspension. Used as intended, Verifiers are able to anonymously retrieve and use a Status List to check the currency of a given credential, without revealing to the Issuer which credential is being checked. This approach avoids the "phone home" problem where Verifiers directly communicate with Issuers during verification.

We consider two classes of Status Lists, "Boolean" and "Multivalue" lists and analyze the privacy impact of the differences between the two. Boolean lists expose a single boolean value for each entry in a list, correlating to a single binary entry for each Verifiable Credential whose status is managed by that list. Multivalue lists provide for arbitrary values in each entry with explicit, custom semantics describing the meaning of potential value, thus allowing Credentials whose status check reveals sophisticated knowledge about the credential.

## [**Verifiable Presentation of Composed Credentials**](https://github.com/WebOfTrustInfo/rwot12-cologne/blob/main/draft-documents/verifiable_presentation_of_composed_credentials.md)

* Diana, Fateme, Golda, Ivan, Markus, Sebastian

This paper introduces a novel framework for the presentation of sets of related verifiable credentials that would apply for different purposes; such as infection protection, donation, or education. The framework allows individuals to assemble multiple credentials issued by different issuers and disclose them all together as one claim to stakeholders. By composing credentials together, we can extend the usual pattern of issuer, holder, and verifier. The further challenge is to generate a credible presentation that will be compelling to stakeholders such as regulators, donors, or employers. By bridging the gap between stakeholders and the world of verifiable credentials, we provide a practical and adaptable solution for a wide range of use cases. This holistic exploration of composite credentials demonstrates their potential to address and change the way credentials are presented and verified in a variety of settings.
