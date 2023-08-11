# Requirements towards Verifiable Credentials arising from Administrative Acts

Authors:  
- Markus Batz (markus.batz@stadt-koeln.de)  
- Dr. Sebastian Zickau (Sebastian.zickau@stadt-koeln.de)  

## Introduction
Verifiable Credential are supposed to be used in administrative procedures on federal, regional, and municipal level. The Intention is to replace paper-based credentials to drive digitalization whilst implementing self-sovereign identity principals, especially increasing decentralization and user privacy.

On the one hand several verifiable credential formats exist covering a set of features, where some features are common to all formats and some features are specific. Administrative acts on the other hand bring in certain requirements, which determine the relevance of these features for the respective administrative act.  It is of interest whether certain pattern exists within these requirements fulfilled by certain features which allow to determine suitable or favorable verifiable credential formats for administrative acts.

## Background and related work
Administrative acts result in a defined status of an individual, which is issued to that individual in form of a credential. Verification is a check whether the holder has a required status or not.

One crucial common requirement for administrative acts results from the need to know, that the person presenting the credential is the one carrying the status.  Either this trust is ensured by the technical ecosystem with features like “holder binding” such that the verifier may rely on the implementation or other trust-building components like pictures or biometry are needed during presentation. Nevertheless, there are also cases were credentials need to be presented by people to whom the credential was not issued. The corresponding feature “delegation” results from explicit rules given by law, like the IfSG §43 and a from practical situations where the holder may not present the credential in case of absence or illness, like in regularly scheduled social welfare hand out processes.
Another common requirement is “data minimalization” determined by governmental law. This leads to features like “predicate” and “selective disclosure”. Especially the feature “predicate” seems very suitable for administrative acts, but it is questionable whether the status testified in the credential may always be reduced to a “yes/no” question. Certain administrative acts are based on previous results of other administrative or external acts, resulting in the necessity for “credential chaining”.

Besides the above-mentioned process- and legal requirements also technical requirements like “security” and “interoperability” need to be discussed. It is obvious that interoperability is a crucial requirement because many administrative acts are executed in every local municipal department with resulting credential valid on federal level. Validation must be (easily) possible everywhere across all “digital identity”-ecosystems used locally to issue the credentials. In many cases the credentials are characterized by high volume with low financial impact behind such that the feature “performance” is more important than the feature “fraud protection”.

A lot of work is done in the area of credential format comparison, where lists of features are compiled, and the most relevant credential formats are assessed against these features.

In this paper the focus is on the requirement side. A set of administrative processes is assessed systematically to verify the completeness of today’s feature-lists, to determine the relevance of these feature for certain processes and to finally come up with requirement patterns and their correlation to credential formats.

## Requirement Assessment in Administrative Acts

Administrative acts are in the scope of several research programs funded by the BMWK under the “Schaufensterprojekte Digitale Identitaeten.de”. In the following table the requirements of several of these administrative acts are assessed against a list of credential format features.  The judgement on the requirements as well as the list of features is subject of further discussion. 

![Tabelle](https://github.com/WebOfTrustInfo/rwot12-cologne/assets/101271725/830f6356-e9e9-4d7e-bc8d-dc69b990a1bf)

The requirement coverage of some features is interdependent. The feature “predicate” relies on the feature “holder binding”. Only if “holder binding” is considered sufficient for the requirements of a given use case “predicates” may be applied. If “holder binding” is considered too weak such that the credential presentation needs to contain identifying attributes “predicates” are not applicable. This consideration depends on the risk in terms of potential damage induced by the administrational act. The potential damage of a tampered “health certificate” is much lower than the potential damage of a tampered “restricted access” credential, therefore the first would be a candidate for “predicates” and the other not. These interdependencies will also determine the requirement patterns. 


## Next Steps

The concept may be extended to a formalized classification of use cases, which allows the selection of suitable credential formats for the respective use case. 


## References

[1] https://github.com/WebOfTrustInfo/rwot11-the-hague/blob/master/final-documents/credential-profile-comparison.pdf
