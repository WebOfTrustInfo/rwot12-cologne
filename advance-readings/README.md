# Advance Readings

In advance of the design workshop, all participants produced a
one-or-two page advance reading to be shared with the other attendees
on either:

- A specific problem that they wanted to solve with a web-of-trust solution, and why current solutions (PGP or CA-based PKI) can't address the problem?
- A specific solution related to the web-of-trust that you'd like others to use or contribute to?

If you will be attending Rebooting the Web of Trust September 2023 in Cologne, please upload your advance readings to this directory with a
pull request.

## Pull Request Submission

To add a paper, create a pull request to this repo with your
contribution (preferably as an .md file, but if you can't, as a PDF),
along with updates to the README.md in this folder. Please also
include a byline with contact information in the paper itself.

Please also enter your paper _twice_ in this README file, once in the
topical listing (adding a new category describing your topic, if
necessary) and one in the alphabetical listing. Please be sure to
include the full URL for your paper in the README, so that we can copy
it to the main page URL and have it still correctly link.

If you don't know how to submit a pull request, please instead submit an issue.

## Request RWOT12 discount code

To those who have submitted an Advance Readings paper, RWOT12 offers a
steep discount on the ticket price for participation to the
event. Please obtain your discount code as follows.

- Copy the link to your Pull Request (see previous section)
- Email to [questions@weboftrust.info](mailto:questions@weboftrust.info), paste the link to the Pull Request and ask for the discount code

Please make sure to make your Pull Request Submission BEFORE you buy
the tickets for RWOT12, in order to apply your discount code.

## Primer Listing

These primers overview major topics which are likely to be discussed
at the design workshop. If you read nothing else, read these. (But
really, read as much as you can!)

* [Advance Reading Primer](./advance-reading-primer.md) — About the advance reading papers
* [RWOT Primer](./rwot-primer.md) — How the design workshop works
* [DID Primer](./did-primer.md) — Decentralized Identifiers ([extended version](./did-primer-extended.md) also available)
* [Functional Identity Primer](./functional-identity-primer.md) — A different way to look at identity
* [Verifiable Credentials Primer](./verifiable-credentials-primer.md) — the project formerly known as Verifiable Claims
* [Glossary of Terms](./glossary-primer.md) — a brief dictionary of technical terms used at RWOT

## Topical Listing

_Please add a level three header (`###`) for your paper's topic if it's not there already, then link it in the form:_

```
[name](link)
   * by [author](mailto:if desired)
   * One to two sentence synopsis or quote
   * #hashtags for topics
```
### Certificates

[Verifiable Credentials for Company Identification using eIDAS Qualified Seal Certificates](./company-identification-with-qseal-certs.md)
   * by Hans Boone
   * proposal to bootstrap company identity by using qualified seal certificates.
   * #qseal #eidas #ODI #vc

### Decentralized Platforms

[MyEduLife](https://github.com/FatemeFathii/MyEduLife/blob/main/advance-readings/MyEduLife.md)
* by [Fatemeh Fathi](Fathi@dbis.rwth-Aachen.de), [Björn Adelberg](bjoern.adelberg@tu-dresden.de), and [Philipp Zagle](philipp.zagler@th-luebeck.de)
* A tool for decentralized storage of individual continuing education biographies
* #self-sovereign-identity #digital-identity #education #skills #distributed-ledger

[Verifiable Credentials on the Ceramic Network](https://github.com/gvelez17/rwot12-cologne/blob/feat/add-advance-reading-for-vcs-over-ceramic/advance-readings/CeramicVerifiableCredentials.md)
   * by Golda Velez
   * A proposal for native storage and retrieval of verifiable credentials on the Ceramic Network
   * #verifiable-credentials #decentralization #ceramic #composedb #shared-data-layer

### DIDs

[DIDs and Nostr &mdash; Key Management and More](./dids-and-nostr-key-management-and-more.md)

- by [Stevan Eraković](mailto:stevan.erakovic@danubetech.com)
- How DIDs can bring easy key management and more to Nostr
- #nostr #dids #decentralized-identity #freedom-of-speech
  
### DIDComm

[A path towards forward secrecy in DIDComm](/advance-readings/didcomm-forward-secrecy.md)
   * by Dan Carez
   * A proposal to achieve forward secrecy and post-compromise security via the integration of ratcheted key exchanges in DIDComm.
   * #didcomm #forward-secrecy #post-compromise-security #ratcheted-key-exchange

### Explain It Like I'm Five

[Explain it Like I'm Five](./Explain-it-Like-I'm-Five.pdf)

- By Jack Gretsch
- Context for those unfamiliar with the subject
- #wikipedia #selfsovereignidentity #decentralizedidentifiers


### Formal Modeling

[A basic conceptual model for verifiable identity](./VerifiableIdentityModel.pdf)

- by l. boldrin
- sketch of a formal model for verifiable identity
- #identity #model

### IoT (Internet of Things)

* [Decentralized Identity and Access Control Management in Forestry 4.0](diam-forestry-4.0.md)
   * by Yongli Mou
   * In the forestry sector, the application of Industry 4.0-compliant concepts, known as Forestry 4.0, holds the promise of revolutionizing forest management and conservation by offering IoT-based capabilities to monitor and manage forest resources.
   * #self-sovereign-identity #access control management #IoT #smart Forestry

### Nostr

[DIDs and Nostr &mdash; Key Management and More](./dids-and-nostr-key-management-and-more.md)

- by [Stevan Eraković](mailto:stevan.erakovic@danubetech.com)
- How DIDs can bring easy key management and more to Nostr
- #nostr #dids #decentralized-identity #freedom-of-speech

[Nostr Verifiable Presentation Protocol](./NostrVP.md)  
  * by [Imad El Aouny](mailto:imad.elaouny@mydid.com), [Frederic Martin](mailto:frederic.martin@mydid.com)  
  * Exchanging Verifiable Credentials (VCs) and Verifiable Presentations (VPs) within the Nostr ecosystem  
  * #did #vc #verifiablecredentials #vp #verifiablepresentations #nostr

### Privacy

[Sustainable Privacy, Authenticity, and Confidentiality](sustainableprivacy.md)
   * by Samuel M. Smith Ph.D.
   * In the SPAC whitepaper, a protocol is described using best practices with readily available cryptographic operations to provide secure privacy, authenticity, and confidentiality. The protocol provides a foundation for best practices for what we are calling sustainable privacy.
   * #spac #privacy #authenticity #confidentiality

### Self-Sovereign Identity

* [Decentralized Identity and Access Control Management in Forestry 4.0](diam-forestry-4.0.md)
   * by Yongli Mou
   * Forestry 4.0, given its intrinsically decentralized and diverse framework involving multiple stakeholders and technologies, necessitates a decentralized IAM solution. This study delves into the potential application of self-sovereign identity as a viable solution to optimize access control management in Forestry 4.0 systems, thereby bolstering overall security and operational efficiency.
   * #self-sovereign-identity #access control management #IoT #smart forestry

* [Echoes from History: Designing Self-Sovereign Identity with Care](./ssi-echoes-from-history.md)
   * by Christopher Allen
   * Self-sovereign identity represents an innovative new architecture for identity management. But, we must ensure that it avoids the pitfalls of previous identity systems. During World War II, two identity pioneers, the Dutch Jacobus L. Lentz and the French René Carmille, took different approaches toward the collection and recording of personally identifiable data. As a result, 75% of Dutch Jews fell victim to the Holocaust versus 23% of the Jews in France. Our foundational work on self-sovereign identity today could have similar repercussions down the road, so it’s imperative that we design this foundation responsibly with diligence and foresight
   * #self-sovereign-identity #history #data-minimization #selective-disclosure

### Verifiable Credentials

[Decentralized Identity and Verifiable Claims for the Arts and Artists](identity-vcs-arts-artists.md)

- by Gaya Blair Pendleton, Valerie Brusola, Markus Willms, and Moses Ma
- Articulating the principles and key design considerations for a use case for DIDs and VCs in the world of fine arts involving both physical and digital collectibles
- #did #vc #verifiablecredentials #nft #art #provenance

[Nostr Verifiable Presentation Protocol](./NostrVP.md)  
  * by [Imad El Aouny](mailto:imad.elaouny@mydid.com), [Frederic Martin](mailto:frederic.martin@mydid.com)  
  * Exchanging Verifiable Credentials (VCs) and Verifiable Presentations (VPs) within the Nostr ecosystem  
  * #did #vc #verifiablecredentials #vp #verifiablepresentations #nostr

[Requirements towards Verifiable Credentials arising from Administrative Acts](credentials-in-administrative-acts.md)
   * by  Markus Batz (markus.batz@stadt-koeln.de), Dr. Sebastian Zickau (Sebastian.zickau@stadt-koeln.de)  
   *  Verifiable Credential are supposed to be used in administrative procedures on federal, regional, and municipal level. The Intention is to replace paper-based credentials to drive digitalization whilst implementing self-sovereign identity principals, especially increasing decentralization and user privacy. On the one hand several verifiable credential formats exist covering a set of features, where some features are common to all formats and some features are specific. Administrative acts on the other hand bring in certain requirements, which determine the relevance of these features for the respective administrative act.  It is of interest whether certain pattern exists within these requirements fulfilled by certain features which allow to determine suitable or favorable verifiable credential formats for administrative acts.
   * verifiablecredentials #federal #municipal #administration

[Trust in Verifiable Digital Product Passport](./verifiable-product-passport.md)

- by [Christian Fries](mailto:christian.fries@eecc.de)
- Using verifiable credentials to transform the digital product passport into a verifiable digital product passport
- #vc #verifiablecredentials #dpp

[The Monetization of Verifiable Credential Issuer Verification](./monetization-of-vc-issuer-verification.md)
  * by Jen Schreiber
  * An exploration of how the monetization of Verifiable Credential Issuer verification will impact the integrity and trust networks within the SSI ecosystem
  * #trust #verifiablecredentials #issuers #verification

[Verifiable Credential Resolver (VCR) for supply chains](./verifiable-credential-resolver-for-supply-chains.md)

- by [Mirko Mollik](mailto:mirkomollik@gmail.com)
- Resoling the endpoint to request VCs from a product having a DID
- #did #vc #verifiablecredentials #supplychain #dpp

[Designing Verifiable Computation Presentations](./verifiable-computation-presentations.md)

- by [Abhishek Mahadevan Raju](mailto:abhishek_mahadevan.raju@tno.nl) (TNO)
- Incorporating Proof of Operation/Computation into Verifiable Presentations to facilitate scenarios requiring compelling evidence of completed computations, while potentially also maintaining privacy.
- #vc #verifiablecredentials #verifiablepresentations #verifiablecomputations #zkp #bbs
  

  
## Alphabetical Listing

_Please also enter your paper alphabetically in the form:_

```
* [Paper Name](link)
```
* [A basic conceptual model for verifiable identity](./VerifiableIdentityModel.pdf)
* [A path towards forward secrecy in DIDComm](/advance-readings/didcomm-forward-secrecy.md)
* [Decentralized Identity and Access Control Management in Forestry 4.0](diam-forestry-4.0.md)
* [Decentralized Identity and Verifiable Claims for the Arts and Artists](identity-vcs-arts-artists.md)
* [Designing Verifiable Computation Presentations](./verifiable-computation-presentations.md)
* [DIDs and Nostr &mdash; Key Management and More](./dids-and-nostr-key-management-and-more.md)
* [Echoes from History: Designing Self-Sovereign Identity with Care](./ssi-echoes-from-history.md)
* [Explain it Like I'm Five](./Explain-it-Like-I'm-Five.pdf)
* [The Monetization of Verifiable Credential Issuer Verification](./monetization-of-vc-issuer-verification.md)
* [MyEduLife](https://github.com/FatemeFathii/MyEduLife/blob/main/advance-readings/MyEduLife.md)
* [Nostr Verifiable Presentation Protocol](./NostrVP.md)
* [Requirements towards Verifiable Credentials arising from Administrative Acts](credentials-in-administrative-acts.md)
* [Sustainable Privacy, Authenticity, and Confidentiality](sustainableprivacy.md)
* [Trust in Verifiable Digital Product Passports](./verifiable-product-passport.md)
* [Verifiable Credential Resolver (VCR) for supply chains](./verifiable-credential-resolver-for-supply-chains.md)
* [Verifiable Credentials for Company Identification using eIDAS Qualified Seal Certificates](./company-identification-with-qseal-certs.md)
* [Verifiable Credentials over the Ceramic Network](./CeramicVerifiableCredentials.md)
