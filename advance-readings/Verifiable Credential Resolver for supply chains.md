# Verifiable Credential Resolver (VCR) for supply chains

By: Mirko Mollik
Date: Jul 24, 2023
Version: 0.1

# Abstract
Web 3.0 is based on a decentralized approach. In most cases the holder is storing the credentials and is presenting them on demand. But objects like a tire from a car can have an identity, but no CPU to present credentials on their own. It gets more challenging when the ownership of the tire changes, together with the responsibility of the credential availability.

# Current problem
We are able to give an object a did, where we can include more information in the did document like a service endpoint. `did:key` or `did:jwk` are not designed for this, since they only store key material for verification methods, but no services. One solution could be `did:web`, it scales well, allows to add more information to the did document and is easy to implement. But `did:web` does not fulfill the requirement of a change of the ownerchip:
A product with the did: `did:web:product13422.companyA.com` cannot be transferred to `companyB.com` since did:web is based on domains names.

So did methods with an independent identifier are preferred, like DLT based approach: e.g. `did:eth`, `did:indy`, `did:trust`. There the identifier of the did document is not linked to the first controller aka the creator of the product. We are for example able to manage the owner of the did document by the [controller](https://www.w3.org/TR/did-core/#did-controller) attribute. But most of the DLT approaches do not scale when millions of products need to be managed because of the big amount of transactions.

So we have the problem that placing the resolver right in the did id makes a separate registry no necessary anymore. But then we are dependent on the first stakeholder to provide the information even when it is not the owner anymore. And on the other hand we have a big registry, that needs to scale for thousands of enterprises.

# Solution
Both solutions could fit depending on the use case. For cases where the lifetime of a product is short and therefore the requirement of the availability of the verifiable credentials systems with a single point of failure/control could be worth the risk. In case of long living products, a registry that is storing the simplest information could fit for the job. The minimal attributes are:
- unique identifier of the product
- endpoint where to query the verifiable credentials (this could only be one endpoint, where the verifier can get a list of multiple endpoints to request them)
- the current owner that can update the endpoint

Credential formats like SD-JWT or W3C-VC are not bound to their storage, only to the subject, in this case the product. So moving the credentials to another storage provider and updating the endpoint should work.


# Open Question
- how many use cases involve a case where the ownership of a product changes so `did:web` is not made for the job
- what current validation logic avoids big scalability for this problem when using a DLT approach
- how many extra information can be appended to the id for better performance but respecting the max length for some use cases
