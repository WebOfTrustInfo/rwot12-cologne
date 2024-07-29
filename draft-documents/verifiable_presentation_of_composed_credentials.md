# Verifiable Presentation of Composed Credentials

**Authors:**

- Markus Batz <markus.batz@stadt-koeln.de>
- Sebastian Zickau <sebastian.zickau@stadt-koeln.de>
- Diana
- Fateme
- Golda
- Ivan
- Markus

## Abstract

This paper introduces a novel framework for the presentation of sets of related verifiable credentials that would apply for different purposes; such as infection protection, donation, or education. The framework allows individuals to assemble multiple credentials issued by different issuers and disclose them all together as one claim to stakeholders. By composing credentials together, we can extend the usual pattern of issuer, holder, and verifier. The further challenge is to generate a credible presentation that will be compelling to stakeholders such as regulators, donors, or employers. By bridging the gap between stakeholders and the world of verifiable credentials, we provide a practical and adaptable solution for a wide range of use cases. This holistic exploration of composite credentials demonstrates their potential to address and change the way credentials are presented and verified in a variety of settings.

## Introduction

The digital transformation of credentials has been a subject of interest for both academia and industry, especially in the context of verifiable credentials. Verifiable credentials are digital statements made by the issuer about a subject, which can be verified by anyone without contacting the issuer. Traditionally, the model of verifiable credentials has been relatively straightforward, involving three main roles: the issuer, the holder, and the verifier. The issuer provides the credential, the holder stores it, and the verifier checks its validity. This model works well for single-purpose credentials but falls short when individuals need to present a set of related credentials for diverse use cases.

Evaluating the truth or validity of the digital statement is a separate matter and may benefit from context, such as having access to statements about the issuer, and other independently signed statements relating to the subject or to the statement itself. 

Hence, we propose several methods of presenting composed credentials, that may provide valuable context for the evaluation of a credential.


## Background information and Related works

### Concepts

!!Dies weiter nach hinten, zu erst die Motivation dann Lösungen!!

#### Verifiable Presentation of multiple credentials

This concept refers to the practice of bundling several credentials together in a single package for the purpose of verification. Instead of verifying each credential individually, the bundled set can be verified all at once, making the process more efficient.

