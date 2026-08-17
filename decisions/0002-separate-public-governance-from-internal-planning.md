<!-- markdownlint-disable-file -->

# ADR-0002: Separate public governance from internal planning

| Field | Value |
|-------|-------|
| Status | Proposed |
| Date | 2026-08-10 |
| Deciders | data-privacy-stack Technical Steering Committee |
| Consulted | Project maintainers |
| Informed | data-privacy-stack community and MVG adopters |
| Related | [ADR-0001](./0001-per-project-mvg-file-distribution.md) |

## Context and Problem Statement

The `data-privacy-stack` organization needs two kinds of cross-organization
content:

- Public governance artifacts, including reusable templates, policies,
  operating principles, adoption guidance, and accepted organization-level
  decisions.
- Internal planning records, including assignments, target dates, readiness
  gaps, private repository details, dependencies, and work status.

These categories have different audiences. MVG is public, TSC-owned, and
already contains organization policies and project templates. It is the right
home for approved governance artifacts, but it is not an appropriate home for
internal operational planning.

Project-specific adoption work presents a third ownership boundary. Each
project's maintainers should plan and execute that work in the project's own
backlog rather than in MVG or a central organization rollout backlog.

## Decision Drivers

- Organization-level public artifacts should have a public, TSC-owned home.
- Internal repository details, assignments, dates, and dependencies must
  remain visible only to the people coordinating the work.
- Approved governance decisions and reusable standards benefit from public
  review and visibility.
- Project maintainers remain accountable for applying MVG in their own
  repositories.
- The model should not require another repository or duplicate delivery work
  across multiple backlogs.

## Options Considered

### Option A: Keep all work in a product repository

Keep organization-level planning and public governance drafts in one product
repository.

**Pros:**

- Internal planning can remain private.
- No new convention is required.

**Cons:**

- A product repository is the wrong ownership boundary for organization work.
- Access must be extended through a repository with a different purpose.
- Approved public governance artifacts remain difficult to discover.

### Option B: Create a private governance-operations repository

Create a dedicated private repository for organization-level planning issues
and supporting documents.

**Pros:**

- Provides durable repository-backed issues.
- Separates internal planning from public MVG content.

**Cons:**

- Adds a repository whose only purpose is maintaining governance work.
- Adds another access list and contributor surface.

### Option C: Track all organization work publicly in MVG

Use MVG issues and documents for both public governance changes and internal
cross-organization planning.

**Pros:**

- MVG is already TSC-owned and publicly discoverable.
- No additional planning system is required.

**Cons:**

- Public issues and documents would expose private repository names,
  readiness gaps, assignments, dates, and dependencies.
- External adopters would see operational details that do not help them use
  MVG.

### Option D: Use an access-controlled organization Project and project backlogs

Use an access-controlled organization-level GitHub Project for internal work
on MVG and other cross-organization concerns. Publish approved governance
artifacts in MVG. Keep implementation and adoption work for a specific project
in that project's backlog.

**Pros:**

- No additional repository is required.
- Internal planning is visible to the TSC and selected maintainers.
- Public MVG content remains focused on reusable governance.
- Project maintainers retain ownership of project-specific work.

**Cons:**

- Draft items in the access-controlled Project are lighter-weight than
  repository issues.
- Public pull requests must stand on their own without links to private
  context.

## Decision

We choose **Option D: Use an access-controlled organization Project and
project backlogs**.

MVG remains the canonical public home for reusable project templates,
organization policies, operating principles, adoption guidance, and accepted
organization-level ADRs. Public MVG issues and pull requests contain only
information intended for publication.

An access-controlled organization-level GitHub Project holds internal planning
for changes to MVG and other cross-organization concerns. Its draft items may
contain assignments, target dates, private dependencies, readiness gaps, and
links to private work. Access is limited to the TSC and selected maintainers.

Each project owns the work required to adopt or update MVG in that project.
That implementation remains in the project's backlog and repository. The
access-controlled Project does not duplicate project delivery backlogs.

Before public MVG content is opened for review, its owner removes internal
repository details and ensures that the proposal is independently
understandable without access to the private planning context.

## Consequences

**Positive:**

- Approved governance artifacts have a canonical, public, TSC-owned home.
- Internal planning remains limited to its intended audience.
- Projects retain accountability for their own adoption work.
- No new repository or duplicate central rollout backlog is required.

**Negative / Costs:**

- GitHub Project draft items provide less durable discussion history than
  repository-backed issues.
- Public proposals require a deliberate sanitization step.
- Status across project-specific adoption efforts is not centralized in MVG.

**Mitigations:**

- Draft items use clear outcomes, acceptance criteria, and links to resulting
  public artifacts.
- Public MVG pull requests include only the context needed to review the
  governance change.
- Project-specific work remains discoverable through each project's normal
  backlog and pull-request history.

## Confirmation

The decision is working when public MVG proposals can be reviewed without
private context, internal planning remains limited to its intended audience,
and project maintainers can manage adoption without a duplicate central
delivery backlog.

We revisit the decision if Project draft items cannot support internal
coordination, contributors cannot understand public MVG proposals on their
own, or project adoption repeatedly requires central delivery coordination.

## References

- [MVG repository README](../README.md)
- [ADR-0001: Per-project distribution of MVG project documents](./0001-per-project-mvg-file-distribution.md)