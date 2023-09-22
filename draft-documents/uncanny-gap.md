# The Uncanny Gap
How we can never know the truth and what we can do instead

Abstract
--------

Digital systems wrestle with the same question that mankind always has:
"what is truth?" From a philosophical perspective, many acknowledge the
limits of what is fundamentally knowable. However, many digital identity
advocates pursue the goal of determining one's "true identity" as a
precondition for providing services. The issue with this goal is that it
conflates what is "true", as in what exists in objective reality, with
the perceptions and beliefs of an individual person or system. We call
this phenomenon "the uncanny gap": the insurmountable difference between
physical reality and its perception, interpretation, or representation
in information systems. Instead of trying to close this gap, digital
systems should be designed to establish a sense of truth that is good
enough for its needs.

**Github**:
[[https://github.com/WebOfTrustInfo/rwot12-cologne/tree/main/draft-documents]{.underline}](https://github.com/WebOfTrustInfo/rwot12-cologne/tree/main/draft-documents)

Outline Thoughts
----------------

-   ### Fundamentals

    -   There is a reality (we accept this as a foundation). Realism.

    -   We can't actually observe the objective truth of it.

    -   Information space != physical space

        -   Different orders of existence

-   ### Legacy Examples

    -   Calculus

    -   Physical Illusions

        -   Wagon Wheels

        -   Bouncing balls w/ & w/o sound

        -   [[https://www.ncbi.nlm.nih.gov/pmc/articles/PMC9206545/]{.underline}](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC9206545/)

        -   [[https://journals.sagepub.com/doi/full/10.1177/0301006620962279]{.underline}](https://journals.sagepub.com/doi/full/10.1177/0301006620962279)

    -   Joseph Campbell

    -   Simulacrum v Simulation

        -   [[https://en.wikipedia.org/wiki/Simulacra\_and\_Simulation]{.underline}](https://en.wikipedia.org/wiki/Simulacra_and_Simulation)

    -   Numbers v Measurables

    -   Language Translation

        -   Translation of sentences into sentences is reasonably
            > possible, but word-to-word mapping is sometimes tricky
            > because multiple words share the same meaning, and a word
            > often has multiple meanings; thus, word-for-word
            > translation mapping does not necessarily lead to accurate
            > substitutions of meaning.

    -   Science advancement by negatives

        -   Iteration over time that survives more and more
            > investigations

        -   Disproving previous theories is the goal

        -   [[https://www.sciencedirect.com/science/article/pii/S0924977X19317195]{.underline}](https://www.sciencedirect.com/science/article/pii/S0924977X19317195)

        -   [[https://www.ncbi.nlm.nih.gov/pmc/articles/PMC7571848/]{.underline}](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC7571848/)

    -   Medical knowledge

        -   What's testable v. what results mean

            -   DNA

        -   When results collide

        -   Arriving at diagnosis

            -   Sometimes by ruling out what is known

                -   Observed symptoms + bloodwork results +
                    > x-ray/MRI/CAT scan = diagnosis

            -   Sometimes by confirming suspicions through confirmed
                > results of testing

                -   Observed symptoms + bloodwork results +
                    > x-ray/MRI/CAT scan = diagnosis

-   ### Digital Consequences

    -   Can't know who is on the other side of the device

    -   Digital Identity (\~attributes & attestations)

        -   Truth about an individual

    -   Biometrics

        -   Worldcoin

        -   [[For every human
            > (worldcoin.org)]{.underline}](https://worldcoin.org/)

    -   Identity is NOT the silver bullet for security

    -   Tacit v Explicit

    -   Digital Authorities v Self-Asserted

    -   Reputation vs Authority

        -   Centralized-Architecture(Identity comes after data: first we
            > create email then we identify yourself)

            -   Signal source of truth(google)

            -   Email and Phone number identifiers

        -   Decentralize-Architecture(local-first and data comes after
            > identity)

            -   Blockchain and Consensus mechanism of people, group and
                > people

-   -   ### Social Consequences

    -   Under age buying online

    -   Estimation of ages of adolescents online

        -   [[https://www.tandfonline.com/doi/full/10.1080/19012276.2021.1887752]{.underline}](https://www.tandfonline.com/doi/full/10.1080/19012276.2021.1887752)

    -   Racism, sexism, bullying

    -   Deep fakes

        -   Voice

        -   Imagery

        -   Identity theft

        -   Fraud

    -   How relationships for the primary basis of trust in humans

        -   [[https://www.cbsnews.com/news/trump-poll-indictments-2023-08-20/]{.underline}](https://www.cbsnews.com/news/trump-poll-indictments-2023-08-20/)

        -   [[https://www.ncbi.nlm.nih.gov/pmc/articles/PMC10083508/]{.underline}](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC10083508/)

    -   Subjective consistency increases trust

        -   [[https://www.nature.com/articles/s41598-023-32034-4]{.underline}](https://www.nature.com/articles/s41598-023-32034-4)

    -   Propaganda

        -   Not meant to convince, but to affect

    -   Truthiness

        -   Looks convincing

        -   Sounds right

-   ### Responses & Mitigations

    -   VC 3-party model

    -   Surfeit of Evidence

        -   Redundancy

        -   Multiple Sources

    -   Consistency over time

        -   Anomaly detection

        -   Predictability

        -   Trust of attestors

-   What matters to me?

    -   What is my boundary as a user on the internet?

        -   How many spaces or domains I am searching or I need truth.

-   ### Bridge between Digital and Physical

    -   Local first(community based applications) Holochain

        -   SSI: identity start from physical interaction

        -   If Reputation can replace the centralize source of truth, if
            > we want to prove the validity of data, so the data can be
            > distributed

-   ### What you can do

    -   **Recognize the fundamental impossibility of closing the gap.**
        > Do not presume that any technical approach can guarantee
        > perfect recognition. No technical approach can guarantee that
        > any particular asserted fact is objectively true. Most
        > importantly, realize that attempting to achieve the impossible
        > is more likely to cause harm from being overzealous than it is
        > to actually resolve your identity question with 100% accuracy.

    -   **Acknowledge that x** your system's notion of identity is
        > complete in and of itself, even if it includes information
        > from multiple sources. As such, external notions of identity
        > such as a legal credentials or OAuth login data provide
        > support and evidence for your notion of the associated user,
        > but they do not define who that user \*is\*.

    -   **Don\'t presume device authentication works.** Every device has
        > its unique attack surface and can be hacked.

    -   **Use multi-factor, multi-source identification mechanisms for
        > higher assurance**. Rather than relying on a single source
        > authority to identify an individual or organization, enable
        > users to leverage multiple distinct authorities to establish
        > their identity in your system.

        -   Multi-factor is inherently already an elevation of
            > security/cost to a system, which some systems might not
            > need. Really the multi-factor should, maybe be a concrete,
            > low barrier example to the "economics to design" point
            > below

    -   **Use the Use Cases your system is designed to support to
        > evaluate the risks, cost, and consequences both the user, and
        > the system runner may experience.** Every system has a set of
        > uses it is designed for and there are harms, and costs
        > associated with implementation choices that will have an
        > effect on both the system runner, and the intended user. To
        > use a concrete example, take a web based service which has
        > users create an account with some identifier. Here we assert
        > that even this, commonly held paradigm in today's web, should
        > be considered carefully when designing a system. Many use
        > cases do not require any user identifier at all, and even if
        > it is low cost to ask the user to make an account, or provide
        > a public key, the act of doing so opens the user to a certain
        > set of potential risks. The user could choose to reuse that
        > identifier and now if a potential data breach occurs you may
        > expose the user to correlation that was unintended. Even if
        > the overall risks are low, understanding the harms that can
        > happen from both the system runner, and the user is crucial to
        > being able to properly evaluate the economic costs that are
        > reasonable, and useful for a given system.

    -   **Use economics to design and validate your system.** Evaluate
        > the costs of your chosen identity mechanisms against benefits
        > and harms. Different mechanisms for recognizing, remembering,
        > and responding to specific people and things have different
        > tradeoffs.

        -   Invest enough to satisfy your requirements without causing
            > unneeded harms or risks for users.

        -   Design your system so that the cost to compromise is greater
            > than the value from doing so. While you can't close the
            > gap, you can make it good enough for the threat models you
            > care about.

        -   For example, don't use biometrics for authenticating into
            > social media, but DO consider biometrics for high security
            > contexts like access to nuclear facilities.

-   ### Conclusion

Authors
=======

Joe Andrieu \<[[joe\@legreq.com]{.underline}](mailto:joe@legreq.com)\>

Erica Connell
\<[[ericasconnell\@gmail.com]{.underline}](mailto:ericasconnell@gmail.com)\>

Zaïda Rivai
\<[[zaida.rivai\@danubetech.com]{.underline}](mailto:zaida.rivai@gmail.com)\>

Shigeya Suzuki
\<[[shigeya\@wide.ad.jp]{.underline}](mailto:shigeya@wide.ad.jp)\>

Eric Schuh
\<[[eric.schuh\@gmail.com]{.underline}](mailto:eric@legreq.com)\>

Contributors
============

Hedayat Abedijoo
\<[[h.abedijoo\@gmail.com]{.underline}](mailto:h.abedijoo@gmail.com)\>

UX Harms

Complexity leads to exodus. User burden matters. Failed tasks from
multi-tasking.

Draft Sections
==============

Fundamentals
------------

To understand the complexity of the Uncanny Gap it is useful to consider
the nature of how truth and identity manifest in different domains and
how some domains build upon others to establish higher orders of truth.
This complex tapestry constitutes how we as individuals and society
generate shared meaning.

### Truth

Consider three domains of truth: science, law, and blockchains. Each of
these domains constitutes their own self-consistent set of accepted
facts, using processes formally defined, understood, and used by those
participating in the domain's truth seeking function. Each is a
simulacrum unto itself, although science and law are both sincere
efforts to map its truth from objective reality.

Science depends upon the scientific process, publication, and
independent validation to establish truth. If a discovery stands up to
the legitimate scrutiny of peers, including the explicit recreation of
the same observation by scientists unassociated with the original
discovery, then, and only then, might a new scientific "truth" gain
acceptance. The greater the number confirming recreations, especially
over time, the more established that particular truth becomes. One
consequence of this truth engine is that advances in Science come not
from affirming another's results, but rather definitely proving
situations in which previous results fail. In this manner, science
constantly challenges its own understanding of the physical world,
maintaining a continually evolving body of shared knowledge.

Law uses mechanisms of statutes, precedence, and rules of evidence and
process to arrive at jurisdictionally acceptable resolutions of
conflicts. If a court of competent jurisdiction finds a particular
assertion to be fact, then within the proceedings of that court it
\*is\* fact and often other courts will accept those findings in its own
deliberations. When a person is found guilty before a court of law, it
is not a statement about reality, it is first and foremost a statement
about what the court recognizes, so that subsequent legal actions can be
based on a common understanding. A verdict of guilty does not
necessarily mean that the guilty individual actually committed the
crime, but rather that, within the limits of the processes and accepted
truths of the court, the individual must be treated as guilty.

Blockchains also establish their own globally acknowledged notion of
truth. Regardless of how much a bitcoin might be worth in some other
currency, it is indisputable which accounts control what amount of
bitcoin. Bitcoin uses proof-of-work, signed cryptographic operations,
and a gossip network to establish a globally consensus about ordered
bitcoin transactions. This truth is independent of which human being or
organization is behind a given account. It doesn' depend on sovereign
state jurisdictions or other human institutions. It depends on math and
an agreed upon protocol, which itself can evolve if the community of
developers agree enough to change it. In fact, the difficulty of
changing that protocol intentionally helps maintain a stable system of
truth making.

Each of these truth systems maintains its own simulacrum in the sense
established by Baudrillard. \[citation\] He defines simulacra as
distinct from objective reality, even if they are intended to be based
on reality. Baudrillard further distinguishes simulacra from
simulations. The latter are explicit attempts to model the physical
world while the former construct independent truth. Simulations can be
evaluated by how well their model matches observed reality. Simulacra,
however, also contain their own grounded notion of truth, which depends
entirely on the mechanisms of that simulacrum

-   Courts define legal truth.

-   Science defines scientific truths.

-   Bitcoin defines how much bitcoin is controlled by different
    > accounts.

Objective Truth
---------------

We typically build information systems because we care about objective
reality, not just simulacra. Outside of pure simulacra like games, we
don't want to base our decisions on a mere information construct, we
want to deal with what is real. We want to respond to real threats and
opportunities, not just imagined possibilities. We want systems that
give us confidence in our actions in the real world. Inevitably, we want
that confidence to reach 100%: to know, with **certainty** the state of
objective reality. Unfortunately, this turns out to be as impossible to
achieve as the perpetual motion machine.

Objective truth has been a goal of scientists and philosophers since the
beginning of time.

Richard Feynman, nobel prize winner and master communicator explains in
his lecture on symmetry, that in a purely informational communication,
there are some things we simply cannot confirm. Only by being in the
same physical space can we resolve certain ambiguities.

===

To illustrate the whole problem still more clearly, imagine that we were
talking to a Martian, or someone very far away, by telephone. We are not
allowed to send him any actual samples to inspect; for instance, if we
could send light, we could send him right-hand circularly polarized
light and say, "That is right-hand light---just watch the way it is
going." But we cannot give him anything, we can only talk to him. He is
far away, or in some strange location, and he cannot see anything we can
see. For instance, we cannot say, "Look at Ursa major; now see how those
stars are arranged. What we mean by 'right' is ..." We are only allowed
to telephone him.

Now we want to tell him all about us. Of course, first we start defining
numbers, and say, "Tick, tick, two, tick, tick, tick, three, ...," so
that gradually he can understand a couple of words, and so on. After a
while we may become very familiar with this fellow, and he says, "What
do you guys look like?" We start to describe ourselves, and say, "Well,
we are six feet tall." He says, "Wait a minute, what is six feet?" Is it
possible to tell him what six feet is? Certainly! We say, "You know
about the diameter of hydrogen atoms---we are 17,000,000,000

hydrogen atoms high!" That is possible because physical laws are not
invariant under change of scale, and therefore we can define an absolute
length. And so we define the size of the body, and tell him what the
general shape is---it has prongs with five bumps sticking out on the
ends, and so on, and he follows us along, and we finish describing how
we look on the outside, presumably without encountering any particular
difficulties. He is even making a model of us as we go along. He says,
"My, you are certainly very handsome fellows; now what is on the
inside?" So we start to describe the various organs on the inside, and
we come to the heart, and we carefully describe the shape of it, and
say, "Now put the heart on the left side." He says, "Duhhh---the left
side?" Now our problem is to describe to him which side the heart goes
on without his ever seeing anything that we see, and without our ever
sending any sample to him of what we mean by "right"---no standard
right-handed object. Can we do it?

==

The lecture explains how our current best understanding of physics gets
us nearly there. Unfortunately, nearly there is not 100%.

==

In short, we can tell a Martian where to put the heart: we say, "Listen,
build yourself a magnet, and put the coils in, and put the current on,
and then take some cobalt and lower the temperature. Arrange the
experiment so the electrons go from the foot to the head, then the
direction in which the current goes through the coils is the direction
that goes in on what we call the right and comes out on the left." So it
is possible to define right and left, now, by doing an experiment of
this kind.

==

Now we did not mention one operation on our list, which must necessarily
be questioned, and that is the relation between matter and antimatter.

==

So if our Martian is made of antimatter and we give him instructions to
make this "right" handed model like us, it will, of course, come out the
other way around. What would happen when, after much conversation back
and forth, we each have taught the other to make space ships and we meet
halfway in empty space? We have instructed each other on our traditions,
and so forth, and the two of us come rushing out to shake hands. Well,
if he puts out his left hand, watch out!

==

We have to watch out because we cannot know through pure communication
whether or not the martian's normal context is made of anti-matter.

It is inherently impossible for two observers to be absolutely certain
they are communicating about the same observed phenomenon.

You can convince yourself, but you can never know.

Meaning as response by the user

Philosophers have argued since time immemorial about whether or not
truth exists and if it does, is it knowable? Even if we accept that
reality exists--for this paper we do--then we must wrestle with whether
or not we, as humans, are perceiving reality and when communicating with
others whether or not we are discussing the same objective phenomenon.
Science and Law both use formal processes to establish facts which are
accepted as true, but each also acknowledges the gap between their
results and actual physical reality. In computer science, Garbage In
Garbage Out is a well worn truism to express the inherent boundaries of
digital systems. The result is an awareness that truth and facts are
constrained within the systems that establish those facts, and using
such truths outside their inherent domain, complications inevitably
arise.

1.  Deep philosophers

2.  Human perception

3.  Common language and cultural perspectives

4.  Scientific process

5.  Legal process

6.  Garbage in, Garbage out

7.  Boundaries

8.  Simul

Identity

Domains

Orders

FEYNMAN!
[[https://www.feynmanlectures.caltech.edu/I\_52.html]{.underline}](https://www.feynmanlectures.caltech.edu/I_52.html)

As individuals however, we can't actually observe the objective truth of
it. Instead we rely upon our senses to provide information we use to
\[understand our subjective truth of it.\] The more confirmations we
collect through our own senses, the more we accept the information as
consistent with objective truth. Then we use words to compare our data
with others, and must spend some time creating a shared mental model of
what words mean, as Feynman describes above. We can only approach enough
alignment to move forward, and can never be sure we share objective
truth.

In our physical world interactions, our multiple senses process both
tacit and explicit information about our interactions. We can discern,
for example, by a person's inflection and facial expression if their
statement "That smells great." is literally expressing what those words
mean by definition or if they are being sarcastic, and are expressing
the opposite.

In the digital space, we do not have the same tacit information input to
help us determine the truth of that statement. The digital space is
simply a different order of existence.

Identity

We define identity as how one recognizes, remembers, and responds to
specific people and things, including ourselves. (Functional Identity
Primer)

Domains of Meaning

As such, each simulacra, each truth engine, defines its own domain.

An unavoidable complication arises whenever we attempt to share
information across domains. Because truth and identity are domain
specific, crossing domain boundaries necessarily involves an impedance
mismatch where some characteristics of the intended message are lost in
translation \[citation?\].

We see this in language translation, where literal equivalents often
lose vital meaning. \[EXAMPLE\]

We also see it in when science-based "truths" are presented to a court
of law. \[EXAMPLE\]

In the end, the domain that continues the discourse applies its own
truth mechanisms to the incoming meaning. Courts accepts as "fact"
things that are unscientific \[EXAMPLE\] while science accepts legal
findings only insofar as it affects the legal operation of the
scientists and institutions: a finding of law would not be a suitable
piece of evidence in a peer-reviewed journal. \[EXAMPLE\]

Legacy Examples
---------------

-   **Physical Illusions**

    -   Wagon Wheels

    -   Bouncing balls w/ & w/o sound

    -   [[https://www.ncbi.nlm.nih.gov/pmc/articles/PMC9206545/]{.underline}](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC9206545/)

    -   [[https://journals.sagepub.com/doi/full/10.1177/0301006620962279]{.underline}](https://journals.sagepub.com/doi/full/10.1177/0301006620962279)

    -   [[https://journals.sagepub.com/doi/pdf/10.1068/p250503]{.underline}](https://journals.sagepub.com/doi/pdf/10.1068/p250503)

-   **Science advancement by negatives**

    -   Iteration over time that survives more and more investigations

    -   Disproving previous theories is the goal

    -   [[https://www.sciencedirect.com/science/article/pii/S0924977X19317195]{.underline}](https://www.sciencedirect.com/science/article/pii/S0924977X19317195)

    -   [[https://www.ncbi.nlm.nih.gov/pmc/articles/PMC7571848/]{.underline}](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC7571848/)

    -   [[https://en.wikipedia.org/wiki/Scientific\_theory]{.underline}](https://en.wikipedia.org/wiki/Scientific_theory)

    -   [[https://en.wikipedia.org/wiki/Scientific\_law]{.underline}](https://en.wikipedia.org/wiki/Scientific_law)

    -   [[https://archive.org/details/principleofrelat00eins]{.underline}](https://archive.org/details/principleofrelat00eins)

-   Language Translation

    -   Translation of sentences into sentences is reasonably possible,
        > but word-to-word mapping is sometimes tricky because multiple
        > words share the same meaning, and a word often has multiple
        > meanings; thus, word-for-word translation mapping does not
        > necessarily lead to accurate substitutions of meaning.

    -   [[https://arc.lib.montana.edu/ojs/index.php/IJS/article/view/993]{.underline}](https://arc.lib.montana.edu/ojs/index.php/IJS/article/view/993)

    -   [[https://www.cukerala.ac.in/cukpdfs/IQAC/3.4.7/3.4.7.ECL.019.pdf]{.underline}](https://www.cukerala.ac.in/cukpdfs/IQAC/3.4.7/3.4.7.ECL.019.pdf)

-   Memory

    -   [[https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4183265/]{.underline}](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4183265/)

    -   [[https://www.ncbi.nlm.nih.gov/pmc/articles/PMC8273185/]{.underline}](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC8273185/)

    -   [[https://discovery.ucl.ac.uk/id/eprint/10091017/3/Brewin\_Regaining%20the%20Consensus%20on%20Memory%20final%20accepted%20version.pdf]{.underline}](https://discovery.ucl.ac.uk/id/eprint/10091017/3/Brewin_Regaining%20the%20Consensus%20on%20Memory%20final%20accepted%20version.pdf)

-   Calculus

-   Joseph Campbell

-   Simulacrum v Simulation

    -   [[https://en.wikipedia.org/wiki/Simulacra\_and\_Simulation]{.underline}](https://en.wikipedia.org/wiki/Simulacra_and_Simulation)

-   Numbers v Measurables

To begin establishing that the uncanny gap is real, and help define what
forms it takes, let\'s take a look at some examples from science, and
your own eyes. By its very nature, the scientific method is a tool to
mitigate the impact of the uncanny gap, and ensure that scientific
theories which are accepted by the scientific community are, in fact,
the closest representation of the physical world that is possible.
Indeed, the very definitions used in the scientific world to define a
"theory" and "law". Taking the case of scientific theory, which is
defined by Wikipedia as,

> A scientific theory is an explanation of an aspect of the [[natural
> world and
> universe]{.underline}](https://en.wikipedia.org/wiki/Natural_science)
> that can be (or a fortiori, that has been) [[repeatedly
> tested]{.underline}](https://en.wikipedia.org/wiki/Reproducibility)
> and corroborated in accordance with the [[scientific
> method]{.underline}](https://en.wikipedia.org/wiki/Scientific_method),
> using accepted
> [[protocols]{.underline}](https://en.wikipedia.org/wiki/Protocol_(science))
> of
> [[observation]{.underline}](https://en.wikipedia.org/wiki/Observation),
> measurement, and evaluation of results. Where possible, theories are
> tested under controlled conditions in an
> [[experiment]{.underline}](https://en.wikipedia.org/wiki/Experiment).^[[\[1\]](https://en.wikipedia.org/wiki/Scientific_theory#cite_note-NAS1999-1)[\[2\]](https://en.wikipedia.org/wiki/Scientific_theory#cite_note-The_Structure_of_Scientific_Theories_in_''The_Stanford_Encyclopedia_of_Philosophy''-2)]{.underline}^
> In circumstances not amenable to experimental testing, theories are
> evaluated through principles of [[abductive
> reasoning]{.underline}](https://en.wikipedia.org/wiki/Abductive_reasoning).
> Established scientific theories have withstood rigorous scrutiny and
> embody scientific
> [[knowledge]{.underline}](https://en.wikipedia.org/wiki/Knowledge).

We see here that a theory relies on a, "repeatedly tested and
corroborated," explanation. The fact that to become a theory requires
repeatability illustrates how the scientific community acknowledges that
a single instance of data, or interpretation of the data is by no means
sufficient to be considered accepted by the scientific community.
Additional discussion of a scientific theory continues on Wikipedia
saying,

> The strength of a scientific theory is related to the diversity of
> phenomena it can explain and its simplicity. As additional
> [[scientific
> evidence]{.underline}](https://en.wikipedia.org/wiki/Scientific_evidence)
> is gathered, a scientific theory may be modified and ultimately
> rejected if it cannot be made to fit the new findings; in such
> circumstances, a more accurate theory is then required. Some theories
> are so well-established that they are unlikely ever to be
> fundamentally changed (for example, scientific theories such as
> [[evolution]{.underline}](https://en.wikipedia.org/wiki/Evolution),
> [[heliocentric
> theory]{.underline}](https://en.wikipedia.org/wiki/Heliocentrism),
> [[cell
> theory]{.underline}](https://en.wikipedia.org/wiki/Cell_theory),
> [[theory of plate
> tectonics]{.underline}](https://en.wikipedia.org/wiki/Plate_tectonics),
> [[germ theory of
> disease]{.underline}](https://en.wikipedia.org/wiki/Germ_theory_of_disease),
> etc.). In certain cases, a scientific theory or scientific law that
> fails to fit all data can still be useful (due to its simplicity) as
> an approximation under specific conditions. An example is [[Newton\'s
> laws of
> motion]{.underline}](https://en.wikipedia.org/wiki/Newton%27s_laws_of_motion),
> which are a highly accurate approximation to [[special
> relativity]{.underline}](https://en.wikipedia.org/wiki/Special_relativity)
> at velocities that are small relative to the [[speed of
> light]{.underline}](https://en.wikipedia.org/wiki/Speed_of_light).^[[\[6\]](https://en.wikipedia.org/wiki/Scientific_theory#cite_note-Misner1973-7)[\[7\]](https://en.wikipedia.org/wiki/Scientific_theory#cite_note-Weinberg-8)[\[8\]](https://en.wikipedia.org/wiki/Scientific_theory#cite_note-Project2061-9)]{.underline}^

Here, the Wikipedia article illustrates one of the most well known
examples of how science deals with the uncanny gap. In the case of
Newton's laws of motion, it is well understood at this point in history
that his law's are only accurate in a certain domain, and Einstein
recognized this because of a set of observed data points which were not
predicted, or deviated from Newton's laws. For Einstein there were three
main tests that his new theory of gravity would need to pass in order
for it to be a recognized improvement. These were proposed in his book,
"The Principle of Relativity", published in 1920, and were:

1.  The observed errors from Newton's laws in the prediction of
    > Mercury\'s orbit's perihelion precession around the sun, or in
    > other words the amount that the long axis of Mercury's shifts each
    > year relative to the previous.

2.  The observed errors in how much light bends around massive objects,
    > such as the sun, for which Newton\'s laws only predicted about
    > half of the observed light bending.

3.  The existence of gravitational redshift, which Einstein had
    > predicted to exist when developing the equivalence principle
    > in 1907.

Eventually Einstein was able to develop his theory of general
relativity, using these three points as a guiding post, but what is
important to see in this example is that the scientific community
understands that their data is complete, and that science as a field
recognizes that the uncanny gap exists as a default mode of working. All
existing scientific theories, and laws, are incorrect in some form, but
useful in the prediction of the real world for their particular domains.
Indeed, even the theory of general relativity is known to be incomplete,
as in the edge case of the singularity event where enough mass prevents
even light from escaping, commonly known as a black hole, as one
example, and the still to be discovered unification of general
relativity and quantum mechanics, as another. Einstein's theory predicts
very well what happens externally to this phenomenon, but says very
little about what happens inside of these, now confirmed, astronomical
objects.

To look at another case where the uncanny gap appears in everyday life,
we turn to the artform of translation. For the purpose of this
illustration, we take a look at a study which looks at the accuracy of
machine translation. In the paper, "Analysis of human versus machine
translation accuracy", published in 2015, used a methodology of taking a
cohort of, "Chinese speakers and who had studied English for at least 15
years", and had them translate a series of both simple and complex
sentences from Chinese to English. These translations were then
evaluated by an evaluator for accuracy; the same set of sentences were
then fed into 10 machine translation tools that were available at the
time of publication. The results found that human translation was
generally much better than the machine translation of the time, however,
that is not what is of interest here. Looking at the study methodology
of having a human evaluator decide the accuracy of the translation shows
the inherent issue of translation, and that is that depending on the
evaluator and their own proficiency in translation of the language, or
their own biases based on the particular dialect of each language they
are most familiar with, it should be expected that each translation
attempt may receive a different score. This is not to say that
evaluators of similar skill in each language would cause the results of
the quoted study to change in any meaningful way, however subtle
differences in the scoring of individual translations shows the inherent
difficulty and uncertainty present in translation. To give an example
from this paper of how translation can go wrong, "a sentence
mistranslated by machines in the current study was 'Customers come
first', which when translated literally from Chinese-to-English by
machines without cultural input, it turned out to be 'The customer is
god.' " Here is an example of a phrase which, when mistranslated,
drastically changed the meaning, and intent of the phrase at face value.
Indeed the authors of the paper point out the issue with this type of
mistranslation, being that the mistranslated phrase, "...may not be
appropriate for much of the English-speaking language group in this
case, as it could even be considered offensive to some." While the
intent of the original phrase is a fairly benign idiom, the
mistranslation of the phrase illustrates, and the potential offensive
nature of the translation when taken at face value, illustrates the
uncanny gap in that a reader, who reads the translation in such a way
that they do, in fact, get offended, would be misconstruing the intent
of the original speaker and illustrates how each person's subjective
reality differs from the objective reality of the world.

Perhaps the most immediately obvious case where the uncanny gap can be
seen is in illusion. Illusions have a wide and deep history of impacting
the human race, whether it be from medical issues, such as psychosis,
self induced illusions from taking substances like psychoactive
mushrooms, or other plants, or simply from the state of dehydration
causing the brain to see water that isn't there. In modern science,
there is much discussion about the nature of illusions, and still much
uncertainty as to what causes the human perception to warp reality even
in simple cases of Visual Illusions. Visual Illusions are a class of
illusions that most people have encountered, whether at school messing
around with friends, or, likely from just browsing the internet for some
time. These are the simple tricks of the eye where if straight lines are
drawn in a certain way they appear to curve, or how when two lines of
the same length are surrounded by certain other lines, one will appear
shorter than the other. Below are some examples of these visual
illusions, which illustrate a direct example of the uncanny gap in
action, you are viewing it in real time, right now.

\<add some examples of visual illusions\>

![](media/image1.jpg){width="1.453125546806649in"
height="1.8486504811898512in"}

*The impossible trident was first published in 1964 by D.H. Schuster.*

![](media/image3.jpg){width="3.1125459317585302in"
height="2.313215223097113in"}

*Illusory motion illusion. *

![](media/image4.png){width="2.7206714785651793in"
height="1.633989501312336in"}

*By Franz Müller-Lyer - MathWorld - Müller-Lyer IllusionMüller-Lyer, FC
(1889). &quot;Optische Urteilstäuschungen&quot;. Archiv für Physiologie
Suppl.: 263--270., Public Domain,
[[https://commons.wikimedia.org/w/index.php?curid=109553102]{.underline}](https://commons.wikimedia.org/w/index.php?curid=109553102)*

###  

Digital Consequences
--------------------

**Identifying peer, Digital Authorities v Self-Asserted**

In real space, if the person in front of you is someone you have met in
the past, you can communicate with them with a certainty that depends on
memory. With family members, this is likely possible. On the other hand,
it is more challenging to identify a person in a digital space. In
particular, it isn\'t easy to communicate with the person in front of
you in the digital space with each person\'s device. Although there are
some means of recognizing the other party by bringing the devices close
to each other or touching them (iOS17), behind the scenes, the
identification of the other party is done through a somewhat complicated
procedure.

Identifying the other party reliably in the digital space demands
relying on a trusted third party, of which relying on an authority as a
trusted third party is a relatively economical method. On the other
hand, the good and bad of relying on authority must be fully considered.

**Digital Identity (\~attributes & attestations) / Truth about an
individual**

An authority provides attestation to some of the attributes that make up
an identity. The authority provides attestation of some of the
attributes that make up an identity. That is, it includes being
validated, which indicates that the attribute information about the
individual is verified and authentic.

**Communication and endpoint verification**

We use devices such as PCs or smartphones to connect in the digital
world to retrieve information and communicate with people via the
devices each user uses. When humans communicate via devices, we want to
know who is on the other side of communication. In reality, It is
challenging to be confident that the party with whom one is
communicating is, in fact, the party with whom one wishes to
communicate. The identity of the other side -- the Digital Identity --
presented in the communication mentioned above must be trustable enough
from the verifier's point of view.

-   Owner vs Possession of a phone

-   Correctness of communication

The problem can be divided into three issues. The first problem is
finding information about the peer endpoint bound to the identity. The
second problem is verification of the correctness of the information of
the endpoint. The third problem is the communication channel established
is the endpoint bound to the peer identity.

**Confidence on the information of the communication endpoint**

Let us discuss the above three points with an e-mail system as an
example.

In the physical world, we usually meet and exchange contact information
like email addresses on business cards, then communicate using e-mail
addresses to meet in digital space. E-mail addresses of the identity is
part of the information called "attributes." We tend to just trust the
presented e-mail address in person is the e-mail address the person
presented. But first and foremost, why do we believe the e-mail address
is correct? How do we verify the email address is correct?

**Confidence on the communication endpoint in use is the right one**

Many service providers verify users' email addresses by sending some
information (often a randomly generated number) to the address, then
asking the user to provide the information. The accuracy of email
delivery depends on multiple technologies and is established by
accepting a certain tolerance for gaps between these multiple
technological elements. Although a detailed discussion is omitted here,
a delicate look at the gaps between technical elements still needs to
make this method more secure and reliable.

**Example: Mobile Phone theft - stealing (verified)
endpoint/impersonalisation, over the shoulder attack**

These days we use smartphones every day. While a smartphone kept by a
person provides trustable enough terminal device to the person who is
keeping the device, if the phone is stolen and the thief can unlock the
phone, the thief can effectively impersonate the owner of the
smartphone. The impersonalisation is possible only if the thief can
unlock the phone. But that's happening in reality. Lately, we don't need
to type-in passwords usually since latest smartphones have fingerprint
or facial recognition technology built-in (TouchID celebrates its 10th
anniversary in September 2023). But from time to time, this technology
does not work, and people end up typing the passwords. Carelessly typing
passwords or pincodes while observed by somebody, allow the observer to
impersonate after having physical access to the phone.

**Example: Man-in-the-middle - stealing communication channel**

**Security economics**

**Biometrics**

**Tacit v Explicit**

(Digital Identity)

Digital identity is the use of digital tools to manage identity.

Digital identity is a new form of identity for humans that enables us to
show up in the digital space with a more relaxed form of consequences.
It is easy to create a new profile in instagram, twitter or any social
media, and practice a presence without much consequences.(let's call it
fake identity) In addition, somehow I need to communicate with people in
the physical world inside the digital world, so then I can create a new
digital identity with more consciousness considering the consequences
that can affect my physical and social interaction.

With more fake digital identities people easily are practicing topics
and hashtags with a new presence without consequences. a new presence to
each topic or context, so new observers are added to any topic or
hashtag. Apart from the core meaning of truth we need to reach
consensus, and more participants make the consensus harder, and
consequently finding the truth in the digital world is getting harder
and harder. But it can bring the next question to the table,

What matters to me? What do I need?

I just wanted to come to the RWOT event this morning, but I didn't know
what to wear, so I checked a couple of internet weather websites for
forecasting the weather condition. They were not equal, and I was not
looking forward to the truth that today the temperature is going to 23
or 20. Or today is going to be 75% or 90%, I just needed to wear a rain
jacket and ask my girlfriend to drive me to the place.

**Avoid Reuse of Identifiers**

If possible, don't reuse identifiers. Automate directed identifiers.
Don't give the user the burden of paying attention to which identifiers
are used with different systems.

While it seems like using strong, "authoritative" identifiers like state
issued IDs, increases confidence of a shared notion of the user, because
we cannot know that the current user is, IN FACT, the appropriate party
for that identifier, relying on the identifier is guaranteed to be an
error in some cases. Given that this "strong" identifier can't be
authoritative, it doesn't give the value imagined, while it does
increase the likelihood of harms from undesired correlation.

If you rely on external identifiers, for example for regulatory
compliance, use those only during onboarding and audit, not for normal
operations. Secure your interactions with cryptographically verifiable
identifiers that are not publicly linked to personally identifiable
information (PII), so that during use of them there is no unnecessary
communication of personally identifiable information.

Social Consequences
-------------------

-   How relationships for the primary basis of trust in humans

    -   [[https://www.cbsnews.com/news/trump-poll-indictments-2023-08-20/]{.underline}](https://www.cbsnews.com/news/trump-poll-indictments-2023-08-20/)

    -   [[https://www.ncbi.nlm.nih.gov/pmc/articles/PMC10083508/]{.underline}](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC10083508/)

    -   Subjective consistency increases trust

        -   [[https://www.nature.com/articles/s41598-023-32034-4]{.underline}](https://www.nature.com/articles/s41598-023-32034-4)

-   Deep fakes

    -   Voice

    -   Imagery

    -   Identity theft

    -   Fraud

    -   [[https://www.theguardian.com/commentisfree/2023/apr/01/ai-deepfake-porn-fake-images]{.underline}](https://www.theguardian.com/commentisfree/2023/apr/01/ai-deepfake-porn-fake-images)

    -   [[https://inews.co.uk/opinion/deepfake-technology-dangerous-women-worst-abuses-2124134]{.underline}](https://inews.co.uk/opinion/deepfake-technology-dangerous-women-worst-abuses-2124134)

    -   [[https://www.technologyreview.com/2021/02/12/1018222/deepfake-revenge-porn-coming-ban/]{.underline}](https://www.technologyreview.com/2021/02/12/1018222/deepfake-revenge-porn-coming-ban/)

    -   Regulating Deep Fakes: Legal and ethical considerations
        > [[https://papers.ssrn.com/sol3/papers.cfm?abstract\_id=3497144]{.underline}](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=3497144)

    -   Deep fake pornography
        > [[https://link.springer.com/article/10.1007/s13347-023-00657-0]{.underline}](https://link.springer.com/article/10.1007/s13347-023-00657-0)

    -   

-   Estimation of ages of adolescents online

    -   [[https://www.tandfonline.com/doi/full/10.1080/19012276.2021.1887752]{.underline}](https://www.tandfonline.com/doi/full/10.1080/19012276.2021.1887752)

-   False accusations by AI generated tools

-   Albert Acosta & "hitting White House staffer"

***How relationships for the primary basis of trust in humans***

Turning from the digital world to the social, the uncanny gap is once
again responsible for many of the issues society faces. Some examples of
this effect include: manipulation of political processes, the problems
of underage children being viewed in sexual contexts online, and the
consequences of deep fakes--which can have effect on both nation state
actors, as well as the individual lives of people. These examples are by
no means exhaustive, but all are a consequence of the same phenomenon,
which is that subjective consistency increases trust. This propensity
for humans to trust subjective sources can be seen easily in popular
systems, such as rating systems for restaurants, where people choose to
travel, and, indeed in the previous three examples that have a much
greater impact on society.

To add credence to the previous claims, let\'s take a look at how each
of the three examples given above have affected the world. Today in the
United States there has been a lot of discussion during the past two
presidential election cycles regarding the topic of election meddling.
Here we are not so interested in the political battle, but rather want
to illustrate the power that exists simply through the relationships
people form with the political leaders they follow. Recently CBS News
conducted a poll of Trump supporters in which they found that given the
statement, "Feel what they tell you is true", the poll respondents
answered with the following responses: 71% - Trump, 63% - Family and
Friends, 56% - Conservative Media Figures, and 42% - Religious Leaders.

![](media/image2.png){width="9.03125in" height="5.083333333333333in"}

The full set of possible answers to the poll question were not
available, however, the results still corroborate the claims made
earlier that if Trump were to say something, most of his supporters
would trust his word over most other sources, regardless of the
objective truth in the world. The consequences of this result, assuming
the respondents would act on the basis of their poll results, should be
fairly evident in the landscape of politics in the United States.

***Deep fakes***

Similarly deep fakes, which are only becoming more sophisticated as the
years roll by, can cause those that view them to believe things that
have consequences stretching from both personal issues to affecting an
entire society, or culture. Meskys (2019) distinguished four categories
addressing the consequences of deep fakes from an ethical and regulatory
point of view. "Hard" cases were seen as deep fakes that relate to porn
or politics, whereas "soft" cases relate to deep fakes created in the
commercial or creative content. The latter cases are socially beneficial
and thus raise less concerns, Meskys (2019).

![](media/image5.png){width="6.5in" height="5.138888888888889in"}

()

On April 17, 2018 BuzzFeed published a deep-fake video of President
Obama (BuzzFeedVideo, 2018), unlikely to be said by the real Obama. The
video demonstrated how easy it was to put words in someone else's mouth.
In politics, deep fakes can have several consequences, influencing
democratic processes, electoral campaigns or other socially significant
events. Deep fakes may be used as catalyst to erode trust in political
institutions, deepen division among social groups. If used by hostile
governments, deep-fakes could even pose threats to national security or
impair international relations, Meskys (2019).

The personal consequences of deep fakes are most easily illustrated in
the effects of deep fake porn, which, over the last 10 years or so has
caused many people, though mostly women, to experience a sometimes life
ruining event completely out of their control. This practice has even
led to issues for the Pope.

***Estimation of ages of adolescents online***

Lastly, an illustration of the uncanny gap in effect from something as
simple as viewing a picture online. In a paper published in 2021 titled,
"How old was she? The accuracy of assessing the age of adolescents'
based on photos", it was found that, "Participants overestimated the age
of the adolescents by, on average, 3.51 years. Participants
overestimated the age of young adolescent girls to a greater extent than
that of younger boys. Men made larger overestimations than women.
Participants also estimated smiling targets as being older than targets
with neutral facial expression..." The immediate impact of this fact in
the world of social media should be obvious. All three of these examples
illustrate the uncanny gap in effect in the real world, and should
establish the importance of understanding these inherent biases all
people have.

**Making Decision in real life based on Digital Truth**

A crucial element in decision-making is the information that people
predominantly gather from the internet through search engines. However,
it is imperative to understand that search engines are not accountable
for the accuracy of the information they provide. Their primary role is
to index and rank data, often influenced by monetization factors---who
pays more gets better visibility. To illustrate, consider a European
family who, based on perceived truths pertinent to Americans, invests
all their savings or takes out credit to pursue opportunities in, for
example, housing. This family could potentially face catastrophic
consequences due to the difference in contexts and realities.\
A friend of the European family who lives in the USA might use the same
information and make a lot of money. This shows how two people can read
the same thing but for one, it's true and works out well, and for the
other, it doesn't. It shows that what is true can depend on the
situation and the context.

**"Me Too" campaign**

I want to say how this campaign that has real value and stories based on
reality at its core can become a gap and a tool for abuse.

Responses & Mitigations
-----------------------

-   Acceptance: Be conscious about the gap and accept it,

    -   don't accept anything immediately as a truth

    -   Double check multiple resources

    -   

-   Consequences

    -   Help for complexity reduction not adding more

-   Digital Hygiene:

    -   Cybersecurity, Identity, Trust

    -   Spend time and resources on your digital hygiene system.

        -   Learn about 2-factor authentication, different mechanisms of
            > securities.

### Current

### Potential

Conclusion
----------

At the end, The reader may ask what I am supposed to take or learn from
this paper and after being more conscious about the uncanny gap.

First we would like to share that the uncanny gap is there and if you
find yourself uncertain and somehow confused about the truth or defining
and finding the truth, don't panic please and you are not alone and
there is a real gap that all of us are experiencing. We are trying to
find the best way to have a good dynamic with the gap and to see how we
can deal with it.\
Apparently the uncanny gap in the digital world is more deeper than the
physical world because of fake identities and lack of consequences. That
is why big brothers like Google have to apply their policies to tell us
what is the truth, and filter fake accounts and find the fake content.
You can easily imagine that the big brother doesn't carry the burden
without benefit, so famous sentences say that: if you do not pay for the
product, you are the product.

So we are giving all our data and information to the big brothers to
tell us what is the truth. Decentralized technology is trying to find
the solution: finding, defining and discovering the truth goes to people
more than the big brother. So it seems the digital world should have a
good bridge to physical life to bring consequences to the digital
identities.

Some technologies like Blockchain, Self-Sovereign Identity, Holochain
are addressing those concerns.

Cleanup/Random Thoughts
=======================

Other abstract ideas
--------------------

1.  "the uncanny gap": the insurmountable difference between physical
    > reality and what information an observer interprets.

2.  "the uncanny gap": the insurmountable difference between physical
    > reality and the information an observer experiences.

3.  "the uncanny gap": the insurmountable difference between physical
    > reality and what an observer experiences, because observers can
    > never know if their representation of physical reality is
    > accurate.

4.  "the uncanny gap": the insurmountable difference between physical
    > reality and the observed representation of that reality.

5.  "the uncanny gap": the insurmountable separation of reality and
    > observed information.

6.  "the uncanny gap": the insurmountable difference between physical
    > reality and the informational representations intended to describe
    > that reality.

7.  "the uncanny gap": the insurmountable difference between physical
    > reality and representations of that reality

8.  "the uncanny gap": the insurmountable difference between physical
    > reality and perceptions of that reality because we can't ever know
    > if the representation is accurate

9.  "the uncanny gap": the insurmountable difference between physical
    > reality and what an observer experiences

10. "the uncanny gap": the insurmountable difference between physical
    > reality and its representation in an information system.

11. "the uncanny gap": the insurmountable difference between physical
    > reality and an information system's perception, interpretation,
    > and representation of physical reality.

12. "the uncanny gap": the insurmountable difference between physical
    > reality and its perception, interpretation, or representation in
    > information systems.

In life-critical or national security situations, it is appropriate to
invest significant resources to gain identity assurance before providing
services. However, for social networking, many service providers simply
need an email confirmation so they can provide means for resetting a
password.

solving the problem of: how can a digital system decide which
information it should rely on?

**We can't know if the representation is accurate**

Digital systems wrestle with the same epistemological questions that
mankind always has: what is truth? From a philosophical perspective,
many acknowledge the limits of what is fundamentally knowable. However,
many digital identity advocates pursue the goal of determining truth as
a precondition for providing services. If the user is, in fact, a
particular human being, then we should allow certain services,

e.g., if it's Joe Andrieu using the computer, then let the user spend
Joe Andrieu's money. We argue that this aspiration to certainty is never
fully achievable. It's essentially impossible to know if the device
being used remains under Joe Andrieu's control...

We suggest that the same mechanisms we use to deal with uncertainty in
the real world can be used to provide reliable services to the right
parties.

---\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

Digital systems wrestle with the same epistemological questions that
mankind always has: what is truth? From a philosophical perspective,
many acknowledge the limits of what is fundamentally knowable. However,
many digital identity advocates pursue the goal of determining one's
"true identity" as a precondition for providing services. The issue with
this goal is that it conflates what is "true", as in what exists in
objective reality, with the notion of an individual observer's truth.
Here it is argued that digital systems should instead be concerned with
solving the problem of: how can a digital system decide which
information it should rely on?

When can we trust that the action initiated online ...

---\-\-\-\-\-\--

**Bibliography **

1.  Meskys, E. (2019, December 2). *Regulating deep fakes: legal and
    > ethical considerations*.
    > [[https://papers.ssrn.com/sol3/papers.cfm?abstract\_id=3497144]{.underline}](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=3497144)

2.  BuzzFeedVideo. (2018, April 17). *You Won't Believe What Obama Says
    > In This Video! 😉* \[Video\]. YouTube.
    > https://www.youtube.com/watch?v=cQ54GDm1eL0

3.  

Appendix A Creative Brief
=========================

Goal
----

Establish "the Uncanny Gap" as a useful phrase for resolving challenging
issues in digital identity.

Audience
--------

Primarily developers and regulators. We want to reach those individuals
making and influencing technical decisions that drive features of
institutional systems, both digital and bureaucratic.

Desired Change in Behavior
--------------------------

New and emerging systems are built with an awareness of the gap,
avoiding harms caused by ineffective attempts to solve the insolvable.

Talking Points
--------------

-   Truth and Identity are domain-bound constructs

-   Crossing domains introduces inevitable errors

-   Reality and Information systems are different domains

    -   Information Systems can never fully represent the truth of
        > reality

-   As a result, system developers should accept the inevitability of
    > uncertainty and design systems where the costs of establishing
    > "truth" is appropriate given the value of that truth and the
    > consequences of error.