![image](https://github.com/gvelez17/rwot12-cologne/assets/798887/f619c573-330f-4935-a647-6093e1dbe624)


#### Composing two or more linked credentials

##### Linking Credentials by Common Subject
   
This involves creating a unified set of credentials that relate to a single individual or entity, known as the subject. The aim is to provide a comprehensive view of that subject's qualifications, skills, or statuses.
   
##### Linking Addressable Credentials
   
Addressable credentials have unique identifiers that allow them to be accessed individually. The concept of linking addressable credentials involves bringing such credentials together, even if they are stored in different locations or issued by different organizations, for the purpose of verification.
   
##### Credential as a Subject
   
In some scenarios, a credential itself can serve as a subject for another credential, creating a hierarchical relationship between them. This adds an additional layer of context to the credentials, making them more informative.
   
##### Linking other Digital Evidence by Hash
   
This concept refers to the inclusion of additional forms of digital evidence, such as documents or media files, in the credential verification process. These additional pieces of evidence are linked to the credentials through cryptographic hashes to ensure their integrity.
   
#### Verifiable Attestations on Credentials

An attestation is an extra layer of verification added to a credential by a third party. This concept enhances the credibility of the credential by providing additional information or endorsements that can be useful during the verification process.

#### Public sets of Verifiable Credentials

This concept involves making a set of credentials publicly available for anyone to verify. This is often used in scenarios where transparency is important, such as public registries or open-source projects.

![image](https://github.com/gvelez17/rwot12-cologne/assets/798887/73e7a18b-b79c-4d6b-8039-e9d23c2e5e27)

## Use cases

write intro ...

### Food
The food industry sector is regulated, and businesses are obligated to prove conformance with legal standards. One legally required standard is to have all employees instructed on hygiene regulations according to the federal German infection protection regulation (§43 IfSG) []. The instruction is conducted by a municipal institution certifying successful participation with a respective *health-certificate* credential. The employee presents this credential on his first commencing day to his first employer, who validates the certificate by countersigning it. This needs to happen three months from the date the test was taken; if not, a new test and new certificate need to be carried out. The health-certificate credential issued to the employee in combination with this *countersignature* of the first employer will be verified by all future employers and inspectors. Even if the employee switches to a *new* employer, the *initial* credential validation is verified. The combined proof may be presented by the employee or by the current employer. Thus, a technical concept is needed to have the two credentials combined when presenting the proof.

#### How to approach this specific use case

??Schon Umsetzung, weiter unten??

To address this specific process, several implementations are possible:

- The analog process is transferred completely to the digital realm.
The employer verifies the digital credential and issues an additional credential confirming that verification, including his issuer details and a timestamp.
- These two credentials could be bound together with different approaches (see below).
- The law describing this exact analog process could be changed to address digital credentials.
- The rule that the employee needs a countersignature within three months could be dropped entirely.

#### Description in general terms
!!this was done for the resepted table with all sorts of different functions, weiter nach hinten!!
!!neue bullet points und wording/Def der Rollen klären!!
!!Vllt. diese Details ganz rauslassen aus diesem Paper und nur konzeptionell beschreiben!!

1. Both credentials are controlled by one stakeholder (employer, employee, or both)

3. The municipal institution (Issuer 1) is issuing the "health-instruction"-certificate (VC1) to the employee (Holder 1). Holder 1 is presenting this VC1 to the employer (Verifier 1, Issuer 2, and Holder 2), he verifies the VC1 and signs (issues) a second VC2. The inspector (Verifier 2) is checking the VC2 which includes information about H1 and H2.

In the second workflow, the VC1 is semi-publicly !!was heißt das?!! available. This information (VC1) is examined and checked by the restaurant owner (I2) as well as signed, the VC1 becomes the VC2 to be later checked by the inspector (V2)
In the third process, the employee is showing her credential VC1 to the inspector (V2) and the restaurant owner is presenting the checked proof of the VC1 to the inspector as VC2.
In the third workflow, a functionality of delegation is introduced which allows the H1 (employee) to delegate the VC1 to the restaurant owner (H2) who is providing this delegated VC1 to the inspector (V2).

!!Lösungen auch weiter nach hinten!!

### Education

Another use case of this idea could be applied to vocational training and education. In the education sector, students often collect various certificates, diplomas, and awards from different schools or training programs. Traditionally, each of these credentials has to be presented individually to employers or educational institutions, making the process cumbersome and time-consuming. Our new framework aims to simplify this by allowing students to combine all their credentials into a single, easy-to-share package.

In this use case, we have three essential roles: *Issuer*, *Holder*, and *Verifier*. As the name suggests, the Issuer is responsible for issuing the VC, usually an authorized organization or institution that provides some courses offers, issues, and signs the credential. The Holder receives his VC from the Issuer and stores it in his own storage, gaining full control over it. He can decide to show his credential to the Verifier, who now can verify the credential by validating the signature that the Issuer gave upon creation. In this context, the issuer would be an educational institution, the holder is the student, and the verifier could be an employer or another educational institution.
The framework for the presentation of sets of binded or related VCs in this use case could be as follows: 

1. Educational Institution (Issuer): May issue one or more credentials for various skills or courses that the student has passed.
2. Learner (Holder): Aggregates his credentials (VC1) and presents them as a composite credential to their employer.
3. Employer (Verifier1): Investigates the validity of binded VCs as a composite VC. They may issue an additional VC (VC2) that signifies the learner’s new role or skill level within the company.
4. Education/Industry Regulatory Body (Verifier2): Checks the validity of the newly issued VC (VC2),  binded to the previous VCs to ensure the validity of those VCs.

In this workflow, the flexibility to assemble multiple credentials (possibly from different issuers) into a single, composite credential allows for a more holistic representation of an individual’s skills, experiences, and competencies.


### Philanthropy
In philanthropy, it is particularly important to verify that funds are distributed for the intended purpose and to the intended recipients. Generally, there are three parties in philanthropy: the funder, the organization providing benefits, and the beneficiaries.  Currently, the organization is likely to provide some detailed reporting to the funder, and possibly a third-party auditor may be engaged to verify the information in the report.

Verifiable credentials have the potential to give agency and leverage to the recipients themselves, by allowing them to directly attest about the benefits received.  If the recipients are also otherwise credentialled, by peer recommendations, work performance, or academic attestations, this can add to the overall credibility of the collected set.  

In areas where corruption is rampant, having an independently verifiable set of related attestations about the use of funds, may make a critical difference in how they are actually distributed.

## Methodology

### Presenting Multiple Credentials
Existing methods allow the construction of a Verifiable Presentation that contains multiple signed credentials, that may have a common subject.  The Holder who signs the Verifiable Presentation is commonly the subject of each credential but is not required to be.  

### Addressable Verifiable Credentials
In some cases, it may be desirable to publish Verifiable Credentials to a public or privately shared dataset.  For example, a restaurant's safety certification may be public, while the individual workers' food handling credentials are held privately and only presented to inspectors.

Several data protocols could be good candidates for publishing verifiable credentials in an addressable manner.  In a related paper, we demonstrate how the Ceramic protocol can be used to publish verifiable credentials into a decentralized network, thus making them addressable.

Note that addressable verifiable credentials may not be fully public, as encryption or access controls can also be put in place.

### Verifiable Presentations of Addressable Credentials
In order to fulfill the requirements of a Verifiable Presentation, the presentation must be signed by a Holder. 

In the case of the Ceramic Network, the Holder is the owner of the data stream. A Proof may be included that the Holder signing the Verifiable Presentation is also the DID that is the Controller of the stream where it was published. This aspect is novel and may be expanded on in a separate paper. 

### Linking Verifiable Credentials in a Presentation
In the case where the credentials do NOT have a common subject, it may be valuable to show a proof of the link between them.

Using Addressable credentials allows one credential to actually be the Subject of another, in that a second person can attest to the validity of a claim.

This can be a powerful way of validating a specific claim without having to layer on business logic.

For example, if a student claims that they took a specific course on specific dates, they may make a self-attestation to that effect.  A professor could make a similar attestation, but it would be necessary to compare the course dates and name in order to ascertain that the professor is referring to the same course.  However if the professor simply directly "vouches for", or attests that *the student's claim is true* then there is no need to compare field by field.  This is only possible if the student's claim is addressable.

One way to do this is to have all of the claims embedded in the same document, which gives them relative addresses, but this requires tight coordination. Having each claim have an independent and verifiable address allows the attestations to happen asynchronously and even enables adversarial attestations.

### Privacy concerns with Addressable Claims
Note that it is not necessary for a claim to be on a public network for it to be addressable.  Several layers of privacy are possible with addressable claims:

1) Wallet address
Generally Verifiable Credentials are requested from the holder by type. It is possible to construct an address starting with the DID of the holder and followed by the type and/or id of the verifiable credential and to provide a library that converts such a URI to a DIDComm or other standard request method. This allows addressing the credential but it may be difficult to ensure consistency in constructing the address; it might not be determinate.

2) Encryption
Even on a public network, data may of course be encrypted for privacy, and the keys provided only as desired. The tools for constructing the Verifiable Presentation may include selective decryption of fields the Controller or Holder wishes to share. 

