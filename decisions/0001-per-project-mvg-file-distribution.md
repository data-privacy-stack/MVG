<!-- markdownlint-disable-file -->

# ADR-0001: Per-project distribution of MVG project documents

| Field | Value |
|-------|-------|
| Status | Proposed |
| Date | 2026-08-10 |
| Deciders | data-privacy-stack Technical Steering Committee |
| Consulted | Project maintainers |
| Informed | data-privacy-stack community |
| Related | [ADR-0002](./0002-separate-public-governance-from-internal-planning.md) |

## Context and Problem Statement

MVG defines a set of project-scoped governance files (`LICENSE`,
`CODE_OF_CONDUCT.md`, `CONTRIBUTING.md`, `GOVERNANCE.md`, `MAINTAINERS.md`,
`SECURITY.md`) that every project repository should carry. We need to decide
whether each project holds its own copy at the repository root or points to a
canonical version in MVG.

## Decision Drivers

- Contributors should find governance files in the repository where they work.
- Repository and ecosystem tooling expects governance files at conventional
  paths within each project.
- Projects need to customize licenses, maintainer lists, security contacts,
  and other project-specific details.
- MVG should remain the canonical reusable template rather than a collection
  of project-specific variants.

## Options Considered

### Option A: Copy and adapt files in each project

Each project keeps its own governance files at the repository root and adapts
the MVG templates to its needs.

**Pros:**

- Contributors and tooling find files where expected.
- Projects can maintain accurate project-specific details.
- A clone contains the complete governance context.

**Cons:**

- Template improvements do not propagate automatically.
- Projects must review their copies for drift.

### Option B: Point projects to files in MVG

Projects reference centralized governance files through links, symlinks, or
submodules.

**Pros:**

- Shared content has one source.
- Template updates are immediately visible.

**Cons:**

- GitHub interfaces and ecosystem tooling may not recognize the files.
- Contributors must leave the project repository to understand its governance.
- Project-specific fields and policies become harder to maintain.

## Decision

We choose **Option A: Copy and adapt files in each project**.

Each project holds its own governance files at the repository root, adapted
for project-specific fields. MVG is the canonical template; project
repositories are the maintained instances.

## Consequences

**Positive:**

- Contributors and tooling find governance files where expected.
- Projects can adapt files to their licenses, maintainers, security contacts,
  and operating needs.
- Each project retains ownership and review responsibility for its governance.

**Negative / Costs:**

- Project copies can drift from the current MVG template.
- Template improvements require deliberate adoption by project maintainers.

**Mitigations:**

- MVG adoption guidance identifies the files and fields maintainers review.
- Projects document intentional deviations in `GOVERNANCE.md` or a
  project-level ADR.
- Each project tracks adoption and updates in its own backlog and repository.

## Confirmation

The decision is working when contributors and tooling consistently find the
required governance files in each project and maintainers can explain any
intentional differences from MVG.

We revisit the decision if repository tooling reliably supports centralized
governance references without degrading contributor access or project-specific
customization.

## References

- [MVG project-docs template](../project-docs/)
- [ADR-0002: Separate public governance from internal planning](./0002-separate-public-governance-from-internal-planning.md)