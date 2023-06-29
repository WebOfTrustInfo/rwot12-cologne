# Trust in Verifiable Digital Product Passports

Authors:  
- Christian Fries [EECC](https://id.eecc.de)  
- Dr. Sebastian Schmittner [EECC](https://id.eecc.de)  

Date: Jul 23, 2023

## Introduction

Today, legislators demand more and more transparency and traceability for products and goods, resulting in the need for digital product passports (DPP). The expectations towards a such product passports are high, comprising interoperability, security and verifiability [1]. These requirements indicate that the use of verifiable credentials (VCs) as the basis for the DPP could be beneficial. The idea is that various parties can assign properties to a DPP via VCs, as immutable and verifiable data packages, and thereby build the DPP or rather the verifiable product passport (VPP). The concept originates from a paper written by the [IDUnion](https://idunion.org/) consortium, a governmental research project on digital identities [2]. Apart from VCs, the IDUnion publication also covers unique product identifiers, e.g. GS1 standardized GTINs, and their adjacent data carries. Both these topics are DPP are perquisites according to [1].


## Implementation

The concepts of the VPP have been implemented by the [European EPC Competence Center](https://id.eecc.de/) in the context of the [ID-Ideal](https://id-ideal.de/) project. The first draft leverages decentralized identifiers (DIDs), W3C JSON-LD VCs and GS1 digital links [3] for realizing the envisioned use case.  

### Components

#### Credential Registry

A registry that can be published using a DIDDocument [4] or other means that allows the query of issued credentials in an unauthenticated or authenticated fashion based on their subject id. Thereby this building block allows easy publication of credentials a stakeholder has signed or obtained and which shall be retrievable for others in order to verify them, i.e. the data within them about the product.

#### Verifier

The verifier software mainly provides the verification functionality and an optional discovery of credentials via [credential registries](#Credential-Registry). This software at best runs at the verifying entity but can also be provided by an independent third party. In order to make this important module accessible we provide an easy to set up open-source implementation [5]. Next to the discovery and verification the provided verifier software also provides the visualization of the VPP.


### Action Flow

GS1 Digital Links can resolve towards arbitrary resources depending on various configurable configuration details. In this use case, the digital link of a product resolves to a [verifier software](#Verifier). There the verifier software queries credential registries in order to find credentials with the product as subject, verifies them and displays DPP based on the data in the VCs, i.e. a VPP.


![](https://ipfs.io/ipfs/QmS9THKsKhykNrJHXMAJg1YXMys7ZBWi5zUV38dx7Koune?filename=dl_vpp.png)
*Example VPP digital link: https://id.eecc.de/01/04012345999990/10/20210401-A/21/XYZ-1234*


#### Authorization

The basic flow does not need authorization and is accessible to the public by the digital link, e.g. customers, who represent the B2C flow of the VPP generation. But the flow is also applicable in the B2B context, e.g. in a circular economy, where it is compulsory that stakeholder can share product data in a trusted way. Here the authenticated endpoint of [credential registries](#Credential-Registry) can be used to retrieve more credentials or credentials with more information disclosed than for the public requester. This an be achieved by authenticating with verifiable presentations, which can both identify/authenticate the requester and contain additional authenticating credentials, e.g. external certificates that grant access to certain resources.  
If registries cannot deliver the needed information, one can always request a presentation of the needed credential at the holder or issuer via OpenID4VP [6].


### Advantages

The described way of realizing a VPP provides a low access barrier, e.g. for the B2C use case while still being able to map more complex B2B use cases with authentication in a federated or decentralized ecosystem. Further it complies to the requirements of the soon mandatory european DPP, leveraging the latest technologies.



## Trust Challenge

An untackled issue of the verification is the trust in identities. While the verification of the cryptographic signature of a DID is a well understood and tamper-proof procedure, the origin of the trust in a certain DID remains a problem that can be tackled in various ways.

### Trusted DIDs

The simplest way is to have a, most likely domain specific, self-maintained trust list, which contains DIDs who the verifier trusts in its domain on a specific claim. This list can be checked against during the verification to determine if a credential of a specific issuer can be considered trustworthy. While it's an easy to implement solution, it is also a high maintenance solution where every stakeholder needs to keep his personal trust list clean and up to date.

### Root of Trust

Similar to the concept of TLS certificates one could create chained trust credentials where the trust origins in a root authority. Thereby a DID could be trusted if it can provide a valid chain of trust VCs, as GS1 is doing it in their LicenceCredential chaining [7].

### Web of Trust

Instead of having central trust authorities, one could leverage credential chaining in order to create a web of trust (WoT), using OpenID4VP [6] as a credential exchange protocol and the DID documents for discovery [8].  


## Conclusion

One can conclude that in order to make the VPP applicable in the real world, it is necessary to establish a framework of trust for DIDs. All mentioned methods could be used to achieve that, but this could be a particularly interesting field of application for a WoT as its decentralized nature fits perfectly with the DID ecosystem.


## References

[1] https://hadea.ec.europa.eu/calls-proposals/digital-product-passport_en

[2] https://idunion.org/wp-content/uploads/2023/04/2023-03-27_IDunion-AP-10.5_Whitepaper_V1.01_final.pdf

[3] https://www.gs1.org/standards/gs1-digital-link

[4] https://www.w3.org/TR/did-spec-registries/#credentialregistry

[5] https://github.com/european-epc-competence-center/vc-verifier

[6] https://openid.net/specs/openid-4-verifiable-presentations-1_0.html

[7] https://github.com/gs1/VC-Data-Model

[8] https://www.w3.org/TR/did-spec-registries/#openid4-verifiable-presentation