3) Access Control
It is also possible to have a Ceramic or other network on private infrastructure, rather than on the shared mainnet.

## Possible workflows and processes

In the realm of verifiable credentials, the workflows and processes can vary significantly depending on the use case, the stakeholders involved, and the types of credentials being used. Below, we outline some possible workflows and processes that could be employed to make the most out of the framework for presenting composed credentials.

### Single Holder, Single Verifier Workflow

In the simplest scenario, a single holder presents a set of composed credentials to a single verifier. The verifier checks the validity of each credential in the set and makes a decision based on the aggregated information. This workflow is straightforward but limited in scope, as it doesn't take advantage of the full potential of composed credentials.

### Multi-Issuer, Single Holder, Single Verifier Workflow

In this workflow, a user may have several credentials from multiple issuers and combines them into a single presentation. The verifier then checks the validity of the composed set, which could provide a more comprehensive view of the holder's qualifications or status. This is particularly useful in scenarios like job applications or academic admissions where multiple aspects of an individual need to be assessed.

### Delegation Workflow

In some cases, a holder may wish to delegate their credentials to another party, who then becomes the new holder. This new holder can then present these credentials to a verifier. This is useful in scenarios where, for example, an employee delegates their health and safety credentials to their employer, who then presents these to a regulatory body.

