# DID Web Method 2.0: Using DID Traits To Improve on `did:web`

## Authors
* Dmitri Zagidulin <dzagidulin@gmail.com>
* Benjamin Goering <ben@bengo.co>
* Juan Caballero <jcaballero@centre.io>

## Introduction

Original `did:web` Benefits:

* Easy to understand and implement (good beginner method)
* Leverages investment in domain name trust/brand
* Benefits from DID Document data model standardization and digital signature tooling (that expects DIDs)

Enhancements inspired by prior art:
- did:web 1.0 implementer experience
- did:plc and other DID Methods

## DID Method Traits

Link to Wayne et al's 2022 post, https://blog.spruceid.com/upgradeable-decentralized-identity/ . Not to be confused with [DID Method Rubric](https://www.w3.org/TR/did-rubric/) -- Traits deals specifically with did document implementation properties, whereas Rubric considers the broader context.

## Enhancements to `did:web`

This method adds the following traits and enhancements to the `did:web` method. Due to overwhelming developer and policy-maker feedback, we're proposing creating a separate DID Method rather than adding complexity to the existing `did:web`.

### Recovery Keys and Pre-Rotation Keys
`"recover": "[hash of the secret recovery key]"`

similar to did:plc and KERI's pre-rotation key

Discuss introducing another verification relationship (in addition to `authentication`, `assertionMethod` etc) versus only including the _hash_ of the pre-rotation/recovery key.

### Self-Certifying Hash in DID URL

What to hash? There's the Data Integrity style approach, where you define excluded fields (`proof` and `id`) and hash the rest of the DID document (JCS canonicalized, of course).

Alternative - did:plc style - hash only the Recovery key.

In either case, the resulting hash gets added to the DID URL fragment. Example:

```
did:webs:example.com#hash=12345
```

It can also be added to the DID `id`, like so:

```
{
  "@context": [
    "https://www.w3.org/ns/did/v1",
    "https://w3id.org/security/data-integrity/v1"
  ],
  id: "did:webs:example.com#hash=12345",
  verificationMethod: [ ... ],
  ...
}
```

Combined with Backwards Links, allows verifier to make risk assessments based on key age and rotation history.

Discuss keeping the original/genesis hashlink in the `id` regardless of updates.

### Backwards Links and Versioning

A DIY append-only web ledger.

Look at prior art (did:peer style update operations).

Discuss `did:plc`'s separation of DID Document _update operations_ at a separate URL, vs embedding the update history in the DID Doc itself.

New DID Document property, `previous`, an object that contains a link to the previous version of the DID document (using the self-certifying hash URL discussed above), as well as a signature over that previous URL using the Recovery Key.

Initial DID Document has `"previous": "self"` link - the "genesis" document.

Subsequent revisions to the DID Document -- link to the previous version, signed by the Revocation key.

```
{
  "@context": [
    "https://www.w3.org/ns/did/v1",
    "https://w3id.org/security/data-integrity/v1"
  ],
  "id": "did:webs:example.com#hash=789",
  "previous": {
    "id": "did:webs:example.com?hash=12345",
    "recoveryProof": "<signature of the previous.id, signed by Recovery key>"
  }
  ...
}
```

### Revocation - Tombstones vs Deletion

Currently, to revoke a `did:web` DID, the document is deleted from the web server.
Downside: verifier cannot differentiate an on-purpose revocation or deletion from a server outtage.

Also, explicit tombstones (marking a DID as revoked) allows for "moved to" redirects, in case of migration.

### Certificate Transparency Log Style Observers

Link to https://certificate.transparency.dev/
Link to https://datatracker.ietf.org/wg/keytrans/about/ (in progress)

Discuss append-only cryptographically secured logs combined with community Monitors.

### Signed DID Documents

Discuss the `did:web` trust model - are signatures redundant because the root of trust is the web server hosting the DID Document?

However, it's really web server plus the _private keys_. In single-person or small organizations, yoking together the web server admin and the holder of the private keys works well.

But in many use cases and organizations, it's useful to separate the authority of the private key holder (typically, senior leadership) from the person uploading a file to a website (rank and file IT).

### Where to Put the Metadata

What metadata is worth recording? Mention the history of the `created` and `updated` timestamps.

Now, DID Document signatures and `previous` proofs can hold the relevant timestamps.

### Handles and Domain Verification Using `alsoKnownAs`

Usefulness of two-way links (mention ActivityPub actors / Fediverse, did:plc, etc).

Mention NNS (the Name Name System)?

### `.well-known` and Default Resolution

Surprising discovery - in many deployments, site owners _are not able to_ create the `.well-known` folder (forbidden by CMS / hosting panel policy).

Recommend instead use `/did.json` top level location.

### Leveraging DNS for Discovery

Mention `did:dns` and DNS-to-DID binding methods.

## Example DID Document

- Put it all together

## Next Steps

- Naming is hard (`did:webS` - S is for Secure)
- Propose as work item to CCG
