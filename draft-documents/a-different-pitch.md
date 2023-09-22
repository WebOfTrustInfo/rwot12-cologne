# Leading with a Different Pitch: Data Portability, Rather Than Privacy

## Authors

- [Ankur Banerjee](https://twitter.com/ankurb), CTO/Co-Founder at [Cheqd](https://cheqd.io) & [Creds.xyz](https://creds.xyz)
- Jack Gretsch, [Legendary Requirements](https://legreq.com/)

## Introduction

The year is 2004. Facebook launched what would later symbolize the most easily explainable dilemma of the digital age. A centralized platform connecting people around the world by sharing experiences and ideas that would eternalize bits of data on a server “somewhere.” Other technology giants like Apple, Amazon, Google, and even Netflix collect our data too. The list of tech companies adopting this practice doesn’t stop there: it extends to “Big Pharma”, or banks, governments, and even non-profits. All of those contributors to “Big Data” in the current year of 2023 is the result of people disclosing their personal information across a recordable, traceable medium that they’ve come to rely on in a growing number of ways that afford convenience, efficiency, and exploration.

In 2015, the first Rebooting the Web of Trust (“RWOT1”) conference convened to protect the autonomy of user data privacy on the internet – from each other, and from Big Data. They developed the Self-Sovereign Identity (“SSI”) model to propose a utopian solution to the dystopia of the eery, heavily-monitored era of [surveillance capitalism](https://en.wikipedia.org/wiki/Surveillance_capitalism). Trust was difficult to bestow to anonymous entities receiving personal information when it was consistently exposed and monetized by the known entities of Big Data. 

Returning to the present day of 2023, RWOT12 concludes yet another annual summit where many attendees champion for the next iteration of standards that could/should be adopted to achieve a decentralized web, where users are in control over who receives their data and how much of it. Some argue that eight years of collective effort is a sign of momentum and continued interest from authorities in this space, and the integrity and tenacity needed to battle the decisive, bureaucratic process of modifying regulations and standards.

Others argue that like with any democratic system, which RWOT is building in terms of SSI, there needs to be reflection on what’s working and what’s not working. After nearly a decade, this paper looks to spark a series of constructive discussions on why the utopia of SSI remains vastly distant from widespread adoption.

**To be clear, this paper is not proposing that self-sovereign identity or its end-goals of improving individuals’ data autonomy and privacy should be abandoned.** We celebrate the massive gains the SSI community has won against the current, entrenched models of technology & data. At the same time, the paper explores topics that could pragmatically improve adoption of SSI in the next 1-5 years.

## Self-sovereign identity is _much_ wider than _just_ DIDs and Verifiable Credentials

### What are the end-goals of an _ideal_ world where SSI is widely adopted?

If we boil down the key end-goals of self-sovereign identity, they may be widely-understood as:

1. Ownership and control of data
2. Only giving away the _minimum_ amount of data necessary
3. Hacking and data breaches
4. Replacing usernames and passwords

The SSI community is diverse, and it is presently too focused on the Decentralized Identifiers and Verifiable Credentials components of a decentralized web that rests in a speculative future. This paper is not questioning the solvency of the SSI community, and not suggesting it abandon the privacy goals that can be made possible by a widespread adoption of DID methods and VCs. However, it is suggesting that the community remain aware that its desired changes to the level of autonomy in data privacy requires a catalyst large enough to perpetuate incentive for Big Data to react. It needs to…

## There’s too much focus on selective disclosure

A significant narrative thrust in the self-sovereign identity world has been increased privacy of individuals, who in an utopian world would be able to be far more selective about what data they are able to share, with whom, and for how long. For instance, one of the big “a-ha!” moment explanations is the concept of “selective disclosure”, for example, just being able to reveal whether your age is above or below 18 / 21 / 25 years old (usually in the context of alcohol licensing).

Selective disclosure for age-restricted products is a great example, but far too often it gets extrapolated to mean that this could be done for _all_ kinds of information. There’s also a widespread impression that is given to people that selective disclosure is _baked in_ and _already present_ in SSI products and services.

**This is a big paradox that we need to deal with, in the SSI community**. On one hand, the concept of selective disclosure is so simple and powerful that it wins over people who might already be inclined to use privacy-preserving technologies. On the other, the _actual_ usage of selective disclosure may not immediately be available in the near future due to technical and practical limitations.

### Selective disclosure is _not_ always technically supported

#### Some widely-adopted digital credential formats do not support selective disclosure

Selective disclosure is only technically feasible in _some_ specific credential formats, e.g., AnonCreds. The far more widely adopted [Verifiable Credential JSON Web Tokens](https://www.w3.org/TR/vc-data-model/) (VC-JWTs[^1]) did not have this capability, until [Selective Disclosure JWTs](https://datatracker.ietf.org/doc/draft-ietf-oauth-selective-disclosure-jwt/) (SD-JWTs) started getting discussed in late 2022 / early 2023 in the early stages of standardisation. [JSON-LD Verifiable Credentials with BBS+ Signatures](https://docs.modernising.opg.service.justice.gov.uk/research-development/articles/verifiable-credentials-bbs/) also have this capability, but are only supported in a select range of software development kits[^2] (SDKs).

#### Many widely-adopted digital credential formats do not support selective disclosure

Selective disclosure with zero-knowledge proofs (ZKP) are limited in the types of data that can be redacted or selectively disclosed. The “age above/below 18 or not” works great because there’s an easy, finite number to calculate. This is not true for other kinds of data. For example, selectively disclosing your first and middle name, but not last name, cannot be boiled down to a mathematical number threshold. While there are ways in which SD-JWTs and JSON-LD with BBS+ _can_ enable such scenarios, it’s far more complex than uses cases which can be boiled down to numbers/counts. [Mobile Driver’s License (mDL)](https://en.wikipedia.org/wiki/Mobile_driver's_license) credentials _could_ support selective disclosure; in practice, however, this is limited to the age above/below use cases.

### Practicality and regulations may not permit selective disclosure

#### Pure “yes / no” selective disclosure is incompatible with regulations in many uses cases

Let’s take an example of Know Your Customer (KYC) checks in the banking/financial services industry. In some of the popular discourse around SSI, there’s a notion that the following use case would be possible _and_ allowed:

1. Ankur opens a bank account with HSBC. Since this is his first time opening a bank account, HSBC conducts a KYC check.
2. HSBC then issues Ankur a digital credential that’s the equivalent of “Yes, Ankur has been KYC’d by HSBC (on this date)”.
3. After a few months, Ankur wants to get a loan from Barclays. Instead of having to provide documents to carry out yet another KYC, Barclays is happy to take the digital credential issued by HSBC that “proves” he was KYC’d by them and uses that for the KYC/ID check part of assessing a loan.

This scenario **is simply not allowed under current legal regulations** for KYC checks in most jurisdictions. Taking the UK jurisdiction as example, the [Good Practice Guidelines (“GPG-45”) for proving and verifying identities](https://www.gov.uk/government/publications/identity-proofing-and-verification-of-an-individual/how-to-prove-and-verify-someones-identity) (which is the official guidance that banks follow) would _not_ allow this form of “KYC-reliance” where Barclays can rely on HSBC’s “green tick”. The liability is _always_ on Barclays to ensure it had a satisfactory level of information to make its own _independent_ decision. Similar guidance applies in most other jurisdictions, besides the UK.

The primary purpose of KYC regulations are intended to prevent money laundering, fraud, organised crime, and sanctioned individuals/organisations. If banks were to rely on just a “green tick” equivalent, it could cause cascading failures where if a bad actor slipped through the net _once,_ they continue to be able to open accounts at other organisations.

**This does not mean digital credentials are not useful in use cases like KYC**. While a “green tick” won’t satisfy the needs of the actual consumers of KYC, i.e., banks, having the data needed for KYC via digital credentials in tamper-proof format _is_ valuable because it speeds up the KYC check/onboarding process, and less susceptible to be based on tampered data compared to physical documents.

Here’s a modified version of the scenario above, which would be more in-line with existing regulations:

1. Ankur opens a bank account with HSBC. Since this is his first time opening a bank account, HSBC conducts a KYC check.
2. HSBC then issues Ankur a digital credential **with the actual details used to conduct the check**, such as name, date of birth, address, source of that information (e.g., these details were extracted from a drivers license, passport, etc).
3. After a few months, Ankur wants to get a loan from Barclays. Instead of asking Ankur to upload a picture of a physical passport or drivers license, Barclays **uses the digital credential issued by HSBC with the _actual_ details normally needed to conduct KYC**.

#### Why would banks, e-commerce, employers etc need more than the bare minimum personal information? Why can’t we aggressively apply selective disclosure in these use cases?

A question that privacy-maximalists ask at this point is _“Why does a bank need to know my name, date of birth, address, etc., anyway?! Why can’t they accept that I’m a real person and leave it at that?”_ Banks _have_ to ask extensive personal information for a multitude of reasons:

1. **Name**
    1. Preventing fraudsters from scamming users into sending funds to unintended recipients. (See: [“authorised push payment (APP)” scams](https://www.psr.org.uk/our-work/app-scams/).)
    2. Detecting known sanctioned individuals, money launderers, organised crime, and terrorist organisations from being able to transfer funds. (See: [United Nations sanctions list for individuals and entities](https://www.un.org/securitycouncil/content/un-sc-consolidated-list), [US OFAC sanctions list](https://ofac.treasury.gov/ofac-sanctions-lists), [UK sanctions list](https://www.gov.uk/government/publications/the-uk-sanctions-list))
    3. Reporting transactions above certain amounts to tax authorities and law enforcement, to track money laundering and tax avoidance.
2. **Date of birth**
    4. Checking eligibility of the user for financial products, e.g., disallowing users below 18 to sign up. (This _could_ use selective disclosure.)
    5. Disambiguating users with similar names from each other.
3. **Address**
    6. Some users prefer to get statements and communications by postmail, rather than electronically. This is an inclusive-by-design choice, especially for older users who may not be as comfortable with online banking, or users with different accessibility needs (such as requiring communication in large text, Braille, etc.).
    7. Sending formal notices/statements. While these can sometimes be sent electronically, in some cases (especially legal disputes, etc.), formal notices can only be served via post.
    8. User closes their account (perhaps exercising their right of withdrawal under privacy laws such as GDPR), and therefore there’s no valid electronic communication channel remaining.
    9. Checking for eligibility due to residency/jurisdiction requirements, e.g., non-residents not being allowed to open accounts.

The general takeaway is that minimal data can be collected by banks if all them were “good” users. In practice, many of them are “bad” users, and _this_ is what pushes the needle towards more data needing to be collected.

Let’s take e-commerce, instead of banking as an example. These are a few reasons why an e-commerce merchant needs personally-identifiable information:

1. **Name**: They need to know _whom_ to direct the package to. This is especially important in multi-dwelling units/buildings. [Knowingly opening someone else’s mail is also a crime](https://www.fosters-solicitors.co.uk/insights/is-it-legal-to-open-someone-elses-mail/) in many jurisdictions.
2. **Address**: Needed to physically deliver the package.
3. **Email address/Phone number**: Getting in touch with the shopper to offer updates on the purchase, and in case there’s problems during delivery.

### Should we abandon selective disclosure?

**Absolutely not!** Selective disclosure is a powerful mechanism to reduce mass surveillance, user tracking, and unnecessary data collection by companies. **However**, we need to correct the misconception that many newcomers to SSI walk away with, that using SSI credentials will result in _no/minimal personal data being shared in every use case_ because the practicalities and regulations in many uses simply do not allow that.

### Key takeaways

1. Until the actual laws/regulations change, in many industries/jurisdictions, selective disclosure is simply incompatible. We can/should campaign to change the laws to reduce what’s considered “necessary” to collect, but in meantime, pragmatically look at the actual needs of the organisations that would need to adopt SSI and what kind of data they need to fulfill their business processes.
2. If we _don’t_ correct common misconceptions that newcomers to SSI have about _how much less data they need to share_ in the next 5-10 years of adoption, they might get disillusioned when they find out that they are sharing the same/similar amount of data as they currently do. This disillusionment could prematurely hurt growth, therefore hurting the end-goals of SSI.

## Leading with a _different_ pitch: data portability, rather than privacy

Lost sight of “where possible” when talking about reducing where the data is collected (which personal data and by whom).

Recognizing that our data will not disappear, and that near-term goals should include the prevention of misuse of our data (not to scrutinize the ethics of monetizing our data, but to focus on how we can securely exchange our data. Not to reduce the data, but to control who sees/uses it. Reduce/eliminate the impact of hacks/leaks, but until then clean up the transmission of existing data – digital credentials with a focus on portability/convenience rather than omission/redaction).

<!-- Footnotes themselves at the bottom. -->
## Notes

[^1]: JWTs can be pronounced as “jots” (as in “jots down”), or spelling out each letter.

[^2]: An “SDK” is how an application developer would build the capability to read/write SSI credentials.