### Embedding Workflow

The embedding scenario is similar to a chaining process. The difference (may) be that in embedding the claim_1/cred_1 will be presented *inside* claim_2/cred_2 and is therefore uniquely bound to 2. It may depend on the format used to represent the credentials if this bounding can be reversed.

### Attestation Workflow

In this workflow, third parties can add attestations to existing credentials, thereby enhancing their credibility. For example, after verifying a student's academic credentials, an employer could add an attestation that the student has been hired and has demonstrated certain skills on the job.

### Permissionless Presentation Workflow

In the case where Verifiable Credentials are available in a public shared data stream, any individual may collect a set and sign a presentation containing them. Effectively anyone with read access to the signed credentials may act as the "Holder" and create a presentation. This may be particularly useful for auditors or journalistic use cases.

Each of these workflows offers its own set of advantages and challenges, and the choice of workflow would depend on the specific requirements of the use case at hand. By understanding and leveraging these different workflows, we can create more flexible, robust, and user-friendly systems for credential verification.

## Relationship functions

### Overview

first five also in edid workshop paper

- Delegation (credential)
- Guardianship (credential)
- Forwarding
- Handover
- Invalidation
- Composition
- Chaining (also Linking/Binding/Augmenting??)
- Attestation
- Witness
- Controllership
- Nesting/Embedding/Merging

sth to avoid
- Impersonation (new, mentioned in SSI book)

### Delegation

In some cases, a holder may wish to delegate their credentials to another party, who then becomes the new holder. This new holder can then present these credentials to a verifier. This is useful in scenarios where, for example, an employee delegates their health and safety credentials to their employer, who then presents these to a regulatory body.

-- text aus erstem paper, mit edid vergleichen!!--
In a \textit{delegation}, holders can give their credentials to other holders. The second holder can present the credentials to a verifier. Including the information that the presented credentials are delegated and by whom may seem to be the normal case. This may also be possible in a delegation where the second holder is not adding the information that the presented credentials were delegated. A delegation has two roles, i.e., the \textit{delegetor} and the \textit{delegate}. The delegator is the subject with the authority to delegate certain rights to others. The delegator should be able to revise or revoke delegation credentials. A delegate is a subject who can carry out a specific task on behalf of another subject, i.e., the delegator.
--

### Guardianship

In a \textit{guardianship} variant, the holder of claims cannot present these to verifiers because of the inability to do so. A legal guardian steps in to support the holder and present the credentials/claims on her behalf. This can be when the holder is not old enough to present claims and is supported by a parent (guardian). Preukschat and Reed describe guardianship as a form of “complete delegation” carried out using a guardianship credential. They state that it enables the guardian to set up and operate an agent and wallet on behalf of the dependent and, when necessary, prove that they are acting in the capacity of a guardian \cite{preukschat2021self}. There are two roles in guardianship, i.e., the \textit{guardian} and the \textit{dependent}. The guardian is the person who controls the claims and credentials on behalf of the subject. The dependent is the person or subject of whom the claims and credentials are about.

-- from aries rfc website, was für die References --
https://github.com/hyperledger/aries-rfcs/blob/main/concepts/0103-indirect-identity-control/guardianship-details.md
Guardianship Details
For a complete walkthrough or demo of how guardianship works, see this demo script.

