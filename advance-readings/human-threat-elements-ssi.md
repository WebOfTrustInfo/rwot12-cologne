# The Human Element: Threats to Trust in Self-Sovereign Identity Systems

## Author

[Ankur Banerjee](https://twitter.com/ankurb), CTO/co-founder at [cheqd](https://cheqd.io)

## Context

The adoption of Self-Sovereign Identity (SSI) systems, which empower individuals with control over their own digital identities, has garnered substantial attention in recent years. While technical security measures are vital, it is equally important to consider the human elements that can compromise trust in SSI-based identity systems. I would like to explore the potential threat vectors associated with human behaviour, highlighting the critical need for a holistic approach to SSI security.

## Potential human factors that compromise trust

### Phishing and Social Engineering

Human susceptibility to phishing attacks and social engineering remains a significant concern in SSI systems. Malicious actors may exploit trust relationships, impersonate trusted entities, or manipulate individuals into disclosing sensitive information. An example of these are confidence scams dubbed "[pig-butchering](https://www.forbes.com/sites/cyrusfarivar/2022/09/09/pig-butchering-crypto-super-scam/)", where scammers use persuasion techniques to extract large sums of money from victims.

### Impersonation of issuers/verifiers

Decentralized Identifiers (DIDs) or other technical measures for transport/app layer security for SSI exchange on their own do not achieve human trust. [Copycat or spoofed websites](https://www.which.co.uk/consumer-rights/advice/how-to-spot-a-copycat-website-a4iDh0D1VIP7) already present challenges where users could be fooled into thinking they are interacting with, say, a bank when they are actually not. Other examples over the past few years include [delivery text scams](https://www.bbc.co.uk/news/newsbeat-57654967) and [authorised push payment (APP) scams](https://www.psr.org.uk/our-work/app-scams/).

These problems are further exacerbated by the fact that most DIDs are strings of garbage letters/numbers, which do not immediately make whether a connected party in SSI context is a scammer or not. An example of these are [IDN homograph attacks](https://en.wikipedia.org/wiki/IDN_homograph_attack) which can create URIs that are visually identical to the English alphabet, but are in fact using characters from other languages.

### Just giving your account details to someone

Previous RWOTs and industry research has focussed a lot on problems such as holder-binding (sometimes using biometric means). However, these measures, at best, are limited to binding to a *device* or a *key on the device*. It does not prevent someone (a holder) from just handing over their device to someone else, or passing along their account / recovery details. These are common behaviours among family members or partners, as demonstrated by [widespread account sharing on Netflix](https://time.com/6223415/netflix-password-sharing-crackdown/) or even [password managers offering shared vaults](https://security.stackexchange.com/q/234747/3139).

### Credential Loss and Recovery

Users may lose access to their SSI credentials, either through device loss, data corruption, or forgetting access keys. Ensuring user-friendly and secure recovery mechanisms is essential to prevent permanent identity loss and maintain trust.

Credential recovery is important since issuers may no longer exist (e.g., previous employers who've gone bust) as well as for more sombre reasons such as the death of a family member. Large online services such as [Apple iCloud offer Legacy Contact recovery](https://support.apple.com/en-us/HT208510), but these could also be compromised to carry out account takeovers instead.

### Consent and Data Sharing

Users must grant consent for sharing their verifiable credentials. Misunderstandings, coercion, or exploitation in consent processes could result in data misuse, undermining trust. Implementing transparent and user-centric consent mechanisms is vital.

Consent isn't *real* consent if it [turns into how GDPR cookie consents work](https://www.wired.co.uk/article/gdpr-cookie-consent-eprivacy). Users clicking "allow all" (to release SSI credentials) is not real consent; this will proliferate nag screens and might return back to status quo while giving the illusion of consent.

### Identity Correlation and Profiling

Even with pseudonymity, malicious actors can attempt to correlate and profile users based on their online activities, thereby violating privacy and potentially leading to identity theft. Strong data protection and minimization practices are essential.

In conjunction with above, while standalone credentials might not reveal correlatable information, large wallet providers or issuers might be able to work around such protections (dubbed as the "[mosaic effect](https://blogs.icrc.org/law-and-policy/2021/02/09/mosaic-effect-revelation-risks/)"). History shows how [ad networks worked around initiatives such as app tracking blocks in iOS](https://blog.hubspot.com/marketing/how-advertisers-are-navigating-ios-14)

### Credential Fraud

In SSI systems, there can be a wide range of issuers, which opens the door to fraudulent claims. While a credential itself may be trustworthy, the weakest link is whether someone can be bribed into issuing [cryptographically tamper-proof credentials with falsified data](https://www.theguardian.com/money/2022/nov/24/100-people-arrested-ispoof-uk-biggest-investigation). There is [a long history of ID document forgery](https://en.wikipedia.org/wiki/Identity_document_forgery), which will also inevitably surface with SSI systems.

### Social Pressure and Peer Influence

Social dynamics can exert pressure on individuals to share their SSI data against their will or better judgment. Designing SSI systems with user-centric controls and anti-coercion mechanisms is crucial.

Services could [simply bribe users to share everything, like Worldcoin did during testing](https://www.technologyreview.com/2022/04/06/1048981/worldcoin-cryptocurrency-biometrics-web3/) (and still continues to do so).

### User Adoption and Usability

Complex user experiences and technical jargon can deter users from embracing SSI systems. Low adoption rates could lead to trust issues due to a lack of critical mass. Ensuring user-friendly interfaces and clear communication is essential. Security could be compromised by a [demonstrated history of bad password practices](https://blog.lastpass.com/2021/01/7-bad-password-habits-to-break-now-2/).

## Conclusion

While the technical aspects of SSI security are undoubtedly significant, understanding and addressing human-centric threat vectors are equally vital for the success of these systems. Building trust in SSI-based identity systems requires a multifaceted approach that combines technical safeguards with user education, user-friendly interfaces, and robust consent mechanisms. As we navigate the path toward a more decentralized and self-sovereign digital identity landscape, the human element must remain at the forefront of our considerations to ensure the integrity, privacy, and trustworthiness of these systems.

I would love to model out these and other potential human factors, using ["red team / blue team" techniques used in cybersecurity / war-gaming](https://en.wikipedia.org/wiki/Red_team) to identify factors and potential solutions.
