# Demo Afternoon

## creds.xyz: Privacy-Preserving Decentralized Reputation (Ankur)

Most traditional use cases such as education & financial credentials are RARELY used!

So decided to concentrate on something much more common: social reputation. 
* Social handles may or may not be related to real names
* Impersonation is a big problem!

Every time you join a new social network, your social reputation starts from zero. It shouldn't!

That's the problem that creds.xyz seeks to solve!

VCs, can verify attendance at events, can link it into social media events.

At [app.creds.xyz](https://app.creds.xyz/).

## A Credential Profile Comparison Matrix: The Next Generation (Mirko)

RWOT11 saw the production of a [profile comparison matrix](https://github.com/WebOfTrustInfo/rwot11-the-hague/blob/master/final-documents/credential-profile-comparison.pdf) for many sorts of verifiable credentials.

It has now been [moved to GitHub as JSON schema](https://github.com/openwallet-foundation/credential-format-comparison-sig) that can be automatically displayed! It supports 3 million combinations, so that you can choose exactly what your needs are, and then see the profiles that meet these needs.

## Digital Product Passport (Sebastian)

You can have digital passport for products.

For this to work, a QR code pretty much needs to show a URL.

Can lead to a page that fetches verifiable credentials for the product and displays them all, including info on who issued them, full verifiable presentation, etc. Can aggregate VCs from different issuers! Can have private VCs! 

The unique thing here is identity of PRODUCT, not identity of PEOPLE, and this is a use case where the product probably doesn't have a wallet and so isn't a holder. 

Includes a [GS1 Digital Link](https://www.gs1.org/standards/gs1-digital-link).

## Godiddy (Zaïda)

Hosted platform that makes it easy for SSI developers and solution providers to work with DIDs.

A playground for creating, updating, resolving, deactivating, and searching `did:ion` DIDs.

At [GoDiddy.com](https://godiddy.com/).

Info on DID usage at [stats.godiddy.com](https://stats.godiddy.com).

## did:directory (Joe)

A directory of did methods based on what's registered with W3C.

Easily searchable! Easy to alos add DID name to URL.

Simple listings, but you can claim you entry to add info if you have W3C contact email!

At [diddirectory.com](https://diddirectory.com/)

## Cheqd Payment Rails (Ankur)

Private company use cases have high costs for implementation of VCs, and it doesn't help the issuer, it just helps the customer to leave!

Hence, Payment Rails, which require payments to unlock encrypted status lists. Verifier can see a VC is valid, but if they want to see its current status (revoked or not), they have to make a payment!

For more see [Cheqd's Credential Service API](https://credential-service.cheqd.net/swagger/).