Use Cases
See https://docs.google.com/presentation/d/1qUYQa7U1jczEFun3a7sB3lKHIprlwd7brfOU9hEJ34U/edit?usp=sharing

Who appoints a guardian (rationales)
See https://docs.google.com/presentation/d/1aq45aUHTOK_WhFEICboXQrp7dalpLm9-MGg77Nsn50s/edit#slide=id.g59fffee7a0_0_0

Transparent vs. Opaque
See https://docs.google.com/presentation/d/1aq45aUHTOK_WhFEICboXQrp7dalpLm9-MGg77Nsn50s/edit#slide=id.g59fffee7a0_0_46

Modes of Guardianship
Holding-Based, Impersonation, Doc-based

See https://docs.google.com/presentation/d/1aq45aUHTOK_WhFEICboXQrp7dalpLm9-MGg77Nsn50s/edit#slide=id.g59fffee7a0_0_265

See also https://docs.google.com/presentation/d/1aq45aUHTOK_WhFEICboXQrp7dalpLm9-MGg77Nsn50s/edit#slide=id.g59fffee7a0_0_280, https://docs.google.com/presentation/d/1aq45aUHTOK_WhFEICboXQrp7dalpLm9-MGg77Nsn50s/edit#slide=id.g59fffee7a0_0_295, https://docs.google.com/presentation/d/1aq45aUHTOK_WhFEICboXQrp7dalpLm9-MGg77Nsn50s/edit#slide=id.g59fffee7a0_0_307

Guardians and Wallets
Need to work on "wallets" term See https://docs.google.com/presentation/d/1aq45aUHTOK_WhFEICboXQrp7dalpLm9-MGg77Nsn50s/edit#slide=id.g59fffee7a0_0_365
--

### Forwarding

In \textit{forwarding} a credential, the holders send their unaltered credentials to other roles. This may be to verify the VC or to inform someone about it. The dictionary definition of forward is to send, e.g., a letter, message, or document, to another person, organization, or address. In a forwarding action, there are \textit{senders} and \textit{receivers}. In a forwarding scenario, $H_1$ forwards her credential to $H_2$ without altering the data.

### Handover

A \textit{handover} is an act or instance of handing something over. In our context, credentials that can be handed over are valid without the binding to a specific \textit{holder}. That means whoever owns the credentials' data block can use them as intended. This could be the case for concert or public transport tickets which are valid without personal identifiable information (PII). The credential is usable without any modification or the addition of information. This function also consists of sender and receiver roles. The function is heavily influenced by the analog version in which someone has a secure against forgery physical ticket that can be passed on. The difficulty in adapting this scenario in the digital world is that data blocks can be copied. In our case, a wallet app would have to be able to permanently delete the sender's credential when it is handed over to the receiver and her wallet. This leads into the last function described here, the \textit{invalidation}.

### Invalidation

In the process of \textit{invalidation}, an official document is deprived of legal efficacy because of contravention of a regulation or law. In our case, a transferred credential, e.g., in cases of delegation, guardianship, or handover, is made invalid of the current controller of the data block, i.e., holder $H_2$.

Tab. \ref{tab:icr}, based on a table in the Sovrin glossary \cite{sovglo3}, compares the mentioned functions in terms of involved roles, keys, added meta-information, security mechanisms, and legal responsibilities. As we describe proposed wallet functionalities, a wallet app developer is required to implement the functions according to a restricted standard as the holders, i.e., dependents and senders rely on it.

The status of a verifiable credential may change over time and these changes need to be communicated to the relying party. \textit{Status lists} are a concept to maintain the status of a credential. For SD-JWT, a specification is presented in a work-in-progress paper about token status lists \cite{ietf-oauth-status-list-01}, which describes a list data structure to represent the status of a JWT. The status list is a byte array containing the referenced credentials' status represented by one or multiple bits. Two or more statuses may be managed depending on the number of bits reserved per referenced credential. The simplest case reserves one bit per credential and thus may express "only" whether a credential is valid or not. The status list is maintained as a JWT and globally referenced by a URI. Therefore, the status list concept is suitable for status changes triggered by the issuer who can maintain access to the status list.  A common holder, as assumed in the use cases in the paper, will not have the technical means to maintain such a list and guarantee its accessibility.

