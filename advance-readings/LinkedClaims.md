# Verifiable Presentation of Linked Claim Graph

**Authors:**

Golda Velez (Cooperation.org) <gvelez17@gmail.com>,
Phillip D. Long (T3 Innovation Network) <pl673@georgetown.edu>

# **Introduction**:

That Verifiable Credentials are signed by a DID has value, but to actually evaluate the credibility of a VC 
it is necessary to know something about the DID, essentially to embed the VC in a social graph.

The LinkedClaims vocabulary is designed for exactly this, for easily adding validations to existing claims 
or to entities such as DIDs, in a standard and minimal vocabulary, as well as hashlinking proof documents with a multibase hash.

A Verifiable Presentation of not only a single claim, but hashlinked supporting documents and signed claims validating the original, 
allows the user to evaluate not only the fact of a signature but to estimate the credibility of the claim.

# **Implementation**:

Given a set of related claims retrieved via GraphQL, the Verifiable Presentation mechanism must not only verify each signature individually, but 
validate the relationships of the claims and the multibase hashlinks to the proof documents.

This is actually quite straightforward since the claims are linked by subject, object or source by address.  If the address is a Ceramic stream,
then the validation is automatic on retrieval, as the stream document is already anchored to a blockchain using a content hash.

Otherwise, a multibase hash is required for validation that the contents of the referenced claim or document have not changed.

# **Benefits**:

The ability to retrieve a linked graph of claims enables a credibility estimation that is not possible from a single claim in isolation.

