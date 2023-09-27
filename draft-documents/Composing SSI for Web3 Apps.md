

# Composing Self-Sovereign Identity for Web3 Applications 

_Arthur Brock, Collin McClain_

## Introduction / Abstract

This paper outlines the digital identity tools that Holochain provides. These tools are built to support our ecosystem of applications, giving them important tools for managing identities both within and between application spaces. Beyond that, we are developing standards, gateways, and other tools for connecting to other Web2 and Web3 systems. We believe that these tools could also be used as individual components in other digital identity systems, extending their capacities. 

Identity solutions are composed of data bound to identifiers. In distributed systems, it is important that these solutions provide unique identifiers and secure bindings, in order to ensure the validity of the information in the absence of a trusted server acting as moderator. Thus, we use cryptographic keypairs as identifiers, signing data that we want to bind to them. 

It is also important to manage the data you display about yourself, and the varied identities you might hold in a distributed digital space. 

Thus, we provide three distinct tools that can be composed together as needed for a particular application. 

[Graphic goes here]


## Summary of Identity Tools for Holochain Apps

**DeepKey:** To provide a Distributed Public Key Infrastructure we have developed a self contained system for key management. DeepKey allows you to replace, revoke, or rederive the agent keys that you then use in your other Holochain applications. When someone installs a new Holochain application, the public key they are using for that application is registered in their local DeepKey registry. Having a public yet distributed space to validate and manage keys ensures that peers in your shared applications can confirm that your agent key is/was valid at the time you make a particular action.

**Personas & Profiles (PnP):** We believe that people should directly own their identity and have control of all their identity-related data. _P&P_ enables people to be the single point of authority for things like: names, phone numbers, email addresses, user pictures, biographical info, critical links, resources, and so on. This data is organized into different personas, because sometimes people have different “personalities” they present in different contexts. When someone installs a new Holochain app, it should present a profile_spec asking the user for mappings and permissions to their relevant personal data elements. This enables someone to update their last name or phone number in one place, and all applications which have access to that particular persona will use the new data.

**Claims & Credentials (CnC):** While _PnP_ lets you set your personal data to whatever you want, sometimes people need to confirm information about you with other sources. I could claim my name is Abraham Lincoln, but will others confirm that? When someone needs to sign a contract, or do something legally binding, what person is bound to the agreement? The _CnC_ app makes it easy to record, find, and verify claims and credentials, from lightweight approaches like 150 people verifying that the hash of my Firstname+Lastname = “uhCk203…8w43”, to weighty credentials like a government signing my passport credentials for performing electronic KYC with my bank.


## Identity Tool CapacitiesUnderstanding Identity Tool Options for your App


### 1. DeepKey

**Public & Private Key Cryptography**

When you run a Holochain application, you use a unique agent key as your address and signature to identify your actions to other agents as coming from you. Because public/private keypairs are globally unique, this provides a reference that can be used between Holochain applications and beyond.

**PKI and Key Lookups/Validations**

Holochain applications can utilize Deepkey to confirm that an agent key is valid when establishing a network connection with another agent, or when validating the actions of other agents to confirm that a key was valid when the action was signed. It does this by making a `key_state(Key, Timestamp)` call to Deepkey, running locally on the same device. Deepkey then reaches out across its own DHT network and returns the state of the key at the relevant time.

**Key Management**

Deepkey defines a management space for keys. The keys under this management umbrella can be revoked or replaced, through the authority of the first Deepkey agent. For the purposes of key management you can set up a social signing rule where you assign a list of M of N keys that collectively can manage the keyspace. This provides a method for revoking and replacing keys, even when the device running the first Deepkey agent is somehow compromised. 

**Key Recovery**

When Deepkey generates new agent keys to be used in apps, it does so by deriving them from device seeds, stored in the Lair Keystore. The paths of these derivations are saved as private entries which can be backed up. In case of the loss of the device Deepkey is running on, those backed up entries can be used, along with the master seed, to rederive the device seeds and agent keys. Thus providing a recovery option for your keys.

**WebDID Resolver Gateway**


#### 2. Personas & Profiles (PnP)