### Composition

### Permissionless Presentation Workflow

In the case where Verifiable Credentials are available in a public shared data stream, any individual may collect a set and sign a presentation containing them. Effectively anyone with read access to the signed credentials may act as the "Holder" and create a presentation. This may be particularly useful for auditors or journalistic use cases.

Each of these workflows offers its own set of advantages and challenges, and the choice of workflow would depend on the specific requirements of the use case at hand. By understanding and leveraging these different workflows, we can create more flexible, robust, and user-friendly systems for credential verification.

### Chaining and linking

In a credential \textit{chaining or linking} situation, the holder gets credentials and claims which are linked together. The linkage information is also presented to the verifier to better understand how these claims were constructed over time and by whom. This is necessary to increase trust through a verifiable chain. The verifier may want to judge/assess the claims depending on their origin. This can be shown in a use case in which a medical person gives out vaccination certificates, and the verifier will be given information about how the medical person was credited with their license. The Aries RFC 0104 \cite{ghariesrfc104} describes a set of conventions, collectively called chained credentials, that allows data in a verifiable credential to be traced back to its origin while retaining its verifiable quality. This is the basis for the chained credential mechanism that gives this RFC its name. Chained credentials contain information about the provenance of some or all of the data they embody; this allows a verifier to trace the data backward, possibly through several links, to its origin and to evaluate trust on that basis \cite{ghariesrfc104}. In chained credentials, there is a linked list of the common issuers, holders, and verifiers, which can be called \textit{origin source} or \textit{provenance} and \textit{links} of a chain. 

### Attestation Workflow

In this workflow, third parties can add attestations to existing credentials, thereby enhancing their credibility. For example, after verifying a student's academic credentials, an employer could add an attestation that the student has been hired and has demonstrated certain skills on the job.

In an \textit{attestation} scenario, the holder is presenting the claims to another entity, and this entity is attesting to the initial claims to increase their value or even to make them valid. In this scenario, the holder of the claims is the same person; the claims are just verified/validated by another party. The \textit{Attestor} is the person attesting a claim or credential of another subject.

### Witness

The \textit{witness} concept is similar to an \textit{attestation}. The difference can lie in the verification process; here, it is actually necessary to have two holders present. They both need to present their individual claims to the same verifier. The verifier decides the state of the credential or claims. The dictionary definition of \textit{witness} is: One who is or was present and can testify from personal observation; one present as a spectator or auditor.

### Controllership
??brauchen wir das??
Owner of car, legal responsibility
%Controllership passt nicht wirklich im Angesicht des Controllers bei VCs, daher eher oben in RW/Def erwähnen

OED definition: controllership, n. The office or function of controller; the period of holding this office. 
controller, n. A person who restrains, regulates, or directs people or things; a person who exercises control.

-- from aries rfc website --
https://github.com/hyperledger/aries-rfcs/blob/main/concepts/0103-indirect-identity-control/controllership-details.md
Controllership Details
How controlled things can undermine privacy
controllership and delegation
Ethical considerations and the duty continuum
Informal controllership by owner
How controllership becomes transparent
sample trust framework (DignifID?)
--

### Nesting and embedding

The \textit{nesting or embedding} scenario is similar to the chaining process. The difference is that in the nesting/embedding case, a credential will be presented inside another credential and is, therefore, uniquely bound to the latter. It may depend on the format used to represent the credentials if this bounding can be reversed.

-- von oben, hier her kopiert --
Embedding Workflow

The embedding scenario is similar to a chaining process. The difference (may) be that in embedding the claim_1/cred_1 will be presented *inside* claim_2/cred_2 and is therefore uniquely bound to 2. It may depend on the format used to represent the credentials if this bounding can be reversed.
--

