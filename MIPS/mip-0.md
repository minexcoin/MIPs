    ID: 0
    Title: MIP Purpose and Guidelines
    Author: Roman Hulenko <rhulenko@minexsystems.com>
    Type: Meta
    Status: Active
    Created: 2017-09-28

What is a MIP?
--------------

MIP stands for MinexCoin Improvement Proposal. An MIP is a design document providing information to the MinexCoin community, or describing a new feature for MinexCoin or its processes or environment. The MIP should provide a concise technical specification of the feature and a rationale for the feature. The MIP author is responsible for building consensus within the community and documenting dissenting opinions.

We intend MIPs to be the primary mechanisms for proposing new features, for collecting community input on an issue, and for documenting the design decisions that have gone into MinexCoin. Because the MIPs are maintained as text files in a versioned repository, their revision history is the historical record of the feature proposal.

For MinexCoin implementers, MIPs are a convenient way to track the progress of their implementation. Ideally each implementation maintainer would list the MIPs that they have implemented. This will give end users a convenient way to know the current status of a given implementation or library.

MIP Types
---------

There are three types of MIP:

-   A **Standard MIP** describes any change that affects most or all MinexCoin implementations, such as a change to the the network protocol, a change in block or transaction validity rules, proposed application standards/conventions, or any change or addition that affects the interoperability of applications using MinexCoin. Standard MIPs are subdivided into the following layers.
    -   **Consensus Layer** - the consensus layer defines cryptographic commitment structures. Its purpose is ensuring that anyone can locally evaluate whether a particular state and history is valid, providing settlement guarantees, and assuring eventual convergence. This layer is subdivided into soft fork and hard fork.
        -   **Soft Fork** - some structures that were valid under the old rules are no longer valid under the new rules. Structures that were invalid under the old rules continue to be invalid under the new rules.
        -   **Hard Fork** - structures that were invalid under the old rules become valid under the new rules.
    -   **Networking Layer** - specifies how nodes find each other and propagate messages.
    -   **Interface Layer** - includes improvements around client API/RPC specifications and specifies higher level calls accessible to applications.
    -   **Application Layer** - specifies high level structures, abstractions, and conventions that allow different applications to support similar features and share data.

-   An **Informational MIP** describes a MinexCoin design issue, or provides general guidelines or information to the MinexCoin community, but does not propose a new feature. Informational MIPs do not necessarily represent MinexCoin community consensus or a recommendation, so users and implementers are free to ignore Informational MIPs or follow their advice.

-   A **Meta MIP** describes a process surrounding MinexCoin or proposes a change to (or an event in) a process. Meta MIPs are like Standard MIPs but apply to areas other than the MinexCoin protocol itself. They may propose an implementation, but not to MinexCoin's codebase; they often require community consensus; unlike Informational MIPs, they are more than recommendations, and users are typically not free to ignore them. Examples include procedures, guidelines, changes to the decision-making process, and changes to the tools or environment used in MinexCoin development.

MIP Champion
------------

Each MIP must have a champion - someone who writes the MIP using the style and format described below, shepherds the discussions in the appropriate forums, and attempts to build community consensus around the idea.

The MIP process begins with a new idea for MinexCoin. It is highly recommended that a single MIP contain a single key proposal or new idea. The more focused the MIP, the more successful it tends to be. A change to one client doesn't require an MIP; a change that affects multiple clients, or defines a standard for multiple apps to use, does. The MIP editor reserves the right to reject MIP proposals if they appear too unfocused or too broad. If in doubt, split your MIP into several well-focused ones.

Vetting an idea publicly before going as far as writing an MIP is meant to save the potential author time. Asking the MinexCoin community first if an idea is original helps prevent too much time being spent on something that is guaranteed to be rejected based on prior discussions (searching the Internet does not always do the trick). It also helps to make sure the idea is applicable to the entire community and not just the author. Just because an idea sounds good to the author does not mean it will work for most people in most areas where MinexCoin is used. Examples of appropriate public forums to gauge interest around your MIP include [the MinexCoin topic in bitcointalk.org], [the Issues section of this repository]. In particular, [the Issues section of this repository] is an excellent place to discuss your proposal with the community and start creating more formalized language around your MIP.