[[[A recent PnP spec](https://hackmd.io/@hololtd/SySXHVOQ3?type=view)]]

**Privacy and Layers of Membranes in Holochain**

**Personas**
Personas are the data files you keep with your personal information in them. You can keep separate personas to use in different spaces (e.g. with separate names and details for work, personal, and gaming). These Persona’s would be held in a private DHT shared between your devices which is called on by other applications when you choose to provide them with a particular persona. 

**Profile Fields**
Applications calling on Personas structure their requests as a set of profile fields such as *Handle*, *Avatar*, *Phone Number*, etc. This data is maintained as a mapping to your Persona so that if you make an update to your Persona’s information, that change will propagate across all applications that reference it. The application can save certain information from your persona like _Handle_ and _ Avatar_ that might be needed when you are offline, sharing that information in the app DHT. Other information might only be rendered through direct calls to _PnP _when you are online to serve them. This will depend on how the application is designed (see some considerations later in this article) and on what data you give permission to be shared in a persistent fashion. 

**Vocabularies and Taxonomies:** 
There are [many existing vocabularies](https://lov.linkeddata.es/dataset/lov/) for user data that an app may want or need to be compatible with rather than reinventing fields and labels. By using standardized Some advantages of doing this are increasing the likelihood of directly connecting your profile fields it is more likely to be able to map directly to the data a user has shared in PnPto existing user data (e.g. is their name stored under FirstName, fname, first_name, given_name, etc.), this also has the advantage of and getting multilingual support via vocabularies which are already translated to many languages.

**Map Specs & Updating and Revoking access**

**Holding Apps Accountable for Privacy of User Data**
There are a variety of ways that identity data can be used. An app might just read something from PnP when the data is needed. Other data may be copied and stored in the same user's local source chain within the app. Other data might be published to the DHT, or potentially even made visible to the Internet via a public gateway. 

PnP uses [Jlinx](https://jlinx.io) as a protocol for human and machine readable agreements about permissions for data usage. 

Below are the current permission types. 


|# | Scope | Persist | Visibility | Comments |
|--|-------|---------|-----------|----------|
|1 | Local | No | Code-only | e.g. App uses it in local validation |
|2 | Local | No | Client | e.g. App displays in UI |
|3 | Local | Yes| Private | e.g. App stores private entry to which author must explicitly grant captokens for access |
|4 | Local | Yes| DHT | e.g. Storing a username to DHT |
|5 | Local | Yes| Public | e.g. Is served on non-localhost port |
|6 | Remote | No | Code-only | e.g. can be sent via remote call or used in global validation |
|7 | Remote | No | Client | e.g. can be sent by signal for remote UI display |
|8 | Remote | Yes | Private | e.g. Stored as private entry or in other private DB |
|9 | Remote | Yes | Can reshare privately | e.g. Can copy/send to other apps which do not expose data publicly 
|10| Remote | Yes | Public | e.g. Visible via anonymous web gateway or via Holo hosting |


**_-------- maybe put this next text in an EndNote? —---_**

Understanding terms in the permissions table:

* **Scope:** Local means the same user whose PnP data is being accessed stores it in their local source chain. Remote means the data leaves the local machine like it is sent to another user, published to the DHT, or made visible to the Internet.
* **Persist:** Is the data stored somewhere outside of PnP.
* **Visibility:** What subsystems is the data visible to? Examples: Is it only read by code? Served to a client or UI? Stored to a private entry? Published to the DHT? Made visible to the Internet or wider than the DHT?

**OAuth Gateway: Owning your Universal Login**
Instead of using Google or Facebook as an OAuth provider to unify your logins to different Web2 sites, PnP enables the possibility of being your own OAuth provider. The Holo hosting network will provide an OAuth gateway to respond to web OAuth API requests. Individuals will need to mark which fields will be available to be accessed via OAuth and those will be persisted by the gateway so that you can use OAuth even when your personal device may not be online to respond to requests. The gateway will periodically update its cached data so that updates you make to personal data in your Web3 data management can also propagate to the Web2 sites you use with this OAuth gateway.


#### 3. Claims & Credentials (CnC)

**The Concept of a Verifiable Credential**
Historically, you have needed to get claims or credentials directly from the source, or possibly through a trusted intermediary. Now, cryptographic signatures make it possible to get such information from anyone, including a person who may be the subject referred to in the claim or credential, and yet be certain that the credential has not been modified or tampered with. The W3C has created a standard for constructing and verifying such credentials. 

**Data Provenance: Universally lightweight VCs**
Since all data in Holochain is signed and sequenced in the author’s source chain, any data which includes an assertion which refers to someone or something is already a lightweight verifiable claim. It is already completely tamper-proof and verifiable. The CnC app is designed to help you organize, discover and share both lightweight claims, for use between Holochain apps and also to present credentials in a standardized format for usage with other web apps or platforms.

**Discoverability and Lookup**
Get links on a base

**Selective Exposure and Zero Knowledge**
Ability to provide ZK proofs and Merkle proofs for verification with selectively exposed data 

**Portable VCs (compliant with W3C standard)**
Ability to convert, or to originally commit and persist, VCs in the larger format to make the portable for use in outside systems


### Composing Identity Services for your App

We have outlined the identity tools that Holochain plans to provide. However, we don’t do so prescriptively. These are tools in a toolbox. The way they are used and brought together is going to depend on your particular use case. Following, we’ll start to hint at some of the options you should consider. 

**PKI:** If you distribute your application via the App Store in the Holochain Launcher, then your users will automatically have most of DeepKey’s features provided by the launcher. If your app is set up to be hosted by Holo, your users will get key registration services, but only get key management if they install the DeepKey browser extension to manage their keys. If you distribute your application via a custom executable (like Electron, or Kangaroo) you will need to package DeepKey yourself, and decide whether you want to run your own PKI space or use the launcher’s DeepKey version for compatibility with launcher and hosted users. 

**Key Management:** (included in launcher and Holo via browser extension) We have outlined how key management functions in Deepkey. However, you have the option to develop an application that does not allow for key rotation. You might not want keys to be persistent, like in a chat app (like firechat). Alternatively, you might want an application that doesn’t provide key management so that you can limit that attack surface and simplify onboarding. 

**Key Recovery:** (included in launcher, not in Holo?) If you want DeepKey to help users recover lost keys or restore their keys from a master seed, you will need to prompt the user to save their seed offline, and be sure to use a device seed to derive any keys for applications.

**DID Integrations:** You will need to provide a DID document format along with any custom services or fields that deviate from the minimalist standard data provided by DeepKey

**Sourcing User Data from PnP:** PnP will be used by many users as a UX aid to easily share details across applications and to manage what personal information they share where. However, you can have users store data directly in your app, but then you would need to develop UX for any sort of updating or management of that information you want users to be able to do. Either way, the user would be storing that data locally on their machine (unless it is published out to the app’s DHT for public consumption). 

**Interfacing with existing Vocabularies:** You will need to reference the vocabulary definition and then have your field names for you profile_spec stick to those names as closely as possible to receive the benefits of using 

**Types of Permissions for Identity Data:** If you choose to use PnP, the app must identify what it will do with each field of data that you request in your profile_spec.

**Membership Proofs for Sybil Resistance:** We recommend that apps consider risks associated with getting flooded by fake accounts (Sybils) and provide at least some basic protections for your apps network. In fact, the genesis process everyone goes through when installing your app is your first opportunity to use a lightweight VC as a “Membership Proof.” The proof is optional, but if you want any Sybil protections, it is the place to put it because it is available to be used when validating someone’s address for joining the network (AgentPubKey). A new user might need to show one or more invitations from current users, or they might need to purchase a username, or stake some funds, or do the work of generating a userkey that meets certain criteria. You’ll want to set the bar low enough to make it easy for new users, but high enough to protect your community from spam and unacceptable disruptions..

**Privacy and Placement of Claims:** If your app uses verifiable claims, you’ll need to make a lot of decisions about where to put them and who can see them. Some claims can be held by the subject that the claim is about. But some types of claims (like ratings, reviews, feedback) risk being selectively filtered if you rely on the subject to hold or discover them. Other subjects may be objects, places, or organizations that aren’t running your app so that they could store them. Some types of claims are meant to be quite public, and others rather private to not leak personal user information. You can store credentials as private entries on chains,or in limited access DHTs, or on rather open DHTs (like the CnC app itself). Data can be encrypted, or selectively exposed from private or encrypted entries with ZK proofs or Merkle proofs.

**Trust Graphs:** Some applications have a need for advanced composition of lightweight claims across a social graph. It is quite easy to bolt these features onto your app using [TrustGraph](https://trustgraph.net/) which has been implemented in Holochain. Their app provides computation of social trust graphs based on claims in a simple format called “trust atoms.” 


### Evolutionary Solutions

We don’t know the right answer, we trust if we make it easy for people to mix and match for their needs, good solutions will evolve and gain adoption in the ecosystem


### Closing notes on on why this matters for identity (and the “triangle” )
Conclusion text goes here...

### Additional Resources:

* [https://miro.com/app/board/uXjVMi2WWwA=/?share_link_id=659594844588](https://miro.com/app/board/uXjVMi2WWwA=/?share_link_id=659594844588) 
* [DeepKey spec and code repo](https://github.com/holochain/deepkey)
* [PnP spec](https://hackmd.io/0fz2cLutTz-sE13ev1ukrw?both)
* CnC spec# Decent Identity Composer & Threat Models

## Old Abstract

*Ankur Bannerjee, Arthur Brock, Jack Gretsch, Collin McClain*

This paper proposes that all digital identity systems are made up of three core elements: digital keys, human-readable names or data; and binding mechanisms between them. This mental model can help establish a shared understanding about the options and trade-offs that developers face when building identity solutions.

Using examples from current identity systems, we illustrate how particular design choices made about the three core elements affect the security & privacy of such systems. We explore a non-exhaustive range of options for each of the core elements, and highlight the benefits and trade-offs in each approach.

Finally, we propose a form of pseudocode configuration definition language that can be used descriptively and succinctly model design decisions. This configuration definition language is also machine-readable, and could be used to configure the set-up and operation of components of decentralized applications.
