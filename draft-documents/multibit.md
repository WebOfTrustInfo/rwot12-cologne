---
title: '[]{#_dmaqng206pn .anchor}Multibit Status List Tradeoffs'
---

Joe Andrieu [[joe\@legreq.com]{.underline}](mailto:joe@legreq.com)

Manu Sporny
[[msporny\@digitalbazaar.com]{.underline}](mailto:msporny@digitalbazaar.com)

Abstract
========

Developers should think carefully when choosing a Status List
configuration, as exposing multiple correlated states introduces
significant risk of unintended inferences and resulting privacy
problems.

Status Lists are used with Verifiable Credentials to provide a
privacy-enabling mechanism for revocation and suspension. Used as
intended, Verifiers are able to anonymously retrieve and use a Status
List to check the currency of a given credential, without revealing to
the Issuer which credential is being checked. This approach avoids the
"phone home" problem where Verifiers directly communicate with Issuers
during verification.

We consider two classes of Status Lists, "Boolean" and "Multivalue"
lists and analyze the privacy impact of the differences between the two.
Boolean lists expose a single boolean value for each entry in a list,
correlating to a single binary entry for each Verifiable Credential
whose status is managed by that list. Multivalue lists provide for
arbitrary values in each entry with explicit, custom semantics
describing the meaning of potential value, thus allowing Credentials
whose status check reveals sophisticated knowledge about the credential.

With any Status List, an astute observer can analyze how different
states change in relation to specific real-world transitions and gain
unexpected insights. By understanding what given bits mean and knowing
that certain values are correlated to the same VC allows a complex
opportunity to infer unintended information. Since multivalue status
lists publicly correlate related values, each with specific meaning,
attackers have a richer source of data to try to understand things that
were perhaps meant to be kept private.

Outline
=======

1.  Use Case : Delivery Estimates

2.  Abstract Data Model

3.  Boolean Status List Data Model

    a.  Description

    b.  Example VC

    c.  Example Status List

4.  Multivalue Status List Data Model

    d.  Description

    e.  Example VC

    f.  Example Status List

5.  Comparison

    g.  Semantic Reveal

    h.  Correlation Topology

    i.  Differential Privacy

    j.  Reuse

    k.  Layer Violation

6.  Conclusion

Use Case : Delivery Estimates
=============================

Consider a specific supply chain use case, where a single Verifiable
Credential communicates the current best estimate for delivery.
Logistics broker **GetItQuick** issues a **Delivery Estimate Verifiable
Credential (DEVC)** for 30 cases of cogs manufactured by Cogswell Cogs.
Using a decentralized supply chain management system, GetItQuick uses a
VC Bitstring Status List to communicate three different status values
for the Verifiable Credential: revocation, suspension, and replacement.

-   **Revocation** means that the estimate is definitely wrong in some
    > way and should not be considered as a legitimate statement by the
    > issuer. Either from a clerical error or system compromise, this VC
    > is permanently renounced.

-   **Suspension** means that there is some problem with the estimate
    > and it should not be relied upon as accurate, however it still
    > represents a legitimate estimate from the Issuer. It may simply
    > have been made irrelevant by recent events.

-   **Replacement** means that the current estimate is still valid, but
    > that a replacement VC should be sought. This might happen because
    > another entity has taken over the authority for that estimate,
    > without invalidating the previous estimates.

Further, GetItQuick uses Status Lists for all Delivery Estimates for all
shipments it is involved with. As such, each Status List may contain
status information for hundreds or thousands of VCs.

For example, in a supply chain scenario, a number of products known to
an attacker might be rerouted in a manner that requires replacing VCs
that attest to expected delivery dates. In that situation, attackers can
potentially gain knowledge about which products are rerouted in the same
way and hence might legitimately be inferred to be on the same
transport, thus potentially revealing information about a flow of
material that was previously not publicly available.

![](media/image3.png){width="3.0in" height="2.34375in"}

You could achieve this goal with two different approaches, with
different topology and different correlatability, which for this paper,
we'll refer to as a Multibit VC and a Singlebit VC.

![](media/image2.png){width="3.0416666666666665in"
height="3.7916666666666665in"}

In a Multibit VC, we use a single status entry to point to a single
entry in one multi-bit status list, which contains separable bits for
each status of revocation, suspension, and replacement. Issuers update
those bits as necessary and verifiers can inspect the list to make their
verification and validation decisions.

![](media/image1.png){width="3.375in" height="3.25in"}

A Singlebit VC has multiple entries in the status property, pointing to
different entries in potentially different status lists. The status list
entries must all be unique, but they could, in fact, use the same status
list or use different lists.

With a Singlebit VC, the different states are only correlatable by
parties who already have access to the VC, which is appropriate. The
verifiers, in fact, MUST be able to correlate all three statuses with
that particular VC. Perhaps more importantly, the semantics of each bit
must be communicated publicly.

With a Multibit VC, the different states for all users are trivially
correlatable in public. All an attacker needs is a single VC, then they
can watch the single status list to discern how complex transitions
change. Even without access to the VCs, attackers can watch transitions,
with full semantic knowledge of the meaning of those bits.

With Singlebit VCs, attackers, without access to a VC, only know that
arbitrary bits are flipping, without knowledge of what those bits mean.
While an attacker can try to infer the meaning based on change analysis,
doing so is subject to significant ambiguity.

With Singlebit VCs AND access to at least one VC, attackers can
understand that particular status lists are sometimes used for specific
functions (revocation, suspension, replacement), but you can\'t be sure
that every entry in that list is a particular kind of status, because
the semantics of the bits are specified in each VC, not in the status
list itself. You could have the SAME statuslist provide different kinds
of status with different bits, meaning that observers can\'t always
infer from a given VC what the other entries in a status list might be.

Additionally, by separating different kinds of statuses to different
lists, any attacker, when considering any VC they don\'t have, an
attacker can\'t know if they are watching all of the factors that might
affect currency. Whereas, in a Multibit VC, attackers always know that
they are viewing a functionally complete set of statuses, including the
meaning of each of those bits.

In practice, most issuers probably won't go to extensive lengths for the
highest privacy configuration, but some will.