Once the champion has asked the MinexCoin community whether an idea has any chance of acceptance a draft MIP should be presented as a [pull request]. This gives the author a chance to continuously edit the draft MIP for proper formatting and quality. This also allows for further public comment and the author of the MIP to address concerns about the proposal.

If the MIP collaborators approve, the MIP editor will assign the MIP a id (generally the issue or PR number related to the MIP), type, layer, give it status “Draft” and add it to the git repository. The MIP editor will not unreasonably deny an MIP. Reasons for denying MIP status include duplication of effort, being technically unsound, not providing proper motivation or addressing backwards compatibility, or not in keeping with the MinexCoin philosophy.

It occasionally becomes necessary to transfer ownership of MIPs to a new champion. In general, we'd like to retain the original author as a co-author of the transferred MIP, but that's really up to the original author. A good reason to transfer ownership is because the original author no longer has the time or interest in updating it or following through with the MIP process, or has fallen off the face of the 'net (i.e. is unreachable or not responding to email). A bad reason to transfer ownership is because you don't agree with the direction of the MIP. We try to build consensus around an MIP, but if that's not possible, you can always submit a competing MIP.

If you are interested in assuming ownership of an MIP, send a message asking to take over, addressed to both the original author and the MIP editor. If the original author doesn't respond to email in a timely manner, the MIP editor will make a unilateral decision (it's not like such decisions can't be reversed :).

MIP Header Preamble
-------------------

The headers must appear in the following order. Headers marked with "*" are optional and are described below. All other headers are required.

-   ID: ID number is determined by the MIP editor or "?" before being assigned;
-   Title: MIP title, maximum 44 characters;
-   Author: list of author's real names and email address;
-   Type: <Standard | Informational | Meta>;
-   *Layer: <Consensus(Soft Fork | Hard Fork) | Networking | Interface | Application>;
-   Status: <Draft | Active | Accepted | Deferred | Rejected | Withdrawn | Final | Replaced>;
-   *Requires: MIP ID(s);
-   *Replaces: MIP ID(s);
-   *Superseded-By: MIP ID;
-   *Discussions-To: email address;
-   Created: date created on, in ISO 8601 (yyyy-mm-dd) format;

The Author header lists the names and the email addresses of all the authors/owners of the MIP. The format of the Author header value must be

Random J. User &lt;address@dom.ain&gt;

If there are multiple authors, each should be on a separate line.

While an MIP is in private discussions (usually during the initial Draft phase), a Discussions-To header will indicate the mailing list or URL where the MIP is being discussed. No Discussions-To header is necessary if the MIP is being discussed privately with the author.

The Created header records the date that the MIP was assigned a ID. Header should be in yyyy-mm-dd format, e.g. 2001-08-14.

MIPs may have a Requires header, indicating the MIP ID that this MIP depends on.

MIPs may also have a Superseded-By header indicating that an MIP has been rendered obsolete by a later document; the value is the ID of the MIP that replaces the current document. The newer MIP must have a Replaces header containing the ID of the MIP that it rendered obsolete.

MIP Format And Structure
------------------------

MIPs should be written in [markdown] format. Image files should be included in a subdirectory for that MIP.

Each MIP should have the following parts:

-   Preamble - header containing metadata about the MIP describe above.

<!-- -->

-   Abstract - a short (~200 word) description of the technical issue being addressed.

<!-- -->

-   Motivation (*optional) - The motivation is critical for MIPs that want to change the MinexCoin protocol. It should clearly explain why the existing protocol specification is inadequate to address the problem that the MIP solves. MIP submissions without sufficient motivation may be rejected outright.

<!-- -->

-   Specification - The technical specification should describe the syntax and semantics of any new feature. The specification should be detailed enough to allow competing, interoperable implementations.

<!-- -->

-   Rationale - The rationale fleshes out the specification by describing what motivated the design and why particular design decisions were made. It should describe alternate designs that were considered and related work, e.g. how the feature is supported in other languages. The rationale may also provide evidence of consensus within the community, and should discuss important objections or concerns raised during discussion.

