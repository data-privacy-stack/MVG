<!-- markdownlint-disable-file -->

# MVG Decisions

This folder holds Architecture Decision Records (ADRs) for the
`data-privacy-stack` organization. Each ADR captures a decision that affects
more than one project or that sets policy for the organization as a whole.

## What Belongs Here

- Governance policy decisions
- Cross-project standards, such as how MVG project documents are distributed
- Decisions that define the boundary between public governance and internal
  organization planning

Project-scoped architecture decisions belong in the project repository, not
here.

## Format

We use a MADR-lite structure. Each ADR includes:

- Metadata: status, date, deciders, consulted, informed, related decisions
- Context and problem statement
- Decision drivers
- Options considered, with pros and cons
- Decision and rationale
- Consequences: positive effects, costs, and mitigations
- Confirmation signals

Copy [`0000-adr-template.md`](./0000-adr-template.md) as the starting point
for a new ADR.

## Numbering

ADRs are numbered sequentially in the order they are proposed
(`NNNN-short-slug.md`). Numbers are never reused, even for superseded ADRs.

## Status Lifecycle

| Status | Meaning |
|--------|---------|
| Proposed | Under discussion through a pull request |
| Accepted | Merged and in effect |
| Superseded by NNNN | Replaced by a later ADR that links to this decision |
| Deprecated | No longer applicable and has no replacement |

Merging a PR changes the status from Proposed to Accepted and stamps the merge
date.

## Reviewing an ADR

Comment on the pull request that proposes or updates the ADR. Once discussion
converges, the TSC or a delegated approver merges it. Non-trivial changes to
an accepted ADR use a new ADR that supersedes the original rather than editing
the historical decision.

## Index

| ID | Title | Status |
|----|-------|--------|
| [0001](./0001-per-project-mvg-file-distribution.md) | Per-project distribution of MVG project documents | Proposed |
| [0002](./0002-separate-public-governance-from-internal-planning.md) | Separate public governance from internal planning | Proposed |