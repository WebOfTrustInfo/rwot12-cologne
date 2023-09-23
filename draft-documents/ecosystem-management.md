# The Ecosystem Coordinator’s role in SSI ecosystem management
Christiane Wirrig, PhD - [Spherity](https://www.spherity.com/), [Blue Steens](https://www.blue-steens.com/) 

# Abstract
Coming at this project from the perspective of an identity wallet provider working to establish a financially sustainable business, the core question is, "Why is it so hard?" 

The analysis builds on a draft piece of work from RWOT11 that developed an [Enterprise SSI stakeholder map](https://github.com/WebOfTrustInfo/rwot11-the-hague/blob/master/draft-documents/ssi-stakeholder-mapping.md) to improve our understanding of which components in an SSI ecosystem need to be engaged to make a technical solution work commercially. The project aims to assess the role of the Ecosystem Coordinator in more detail based on real-world observations. What does an Ecosystem Coordinator need to be and do to make their respective ecosystem work? In which way is a service provider's business model influenced by the nature and operations of the Ecosystem Coordinator? Which barriers and accelerators exist in the ecosystem?

# Introduction
Carsten Stöcker’s “5 Critical Success Factors” for blockchain-based solutions highlight the importance of developing a complete ecosystem to drive adoption and collaboration (Brumnik, 2023). This involves gaining the support for the business case from all relevant stakeholders. An indispensable foundation stone is the development and monitoring of a trust framework. A key question is, “Who takes care of all this?”

Based on work performed at RWOT11, an entity called the *Ecosystem Coordinator* (Boone & Wirrig, 2022) seems well-placed to take such a leadership role. This paper aims to deliver a brief assessment of real-world self-sovereign identity (SSI) ecosystem coordinators, their influence on stakeholders and, ultimately, on commercial viability.

I distinguish between *established* and *emerging* Ecosystem Coordinators. The former has existed within their ecosystem already before the discovery of the specific SSI use case; whereas the SSI use case was the reason for the birth of the latter.

# Established Ecosystem Coordinator

## Prior research
Lacity et al. (2023) have analysed three different SSI ecosystems and concluded that starting with the issuer fast-tracks adoption. Looking at those case studies in more detail, it turns out that the issuers also appeared to be the Ecosystem Coordinators. Thanks to their central roles within their respective ecosystems, these issuing entities also concerted all efforts, such as defining the scope of the use case, pulling in more actors, educating, etc. These coordinators were also well-established bodies, namely NHS England, Bonifii and the province of British Columbia, that had a good overview of and handle on the envisaged initial ecosystem membership already at the outset of their projects. As the authors said, it made sense for those entities to lead the pilots. 

## NACS ecosystem - US convenience stores
The [National Association of Convenience Stores (NACS)](https://www.convenience.org/) is a trade association for convenience and fuel retailing stores. There are nearly 150,000 convenience stores operating in the United States (NACS, 2022) that perform dozens of age checks every day to sell alcohol or other age-restricted items. As Ecosystem Coordinator NACS has been fundamental in driving the development of a W3C verifiable credential-based (W3C, 2022) tool for the facilitation of age checks leveraging people’s driver’s licences and any participating point-of-sale and payment system ([TruAge](https://www.mytruage.org/); Businesswire, 2021). 

However, NACS itself is not the credential issuer; TruAge is. TruAge offers the issuance and verification service and has been set up as a not-for-profit entity that is funded by the manufacturers of age-restricted products. Originally, system development was funded by NACS membership fees and TruAge sponsors.  TruAge is well positioned to take over as Ecosystem Coordinator, as it connects its technical integrators, manufacturers, retailers and consumers, whereas NACS focuses on retailer interests.

In principle, the reliance on open standards enables technical interoperability and, thus, allows any digital SSI wallet provider, issuer or point-of-sale vendor to enter this ecosystem.

# Emerging Ecosystem Coordinator
What if the use case does not provide a tight initial ecosystem with an already existing, strong coordinator?

## OCI ecosystem - US pharmaceutical supply chain
The Open Credentialing Initiative ([OCI](https://www.oc-i.org/)) was born out of a pilot involving a handful of key stakeholders in an ecosystem that had yet to be clearly defined. The first use case focused on a niche problem, i.e. proving so-called Authorized Trading Partner status in electronic pharmaceutical product-related enquiries between supply chain partners. The driver behind this pilot was a new U.S. law called the Drug Supply Chain Security Act ([DSCSA](https://www.fda.gov/drugs/drug-supply-chain-integrity/drug-supply-chain-security-act-dscsa)).

Realising that a central entity was needed to refine and standardise the successfully piloted solution approach, provide a safe space for members to interact and drive industry adoption, some of the pilot participants came together to found OCI in April 2021 (Wirrig, 2022). The consortium’s network of members and supporters has grown since and developed an [*Interoperability Profile*](https://www.oc-i.org/interoperability-profile), basically a set of shared conformance standards. 

OCI obtains funding to finance its essential operations from sponsors, while membership is free. However, members participate as volunteers in OCI’s meetings and activities. Despite the active involvement of commercial solution providers, OCI aims to remain neutral and presents itself as a hub for any interested supply chain participants, including trade organisations and relevant standard setters. OCI conformance requirements allow for a degree of divergence between solution providers, e.g. two different DID methods (OCI, 2023), to enable competition, but also strive to provide sufficient prescription to keep those services compatible with each other. These architectural choices are there to prevent vendor lock-ins and enable commercial competition in other aspects of service offerings. As part of its coordinating role in support of adoption and service interoperability, OCI lists those providers that have attested compliance with its conformance criteria.

## IDunion ecosystem - European Schaufenster
Back in 2019/20 the German [Federal Ministry for Economic Affairs and Climate Action](https://www.bmwk.de/Navigation/DE/Home/home.html) ran a selection program to find three to four SSI “Schaufenster” projects to fund for up to three years. The ideal desired outcome was a system that enabled technological interoperability between all funded projects. 

[IDunion](https://idunion.org/?lang=en) was one of the grant winners. Since then IDunion has grown into arguably the biggest of the four projects based on membership, which includes various companies, associations and other national organisations. In its role as Ecosystem Coordinator, IDunion’s goal from the start was to create an industry network. Eventually in July 2022, the research project spun off a separate legal entity called a *Sociedad Cooperativa Europea* (SCE), a European cooperative with limited liability. The IDunion SCE is to survive the limited grant funding period and manage the technical operations under its umbrella.

IDunion’s original funding came from the German government grant and is supplemented by membership fees. The ultimate goal is to sustain the organisation through revenue from provided services, e.g. infrastructure provision.

Over time IDunion has covered a variety of potential use cases stimulated by its members, for example, banks were interested in KYC, supplier onboarding and enterprise identity was driven by large manufacturers. In technological terms, IDunion has always aimed to avoid vendor lock-ins and expanded on prior work, which gave it a practical head-start ahead of the other Schaufenster projects. However, while architectural expectations within IDunion have always been clear to Schaufenster participants and interested close parties, IDunion has never formally committed to its own shared conformance criteria to prevent premature self-imposed restrictions in an uncertain environment. Technological interoperability of participants is determined by their developments to work within the confines of the existing IDunion tech stack. That said, individuals from within IDunion have contributed to the creation of open standards, such as [OpenID for VC](https://openid.net/sg/openid4vc/), SD-JWT (IETF, 2023) and Status List 2021 (W3C, 2023). At the moment IDunion is facing the decisive challenge of navigating future compliance with the upcoming European Digital Identity Architecture and Reference Framework (European Commission, 2022) and [eIDAS](https://digital-strategy.ec.europa.eu/en/policies/eidas-regulation) 2.0.
## mDL ecosystem - US driver licences
The mobile driver licence (mDL) may be seen as a controversial example in this SSI-focused assessment, as it does not go along with W3C’s VC Data Model (W3C, 2022). However, it has been argued that mDL’s approach and SSI show a degree of overlap despite concerns around privacy, key control and vendor tie-in within mDL’s design (INATBA, 2023).

The reason for its inclusion here is that it is a project leveraging digital identifiers that has made a lot of waves in the media, has seen big tech in the lead and found institutional support. Thus, it is more advanced than many other digital identity projects, especially those that are in pre-adoption or pre-commercial stages.

[AAMVA](https://www.aamva.org/jurisdiction-data-maps#anchorformdlmap) and the [Secure Technology Alliance (STA)](https://www.mdlconnection.com/implementation-tracker-map/) track the adoption in maps showing that several US states have accomplished or are heading for interoperable implementation; others are in earlier stages of legislative or study activity. Interestingly both maps don’t seem to agree fully. To drive adoption, California’s DMV, for example, has launched a public pilot to engage everyday users [DMV CA](https://www.dmv.ca.gov/portal/ca-dmv-wallet/).

To arrive at a common worldwide standard, the ISO/IEC 18013 series (refer to [section 35.240.15](https://www.iso.org/ics/35.240.15/x/)) was created to describe the various requirements that ultimately enable the implementation and interoperability of a driving licence on a mobile device. The US Department of Homeland Security has enshrined ISO/IEC 18013–5 (ISO, 2021) in a Proposed Rule (DHS, 2021). Part 5 of the standard was further expanded by separate guidance issued by the American Association of Motor Vehicle Administrators (AAMVA) for use by US Departments of Motor Vehicles (DMVs) (AAMVA, 2022). [NIST](https://www.nccoe.nist.gov/projects/digital-identities-mdl) has launched a project looking to dive deeper into the requirements and claims of the standards ISO/IEC 18013-5 and -7 and their ecosystems.

STA appears to act in the role of an Ecosystem Coordinator (STA, 2020; STA 2021).

# Conclusions (To Do)
- OCI vs mDL: grass roots vs big tech, legislators & industry bodies getting involved, international ISO vs own specs
- IDunion: politically challenging complex regulatory environment
- NACS: Where’s the tech ecosystem and own standards? Seems only 1 player. issuer = EC. competitiveness?
- Need strong driver with established links to external decision makers and primary interest in success of tech approach

# Limitations
My goal was to complete the entire article during the RWOT12 week with a small allowance for additional conclusions and inclusion of feedback on the draft piece thereafter. Due to these time constraints, I could not dive as deeply into each case study as I had hoped. One case study demonstrating an established Ecosystem Coordinator that was brought to my attention during RWOT12 revolves around the [Car Connectivity Consortium](https://carconnectivity.org/). Sadly, there was no time left to explore this further.

# Contributions
I am grateful for inspiration and information gathered from fellow RWOT12 participants and all those little side conversations with various RWOT12 attendees. In particular, my understanding of the following use cases was given more colour by:
- IDunion use case: [Sebastian Schmittner](https://www.linkedin.com/in/sebastian-schmittner-a43440107/), [Sebastian Zickau](https://www.linkedin.com/in/zickau/), [Carsten Stöcker](https://www.linkedin.com/in/dr-carsten-st%C3%B6cker-1145871/)
- NACS use case: [Joe Andrieu](https://www.linkedin.com/in/joe-andrieu-a0528/) 

# References
- AAMVA. [Jurisdiction Data Maps - Mobile Driver License Implementation Data Map](https://www.aamva.org/jurisdiction-data-maps#anchorformdlmap). Accessed 21/09/2023.
- AAMVA, 2022. [Mobile Driver’s License (mDL) Implementation Guidelines, Version 1.1](https://www.aamva.org/getmedia/c4fe2a21-91ff-449d-9df3-5a7e33cf3a8e/mDL-Implementation-Guidelines-1-0%E2%80%942021.pdf). 
- BMWK. Bundesministerium für Wirtschaft und Klimaschutz [Homepage](https://www.bmwk.de/Navigation/DE/Home/home.html). Accessed 22/09/2023.
- Boone & Wirrig, 2022. [Surviving in the SSI Ecosystem](https://github.com/WebOfTrustInfo/rwot11-the-hague/blob/master/draft-documents/ssi-stakeholder-mapping.md).
- Brumnik, 2023. [Blockchain Paving the Way for Secure and Transparent Supply Chains: Insights from Spherity’s Success in the U.S. Pharmaceutical Industry](https://medium.com/@olga.brumnik/blockchain-paving-the-way-for-secure-and-transparent-supply-chains-insights-from-spheritys-1c44a08fa738).
- Businesswire, 2021. [NACS Announces TruAge™ Digital ID-Verification Solution](https://www.businesswire.com/news/home/20210511005386/en/NACS-Announces-TruAge%E2%84%A2-Digital-ID-Verification-Solution). 
- DHS, 2021. [Minimum Standards for Driver's Licenses and Identification Cards Acceptable by Federal Agencies for Official Purposes; Mobile Driver's Licenses](https://www.federalregister.gov/documents/2021/04/19/2021-07957/minimum-standards-for-drivers-licenses-and-identification-cards-acceptable-by-federal-agencies-for).
- DMV CA. [Download California’s first mobile driver’s license (mDL) today](https://www.dmv.ca.gov/portal/ca-dmv-wallet/). Accessed 21/09/2023.
- European Commission. [eIDAS Regulation](https://digital-strategy.ec.europa.eu/en/policies/eidas-regulation). Accessed 22/09/2023.
- European Commission, 2022. [European Digital Identity Architecture and Reference Framework – Outline](https://digital-strategy.ec.europa.eu/en/library/european-digital-identity-architecture-and-reference-framework-outline). Accessed 22/09/2023.
- FDA. [Drug Supply Chain Security Act (DSCSA)](https://www.fda.gov/drugs/drug-supply-chain-integrity/drug-supply-chain-security-act-dscsa). Accessed 20/09/2023.
- IDunion. An ecosystem for trusted identities [Hompage](https://idunion.org/?lang=en). Accessed 20/09/2023.
- IETF, 2023. [SD-JWT-based Verifiable Credentials (SD-JWT VC)](https://www.ietf.org/archive/id/draft-ietf-oauth-sd-jwt-vc-00.html).
- INATBA, 2023. [MOBILE DRIVER’S LICENCE (MDL) & SELF-SOVEREIGN IDENTITY (SSI) COMPARISON – UPDATED](https://inatba.org/news/mobile-drivers-licence-mdl-self-sovereign-identity-ssi-comparison/).
- ISO. [35.240.15 - Identification cards. Chip cards. Biometrics](https://www.iso.org/ics/35.240.15/x/). Accessed 21/09/2023.
- ISO, 2021. [ISO/IEC 18013-5:2021 - Personal identification — ISO-compliant driving licence — Part 5: Mobile driving licence (mDL) application](https://www.iso.org/standard/69084.html).
- Lacity et al., 2023.[The Quiet Corner of Web3 That Means Business](https://sloanreview.mit.edu/article/the-quiet-corner-of-web3-that-means-business/).
- NACS. Advancing Convenience & Fuel Retailing [Homepage](https://www.convenience.org/). Accessed 21/09/2023.
- NACS, 2022. [U.S. CONVENIENCE STORE COUNT](https://www.nacsmagazine.com/issues/february-2022/us-convenience-store-count).
- NIST. [Digital Identities - Mobile Driver's License (mDL)](https://www.nccoe.nist.gov/projects/digital-identities-mdl). Accessed 21/09/2023.
- OCI. Open initiative enabling trusted digital interactions in pharmaceutical supply chains [Homepage](https://www.oc-i.org/). Accessed 20/09/2023.
- OCI. [DSCSA Interoperability Profile](https://www.oc-i.org/interoperability-profile). Accessed 20/09/2023.
- OCI, 2023. Digital Wallet Conformance Criteria v3.3.0: [4.1.2 Verifiable Data Registry & Endorsed DID Methods](https://open-credentialing-initiative.github.io/Digital-Wallet-Conformance-Criteria/v3.3.0/#verifiable-data-registry-endorsed-did-methods). Accessed 20/09/2023.
- Open ID. OpenID for Verifiable Credentials - Overview [Homepage](https://openid.net/sg/openid4vc/). Accessed 22/09/2023.
- STA, 2020. [The Mobile Driver’s License (mDL) and Ecosystem](https://www.securetechalliance.org/publications-the-mobile-drivers-license-mdl-and-ecosystem/).
- STA, 2021. [Secure Technology Alliance Invites Businesses to Accept mDLs in Response to Apple Wallet Integration](https://www.globenewswire.com/en/news-release/2021/09/21/2300850/22743/en/Secure-Technology-Alliance-Invites-Businesses-to-Accept-mDLs-in-Response-to-Apple-Wallet-Integration.html).
- STA: mDLConnection. [Implementation Tracker Map](https://www.mdlconnection.com/implementation-tracker-map/). Accessed 21/09/2023.
- TruAge. Prove your age. Protect your identity. [Homepage](https://www.mytruage.org/). Accessed 21/09/2023.
- Wirrig, 2022. [Closing a Key Gap in DSCSA Compliance](Closing a Key Gap in DSCSA Compliance (pharmaceuticalcommerce.com)).
- W3C, 2022. [Verifiable Credentials Data Model v1.1 - W3C Recommendation, 03 March 2022](https://www.w3.org/TR/vc-data-model/).
- W3C, 2023. [Status List 2021](https://www.w3.org/community/reports/credentials/CG-FINAL-vc-status-list-2021-20230102/).