<!-- -->

-   Backwards Compatibility - All MIPs that introduce backwards incompatibilities must include a section describing these incompatibilities and their severity. The MIP must explain how the author proposes to deal with these incompatibilities. MIP submissions without a sufficient backwards compatibility treatise may be rejected outright.

<!-- -->

-   Test Cases - Test cases for an implementation are mandatory for MIPs that are affecting consensus changes. Other MIPs can choose to include links to test cases if applicable.

<!-- -->

-   Implementations - The implementations must be completed before any MIP is given status “Final”, but it need not be completed before the MIP is accepted. While there is merit to the approach of reaching consensus on the specification and rationale before writing code, the principle of “rough consensus and running code” is still useful when it comes to resolving many discussions of API details.

MIP Editor Responsibilities and Workflow
--------------------------------------

For each new MIP that comes in, an editor does the following:

-   Read the MIP to check if it is ready: sound and complete. The ideas must make technical sense, even if they don't seem likely to be accepted.
-   The title should accurately describe the content.
-   Edit the MIP for language (spelling, grammar, sentence structure, etc.), markup (Github flavored Markdown), code style.

If the MIP isn't ready, the editor will send it back to the author for revision, with specific instructions.

Once the MIP is ready for the repository, the MIP editor will:

-   Assign an MIP id (generally the PR number or, if preferred by the author, the Issue # if there was discussion in the Issues section of this repository about this MIP).
-   Accept the corresponding pull request.
-   List the MIP in [README.md](../README.md).
-   Send a message back to the MIP author with next step.

Many MIPs are written and maintained by developers with write access to the MinexCoin codebase. The MIP editors monitor MIP changes, and correct any structure, grammar, spelling, or markup mistakes we see.

The editors don't pass judgment on MIPs. We merely do the administrative & editorial part.

MIP Editors
-----------

The current MIP editors are

` * Roman Hulenko <rhulenko@minexsystems.com>`

MIP Work Flow
-------------

The MIP repository Collaborators change the MIPs status. Please send all MIP-related email to the MIP Collaborators, which is listed under MIP Editors above. Also see MIP Editor Responsibilities & Workflow.

Standard MIPs consist of two parts, a design document and implementation. The MIP should be reviewed and accepted before an implementation is begun, unless an implementation will aid people in studying the MIP.

For an MIP to be accepted it must meet certain minimum criteria. It must be a clear and complete description of the proposed enhancement. The enhancement must represent a net improvement. The proposed implementation, if applicable, must be solid and must not complicate the protocol unduly.

Once an MIP has been accepted, the implementations must be completed. When the implementation is complete and accepted by the community, the status will be changed to “Final”.

An MIP can also be assigned status “Deferred”. The MIP author or editor can assign the MIP this status when no progress is being made on the MIP. Once an MIP is deferred, the MIP editor can re-assign it to draft status.

An MIP can also be “Rejected”. Perhaps after all is said and done it was not a good idea. It is still important to have a record of this fact.

MIPs can also be superseded by a different MIP, rendering the original obsolete.

The possible paths of the status of MIPs are as follows:

<img src=./mip-0/process.png>

Some Informational and Meta MIPs may also have a status of “Active” if they are never meant to be completed. E.g. MIP 0 (this MIP).

History
-------

This document was derived heavily from [Bitcoin's BIP-0002] written by Luke Dashjr <luke+bip@dashjr.org> and from [Ethereum's EIP-0001] written by Martin Becze <mb@ethereum.org>, Hudson Jameson <hudson@ethereum.org> which in turn was derived from [Python's PEP-0001]. In many places text was simply copied and modified.

  [the MinexCoin topic in bitcointalk.org]: https://bitcointalk.org/index.php?topic=2217037.0
  [pull request]: https://github.com/minexcoin/MIPs/pulls
  [the Issues section of this repository]: https://github.com/minexcoin/MIPs/issues
  [markdown]: https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet
  [Bitcoin's BIP-0002]: https://github.com/bitcoin/bips
  [Ethereum's EIP-0001]: https://github.com/ethereum/EIPs
  [Python's PEP-0001]: https://www.python.org/dev/peps/
