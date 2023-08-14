# Verifiable Credentials on the Ceramic Network

**Authors:**
Golda Velez (3box) <golda@3box.io>

This may possibly become a future CIP (Ceramic Improvement Proposal) https://github.com/ceramicnetwork/CIPs

## **Introduction**:

ComposeDB models are similar to Verifiable Credentials in that they are a structured set of fields signed by a DID.  

They have the additional properties of being content-addressable at a CID, 
and benefiting from the Ceramic protocol capability of updating the contents at the original content-addressed address. 

Providing a native storage and retrieval mechanisms for verifiable credentials would be of value to adoption and use in the decentralized web.

## **Implementation**:

If we can convert a ComposeDB document to and from a valid Verifiable Credential including signature, this would provide a powerful decentralized 
storage and update system for VCs.

The challenge is in keeping the signature valid across the transformation. Three approaches will be evaluated:

1)  The brute force solution to this is simply to store the entire VC blob as a 
data field in a ComposeDB model, and simply signing both the original VC and the composedb document at the same time via a tool.

2) A second method that also leans on a tool is to make a model that corresponds to the VC fields, and storing the signature in a "proof" or other field.  This still requires 
that the ComposeDB and VC be signed independently (possibly simultaneously on creation)

3) An ideal method would be if the signature could be reused between VCs and ComposeDB models, so that a ComposeDB model could be reconfigured into a valid and 
signed verifiable credential.  The question is whether this can be possible, if there is a combination of fields that actually would create a valid signature 
across both specifications.  This is uncertain and will be the initial focus of the work.  If possible, this will likely result in a CIP.

If it is determined that (3) is not possible, then the project will focus on a tool that implements method (1) or (2)

## **Example**:

A simple example of a permissionless claim might be a witness to an accident, that has already been reported on some classical website:

```
{"@context": ["https://www.w3.org/2018/credentials/v1",
              "http://cooperation.org/credentials/v1/"
             ],
 "type": ["VerifiableCredential", "LinkedClaim"],
 "issuanceDate": "2023-08-02T21:36:59Z",
  "credentialSubject": {
    "id": "https://accidents.example.com/reports/accident-1",
    "type": ["LinkedClaim"],
    "claim": "witnessed",
    "statement": "Truck ran a red light...",
    "effectiveDate": "2023-08-02",
    "source": {
       "id": "did:me123",
       "sourceType": "firstHand",
    }
  }
}
``` 

Similarly, such a claim could be entered using the LinkedClaim public model on ComposeDB. 

In this case the signed blob is publicly available on the Ceramic network, such as on Cerscan: https://cerscan.com/mainnet/stream/kjzl6kcym7w8y9njlcne78r3y9dum8aplz1kn6k3wkydik2vqle7f4zyedmmicv

or on the server where it was originally made https://ceramic.linkedtrust.us/api/v0/streams/kjzl6kcym7w8y9njlcne78r3y9dum8aplz1kn6k3wkydik2vqle7f4zyedmmicv

and the structure is similar, but not identical, to the Verifiable Credential format

```
{
  "streamId": "kjzl6kcym7w8y9njlcne78r3y9dum8aplz1kn6k3wkydik2vqle7f4zyedmmicv",
  "state": {
    "type": 3,
    "content": {
      "claim": "witnessed",
      "source": {
        "howKnown": "FIRST_HAND",
        "sourceID": "did:me123"
      },
      "statement": "Truck ran a red light...",
      "subjectID": "https://accidents.example.com/reports/accident-1",
      "effectiveDate": "0023-08-02"
    },
    "metadata": {
      "controllers": [
        "did:pkh:eip155:1:0x3176dd992793ae9c50b92fe09e1bb7cccdff8016"
      ],
      "model": "kjzl6hvfrbw6c7f8zr4bdyzfumj7hv7r9i7dbu57isrzezqjuetkum2885p9agc"
    },
    "signature": 2,
    "anchorStatus": "PENDING",
    "log": [
      {
        "cid": "bagcqcerax5wzvog27fnaipfpuju4delhu72whbxj5oksrvg3pni5mszysbxq",
        "type": 0,
        "expirationTime": 1692590344
      }
    ],
    "doctype": "MID"
  }
}
```

The Ceramic format has some additional fields defining the model, but would seem largely compatible with the verifiable credential format.

The question is, whether fields can be defined on both the Verifiable Credential and Ceramic model side, to make the signature portable across the two.

## **Benefits**:

If this is successful, then it provides an immediate decentralized storage and retrieval mechanism for sharing verifiable credentials in a public data feed.  

# **References**:

[1] https://github.com/WebOfTrustInfo/rwot11-the-hague/blob/master/final-documents/composable-credentials.pdf

[2] https://cips.ceramic.network/CIPs/cip-137