-- zusätzlich aus Wöterbuch --
OED definition: nesting, in nest, v. Of an animal, esp. a bird. intransitive. To make or have a nest in a particular place. nesting, adj. That makes or occupies a nest. nesting, n. The action, or manner, of constructing a nest or nests. embedding, in embed | imbed, v. transitive. To fix firmly in a surrounding mass of some solid material. Also reflexive. embedding, n. The action of the verb. The action of embed, v. 1a. embed | imbed, v. transitive. To fix firmly in a surrounding mass of some solid material. Also reflexive.
Roles: ...
-- 

|                                              | Delegation Relationship                                   | Guardianship Relationship                                  | Controller Relationship                        |
|----------------------------------------------|-----------------------------------------------------------|------------------------------------------------------------|------------------------------------------------|
| Exists between two identity owners           | Yes                                                       | Yes                                                        | No                                             |
| Both parties control their own private Keys  | Yes                                                       | No**                                                       | No***                                          |
| Who authorizes the relationship              | Delegator                                                 | Dependent or a legal representative of the  Dependent      |  |
| Authorization mechanism                      | Delegation Credential (may be backed by  legal agreement) | Legal agreement (may be backed by Guardianship Credential) | Thing Controller Credential                    |
| Who has legal responsibility                 | Depends on the relationship (see text)                    | Guardian (serving as information fiduciary  )              | Depends on the relationship (see text)        |

## Future Work

Looking ahead, there are several important questions that need to be addressed to further develop and refine the framework for presenting composed credentials:

1. **Revocation:** Can individual credentials or entire sets of combined credentials be revoked? Understanding how to manage revocation is crucial for maintaining trust and integrity in the system.

2. **Privacy:** Is it possible to hide certain parts of the composed credentials from the verifier? This would allow for more privacy while still enabling verification.

3. **Nested Compositions:** Can a set of composed credentials be treated as a single unit, which can then be included in another set of composed credentials? Exploring this could offer more flexibility in how credentials are presented and verified.


## Conclusion
The digital transformation of credentials is an ongoing process that presents both challenges and opportunities. This paper introduces a novel framework for the presentation of sets of related verifiable credentials, extending the traditional model of issuer, holder, and verifier to accommodate more complex and diverse use cases. Through the concept of composed credentials, we offer a more holistic and flexible approach to credential verification, one that is adaptable to a wide range of scenarios including employment, education, and philanthropy.
Our exploration into the various workflows and processes demonstrates the versatility of this framework, providing practical solutions for real-world challenges in credential management and verification. While there are questions that require further investigation, as outlined in the Future Work section, the current framework serves as a robust foundation for the next generation of digital credentials.
By bridging the gap between stakeholders and the evolving world of digital credentials, we take a significant step towards a more secure, efficient, and user-friendly ecosystem for identity verification and trust.

## References

[1] Maintained by the Sovrin Governance Framework Working Group. 2019. Sovrin Glossary V3. https://sovrin.org/wp-content/uploads/Sovrin-Glossary-V3.pdf

[2] Alex Preukschat and Drummond Reed. 2021. Self-sovereign identity. Manning Publications.

[3] Daniel Hardman, Lovesh Harchandani , Aries RFC 0104: Chained Credentials, https://github.com/hyperledger/aries-rfcs/tree/main/concepts/0104-chained-credentials

[4] Manu Sporny, Dave Longley, David Chadwick, and Orie Steele. 2024. Verifiable CredentialsDataModelv2.0,W3CCandidateRecommendationSnapshot. https: //w3c.github.io/vc- data- model/

[5] Daniel Hardman, Aries RFC 0103: Indirect Identity Control, https://github.com/hyperledger/aries-rfcs/blob/main/concepts/0103-indirect-identity-control/README.md

[6] Deutsches Infektionsschutzgesetz §43 Belehrung, Bescheinigung des Gesundheitsamtes, https://www.gesetze-im-internet.de/ifsg/__43.html

[7] 
