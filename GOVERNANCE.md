# Symbl.ai Community Governance

This document defines the Symbl.ai's project governance.

## Overview

**Symbl.ai** is committed to building an open, inclusive, productive and self-governing open source community focused on building high quality tooling that enables users to consume, use, and access the Symbl.ai Platform. The community is governed by this document with the goal of defining how community should work together to achieve this goal.

## Code Repositories

The following code repositories are governed by the Symbl.ai community and maintained under the `symblai\community` organization.

* **[Community](https://github.com/symblai/community):** This administrative community repository
* **[Getting Start Samples](https://github.com/symblai/getting-started-samples):** The Example/Samples repository for the Symbl.ai Community

## Community Roles

* **Users:** Members that engage with the Symbl.ai community via any medium (Slack, GitHub, mailing lists, etc.).
* **Contributors:** Regular contributions to projects (documentation, code reviews, responding to issues, participation in proposal discussions, contributing code, etc.). 
* **Maintainers**: The Symbl.ai project leaders. They are responsible for the overall health and direction of projects; final reviewers of PRs and responsible for releases. Some Maintainers are responsible for one or more components within the Symbl.ai organization, acting as technical leads for those components. Maintainers are expected to contribute code and documentation, review PRs including ensuring quality of code, triage issues, proactively fix bugs, and perform maintenance tasks for these components.

### Maintainers

New maintainers must be nominated by an existing maintainer and must be elected by a supermajority of existing maintainers. Likewise, maintainers can be removed by a supermajority of the existing maintainers or can resign by notifying one of the maintainers.

### Supermajority

A supermajority is defined as two-thirds of members in the group.
A supermajority of [Maintainers](#maintainers) is required for certain
decisions as outlined above. A supermajority vote is equivalent to the number of votes in favor being at least twice the number of votes against. For example, if you have 5 maintainers, a supermajority vote is 4 votes. Voting on decisions can happen on the mailing list, GitHub, Slack, email, or via a voting service, when appropriate. Maintainers can either vote "agree, yes, +1", "disagree, no, -1", or "abstain". A vote passes when supermajority is met. An abstain vote equals not voting at all.

### Decision Making

Ideally, all project decisions are resolved by consensus. If impossible, any
maintainer may call a vote. Unless otherwise specified in this document, any
vote will be decided by a supermajority of maintainers.

## Proposal Process

One of the most important aspects in any open source community is the concept
of proposals. Large changes to the codebase and / or new features should be
preceded by a proposal in our community repo. This process allows for all
members of the community to weigh in on the concept (including the technical
details), share their comments and ideas, and offer to help. It also ensures
that members are not duplicating work or inadvertently stepping on toes by
making large conflicting changes.

The project roadmap is defined by accepted proposals.

Proposals should cover the high-level objectives, use cases, and technical
recommendations on how to implement. In general, the community member(s)
interested in implementing the proposal should be either deeply engaged in the
proposal process or be an author of the proposal.

The proposal should be documented as a separated markdown file pushed to the root of the 
`design` folder in the [Community](https://github.com/symblai/community/tree/main/design)
repository via PR. The name of the file should follow the name pattern `<short
meaningful words joined by '-'>_design.md`, e.g:
`restore-hooks-design.md`.

Use the [Proposal Template](https://github.com/symblai/community/blob/main/design/_template.md) as a starting point.

### Proposal Lifecycle

The proposal PR can follow the GitHub lifecycle of the PR to indicate its status:

* **Open**: Proposal is created and under review and discussion.
* **Merged**: Proposal has been reviewed and is accepted (either by consensus or through a vote).
* **Closed**: Proposal has been reviewed and was rejected (either by consensus or through a vote).

## Lazy Consensus

To maintain velocity in a project, the concept of [Lazy
Consensus](http://en.osswiki.info/concepts/lazy_consensus) is practiced. Ideas
and / or proposals should be shared by maintainers via
GitHub with the appropriate maintainers are tagged. Out of respect for other contributors,
major changes should also be accompanied by a ping on Slack or a note on the
Community mailing list as appropriate. Author(s) of proposal, Pull Requests,
issues, etc.  will give a time period of no less than five (5) working days for
comment and remain cognizant of popular observed world holidays.

Other maintainers may chime in and request additional time for review, but
should remain cognizant of blocking progress and abstain from delaying
progress unless absolutely needed. The expectation is that blocking progress
is accompanied by a guarantee to review and respond to the relevant action(s)
(proposals, PRs, issues, etc.) in short order.

Lazy Consensus is practiced for all **Community** projects in `symblai` org, including
the main project repository and the additional repositories.

Lazy consensus does _not_ apply to the process of:

* Removal of maintainers from the Symbl.ai Community

## Updating Governance

All substantive changes in Governance require a supermajority agreement by all maintainers.
