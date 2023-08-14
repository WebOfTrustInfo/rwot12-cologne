# Verifiable Presentation of Linked Claim Graph

**Authors:**

Golda Velez (Cooperation.org) <gvelez17@gmail.com>,
Phillip D. Long (T3 Innovation Network) <pl673@georgetown.edu>

## **Introduction**:

That Verifiable Credentials are signed by a DID has value, but to actually evaluate the credibility of a VC 
it is necessary to know something about the DID, essentially to embed the VC in a social graph.

The LinkedClaims vocabulary is designed for exactly this, for easily adding validations to existing claims 
or to entities such as DIDs, in a standard and minimal vocabulary, as well as hashlinking proof documents with a multibase hash.

A Verifiable Presentation of not only a single claim, but hashlinked supporting documents and signed claims validating the original, 
allows the user to evaluate not only the fact of a signature but to estimate the credibility of the claim.

## **Implementation**:

Given a set of related claims retrieved via GraphQL, the Verifiable Presentation mechanism must not only verify each signature individually, but 
validate the relationships of the claims and the multibase hashlinks to the proof documents.

This is actually quite straightforward since the claims are linked by subject, object or source by address.  If the address is a Ceramic stream,
then the validation is automatic on retrieval, as the stream document is already anchored to a blockchain using a content hash.

Otherwise, a multibase hash is required for validation that the contents of the referenced claim or document have not changed.

## **Benefits**:

The ability to retrieve a linked graph of claims enables a credibility estimation that is not possible from a single claim in isolation.

## **Example**:

Simple example, is this claim with a PDF as evidence

```
{
  "@context": [
    "https://www.w3.org/2018/credentials/v1",
    "linked-claim-context.json",
    "schema-mock-context.json",
    "impact-mock-context.json"
  ],
  "type": ["VerifiableCredential"],
  "issuer": {
    "id": "did:employee678",
    "name": "Angel Smith"
  },
  "issuanceDate": "2022-12-01T00:00:00Z",
  "credentialSubject": {
    "id": "did:agency987",
    "type": ["LinkedClaim", "Impact"],
    "effectiveDate": "2022-12-01", 
    "statement": "BEMA helped 200 individuals repair their homes after Hurricane Zeta, with ongoing work on at least 50 locations as of this date.",
    "impactClaim": {
        "type": "ImpactClaim",
        "id": "cid:09871234324",
        "impactType":"direct"
    },
    "source": {
         "type": "ClaimSource",
         "id": "https://recoveryagency.com/2022/ReportDetail.pdf",
         "digestMultibase": "QmWATWQ7fVUCs9KuU6XvTkjhP8m8s1ek6G8a5XbtWMEoLb",
         "sourceType": "document",
         "howKnown": "Published to web",
         "dateObserved": "2022-12-01"
      }
    }
}
``` 

In this case, the Verifiable Presentation would not only validate the signature on the VC but also would verify if the source is retrievable and if the hash value is correct. 

## **References**:

[1] http://cooperation.org/credentials/v1/

[2] https://github.com/WebOfTrustInfo/rwot11-the-hague/blob/master/final-documents/composable-credentials.pdf

[3] https://datatracker.ietf.org/doc/draft-multiformats-multibase/
