This is the suggested template for new MIPs.

Note that an MIP number will be assigned by an editor. When opening a pull request to submit your MIP, please use an abbreviated title in the filename, `mip-draft_title_abbrev.md`.

## Preamble

    ID: <to be assigned>
    Title: <MIP title>
    Author: <list of authors' names and email addresses>
    Type: <Standard | Informational | Meta>
    Layer (*optional): <Consensus(Soft Fork | Hard Fork) | Networking | Interface | Application>
    Status: Draft
    Requires (*optional): <MIP ID(s)>
    Replaces (*optional): <MIP ID(s)>
    Created: <date created on, in ISO 8601 (yyyy-mm-dd) format>

## Abstract
A short (~200 word) description of the technical issue being addressed.

## Motivation
The motivation is critical for MIPs that want to change the MinexCoin protocol. It should clearly explain why the existing protocol specification is inadequate to address the problem that the MIP solves. MIP submissions without sufficient motivation may be rejected outright.

## Specification
The technical specification should describe the syntax and semantics of any new feature. The specification should be detailed enough to allow competing, interoperable implementations. 

## Rationale
The rationale fleshes out the specification by describing what motivated the design and why particular design decisions were made. It should describe alternate designs that were considered and related work, e.g. how the feature is supported in other languages. The rationale may also provide evidence of consensus within the community, and should discuss important objections or concerns raised during discussion.

## Backwards Compatibility
All MIPs that introduce backwards incompatibilities must include a section describing these incompatibilities and their severity. The MIP must explain how the author proposes to deal with these incompatibilities. MIP submissions without a sufficient backwards compatibility treatise may be rejected outright.

## Test Cases
Test cases for an implementation are mandatory for MIPs that are affecting consensus changes. Other MIPs can choose to include links to test cases if applicable.

## Implementation
The implementations must be completed before any MIP is given status "Final", but it need not be completed before the MIP is accepted. While there is merit to the approach of reaching consensus on the specification and rationale before writing code, the principle of "rough consensus and running code" is still useful when it comes to resolving many discussions of API details.