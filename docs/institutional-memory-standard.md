# Institutional Memory Standard

## Purpose

This document defines the minimum institutional-memory model for The Great Academy. It supports the mission of preserving knowledge, making uncertainty visible, distinguishing evidence from belief, and ensuring that decisions remain traceable to their rationale and outcomes.

This standard is a Phase 1 working governance document. It does not override the Constitution. It clarifies how institutional knowledge is organized and managed within the repository.

## Authority and precedence

1. Constitution and valid constitutional amendments
2. Approved institutional policies and governance decisions
3. Approved architecture and institutional standards
4. Approved project specifications and plans
5. Research, evidence, and working documents
6. Operational records and implementation artifacts

A lower-level document cannot silently override a higher-level constitutional requirement.

## Core categories

The repository distinguishes material by classification:

- CANONICAL
  - Authoritative principles, policies, architecture, and constitutional material
- WORKING
  - Drafts, proposals, designs, and evolving material under review
- RESEARCH
  - Evidence, references, experiments, claims under review, and learned findings
- PROJECT
  - Records for project-specific work that applies Academy principles
- ARCHIVED
  - Superseded, historical, or preserved material retained for provenance

Classification and epistemic status must remain separate. A record may be canonical and still be uncertain or under review. A research record may be strong evidence without becoming policy.

## Epistemic and workflow dimensions

These dimensions must remain distinct:

### 1. Reasoning type
- OBSERVATION
- INFERENCE
- HYPOTHESIS
- PROPOSAL
- UNKNOWN

The reasoning type describes how a statement is being held, not whether it is formally approved.

### 2. Evidence assessment
- SUPPORTED
- CONTRADICTED
- INCONCLUSIVE
- UNASSESSED

This describes the current state of the evidence relevant to a claim.

### 3. Workflow state
- DRAFT
- IN REVIEW
- APPROVED
- SUPERSEDED
- ARCHIVED

This describes the lifecycle of the record itself.

### 4. Decision status
- PROPOSED
- APPROVED
- REJECTED
- DEFERRED
- REVOKED
- SUPERSEDED

This describes the institutional decision status of a proposal or action.

### 5. Implementation outcome
- PLANNED
- IN PROGRESS
- COMPLETED
- BLOCKED
- FAILED
- WITHDRAWN

This describes what happened after a decision was authorized.

These fields must not be collapsed into a single status field.

## Required institutional-memory flow

The Academy must preserve the following lifecycle:

QUESTION → RESEARCH → EVIDENCE → INTERPRETATION → DECISION → ACTION → RESULT → LESSON

This is the minimum evidence-oriented workflow for first release. It must be traceable, reviewable, and reversible where necessary.

## Record types

This standard describes conceptual record types for Phase 1. These are not claims that the repository already implements automated workflow tooling, database tables, role-based access systems, or audit infrastructure.

### 1. Question record
Purpose: define the issue or inquiry to investigate.

Required fields:
- id
- title
- description
- created_by
- created_at
- status
- related_project or none
- related_concern

Optional fields:
- priority
- tags
- source_context

### 2. Source record
Purpose: preserve provenance for research inputs.

Required fields:
- id
- title
- source_type
- source_reference
- author
- publication_date (if known)
- access_date
- provenance_note
- created_by
- created_at

Optional fields:
- url
- document_hash
- citation
- access_notes

### 3. Claim record
Purpose: represent a fact, assertion, or statement to be assessed.

Required fields:
- id
- question_id
- text
- created_by
- created_at
- reasoning_type
- review_status

Optional fields:
- confidence
- related_sources
- notes

### 4. Evidence record
Purpose: connect claims to support, contradiction, or ambiguity.

Required fields:
- id
- claim_id
- source_id
- evidence_assessment
- summary
- created_by
- created_at

Optional fields:
- excerpt
- strengths
- limitations
- uncertainty_note

### 5. Interpretation record
Purpose: explain what the evidence means.

Required fields:
- id
- question_id
- summary
- reasoning_type
- evidence_assessment
- uncertainty_note
- created_by
- created_at

Optional fields:
- assumptions
- limitations
- conflicting interpretations

### 6. Decision record
Purpose: record an institutional choice and its rationale.

Required fields:
- id
- question_id
- decision_status
- rationale
- alternatives_considered
- evidence_summary
- proposer
- accountable_owner
- approver
- approval_required
- approved_at (required only when decision_status is APPROVED)
- created_by
- created_at

Conditional requirement:
- approval_required is required only when the decision is being evaluated for approval.
- approver and approved_at are required only when decision_status = APPROVED.
- proposer is required for all proposals.
- accountable_owner is required for all actions derived from a decision.

Optional fields:
- risk_summary
- follow_up_required
- expiry_date
- supersedes

### 7. Action record
Purpose: connect an authorized decision to an action.

Required fields:
- id
- decision_id
- title
- description
- owner
- created_by
- created_at
- status

Optional fields:
- due_date
- dependencies
- linked_project
- notes

### 8. Result record
Purpose: capture observed outcomes of an action.

Required fields:
- id
- action_id
- summary
- outcome_status
- observed_at
- created_by

Optional fields:
- metrics
- evidence
- deviations
- lessons_preliminary

### 9. Lesson record
Purpose: preserve learning from success, failure, correction, and revision.

Required fields:
- id
- question_id or action_id
- summary
- lesson_type
- created_by
- created_at

Optional fields:
- review_after
- related_decisions
- related_sources

### 10. Audit record
Purpose: preserve history of changes, approvals, and corrections.

Required fields:
- id
- record_type
- record_id
- event_type
- actor
- timestamp
- before_summary
- after_summary

Optional fields:
- reason
- approval_reference

## Integrity rules

The following rules are required:

- No claim may be treated as fact without a source or provenance.
- Contradictory evidence must remain visible; it may not be silently overwritten.
- Interpretation must be clearly separated from evidence.
- Decision records must record rationale and approval authority only when actual approval is required and occurs.
- A decision may be revised, rejected, or superseded, but never silently erased.
- Archived records must retain their provenance and original date.
- Source identity must include date accessed and provenance note when applicable.
- Rejected or superseded records must remain accessible for institutional memory.
- A record must not be marked approved without a clear approval reference and status.
- A proposed or rejected decision must not require approval metadata that belongs only to an approved decision.

## Minimum repository conventions

The repository should preserve:
- README.md as the high-level entry point
- CONSTITUTION.md as the governing authority
- docs/ as the working repository for human-readable process documents
- research/ for evidence and research material once Phase 1 is further developed
- projects/ for project-related records when formalized
- archive/ or archived/ only when a material classification requires historical retention

The root Constitution remains authoritative. The repository should not duplicate or conflict with it.

## Review and maintenance

A record is only as strong as its traceability. All institutional-memory records should be reviewed for:
- source clarity
- uncertainty labeling
- authority status
- consistency with the Constitution
- risk or consequence of incorrect classification

This standard is intended to support the Academy’s mission without creating unnecessary process overhead.

## Exit criteria for this standard

This standard is considered usable when:
- all required record types are defined
- classifications are clear
- evidence and uncertainty are explicitly distinguished
- decision and action history are traceable
- the repository can explain how records are preserved and reviewed
- the standard remains proportionate to Phase 1 and does not imply capabilities that do not yet exist
```

{"path":"docs/research-evidence-record-template.md","content":"# Research and Evidence Record Template

## Purpose

Use this template when recording research, evidence, or claim assessment. Each record must preserve source identity, uncertainty, and review status.

## Required fields

### Metadata
- Record ID
- Title
- Question ID
- Created by
- Created at
- Last updated
- Review status
- Classification
- Reasoning type

### Source and provenance
- Source title
- Source type
- Author or publisher
- URL or reference
- Publication date (if known)
- Access date
- Provenance note
- Source reliability note

### Claim and evidence
- Claim summary
- Claim status
- Evidence assessment
- Supporting evidence
- Contradictory evidence
- Inconclusive evidence
- Uncertainty note
- Limitations

### Review and traceability
- Reviewed by
- Review date
- Approval status
- Related decision ID
- Related project
- Related source IDs

## Suggested markdown structure

```markdown
# Research Record: [Title]

## Question
[What question is this record trying to answer?]

## Source
- Title:
- Type:
- Author:
- Publication date:
- Accessed on:
- URL/reference:
- Provenance note:
- Reliability note:

## Claim
[State the claim clearly.]

## Reasoning type
- OBSERVATION / INFERENCE / HYPOTHESIS / PROPOSAL / UNKNOWN

## Evidence assessment
- SUPPORTED / CONTRADICTED / INCONCLUSIVE / UNASSESSED

## Findings
### Supporting evidence
- ...

### Contradictory evidence
- ...

### Inconclusive or missing evidence
- ...

## Researcher interpretation
[State what the researcher infers from the evidence.]

## Limitations
- ...

## Uncertainty
- ...

## Review status
- DRAFT / IN REVIEW / APPROVED / SUPERSEDED / ARCHIVED

## Related decisions or actions
- ...

## Notes
- ...
```

## Requirements

- Record provenance before claiming a fact is supported.
- Preserve contradictory evidence rather than deleting it.
- State uncertainty explicitly.
- Distinguish evidence from interpretation.
- Link the record to a question or decision if possible.
- Do not silently convert a hypothesis into an accepted fact.
- Do not treat a source as automatically proving all claims it contains.
- Keep the source statement, the researcher interpretation, and the institutional assessment distinct.

## Review checklist

- Source is identified
- Reliability note is included where relevant
- Date accessed is recorded
- Claim is clearly stated
- Evidence is supported or contradicted explicitly
- Uncertainty is noted
- Related decision or action is recorded if applicable
- Document status is clear
- Approval or review state is described accurately
```

{"path":"docs/decision-record-template.md","content":"# Decision Record Template

## Purpose

This template captures decisions, rationale, evidence, and follow-up actions. It is designed to distinguish a proposed decision from an authorized decision and to preserve the chain from research to action to outcome.

## Required fields

- Decision ID
- Question ID
- Decision title
- Proposed by
- Created at
- Decision status
- Decision owner
- Reviewers
- Approval authority
- Rationale
- Alternatives considered
- Evidence summary
- Risks and considerations
- Decision date
- Implementation outcome

## Decision status rules

- PROPOSED: no approval is yet recorded; a proposal is not an authorized action.
- APPROVED: approval authority, approval date, and approval reference must be recorded.
- REJECTED: preserve the rationale and reason for rejection.
- DEFERRED: record the reason and conditions for reconsideration.
- REVOKED: record the reason and reference the superseding decision if any.
- SUPERSEDED: preserve the previous record and the reason for supersession.

## Suggested markdown structure

```markdown
# Decision Record: [Title]

## Question
[What problem or uncertainty led to this decision?]

## Proposal
- Proposed by:
- Proposed on:
- Decision status:

## Decision owner
- Name / role / accountable authority

## Required approval authority
- Who must approve before action proceeds?
- Required only when the decision is being reviewed for approval.

## Rationale
[Why this decision was chosen.]

## Alternatives considered
- Option 1: ...
- Option 2: ...
- Option 3: ...

## Evidence summary
- Sources reviewed:
- Supporting evidence:
- Contradictory evidence:
- Uncertainty and limitations:

## Risk and consequence
- What could go wrong?
- What are the trade-offs?
- What is the expected impact?

## Authorization
- Approved by:
- Approval date:
- Approval reference:
- Required only for APPROVED decisions.

## Action
- What action follows this decision?
- Who is accountable?
- Deadline or review date:

## Outcome
- Status: PLANNED / IN PROGRESS / COMPLETED / BLOCKED / FAILED
- Result summary:
- Evidence of outcome:
- Lessons learned:

## History
- Proposed:
- Approved:
- Rejected:
- Deferred:
- Revoked:
- Superseded:
- Archived:
```

## Review rules

- A proposal is not an approval.
- An approved decision must have a clear authority and date.
- A decision must be traceable to the evidence that informed it.
- A new decision may supersede an earlier decision, but the earlier record must remain visible.
- An action without a decision should be treated as an exception or as unapproved work.
- A proposed or rejected decision must not require approval metadata that belongs only to an approved decision.

## Closure requirements

A decision record is complete when:
- rationale is documented
- evidence is linked
- authority is recorded when approval occurs
- action or deferral is stated
- outcome is recorded when known
- history is preserved
```

{"path":"docs/migration-register.md","content":"# Phase 1 Migration Register

## Purpose

This register tracks existing institutional materials that may require classification, migration, or preservation. It does not invent new documents. It only records what currently exists and what needs human review or explicit approval.

## Current repository baseline

Repository:
- https://github.com/marksmanag/The-Great-Academy-

Canonical branch:
- main

Current commit inspected:
- afea3679549043c6c21283c4f577ebbff3ce9399

## Register

| Item | Current path | Current known classification | Proposed classification | Proposed destination | Reason | Duplicate/conflict risk | Approval required | Migration status | Verification method |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| README | README.md | PENDING REVIEW | CANONICAL | root | Entry point and mission statement | Low | Repository owner / maintainer | PRESERVE | File review |
| Constitution | CONSTITUTION.md | PENDING REVIEW | CANONICAL | root | Governing principles and constitutional authority | Low | Repository owner / maintainer | PRESERVE | File review |
| Governance | CONTRIBUTING.md | PENDING REVIEW | CANONICAL | root | Contribution and review process | Low | Maintainer review | PRESERVE | File review |
| Code of Conduct | CODE_OF_CONDUCT.md | PENDING REVIEW | CANONICAL | root | Community standards | Low | Maintainer review | PRESERVE | File review |
| Security | SECURITY.md | PENDING REVIEW | CANONICAL | root | Security and reporting rules | Low | Maintainer review | PRESERVE | File review |
| Roadmap | ROADMAP.md | PENDING REVIEW | CANONICAL | root | Phase planning and direction | Low | Maintainer review | PRESERVE | File review |
| License | LICENSE | PENDING REVIEW | CANONICAL | root | Legal foundation | Low | Legal/maintainer review | PRESERVE | File review |
| CODEOWNERS | .github/CODEOWNERS | PENDING REVIEW | CANONICAL | .github/ | Ownership and review responsibility | Low | Maintainer review | PRESERVE | File review |
| Future directory structure | README section listing constitution/, academy/, architecture/, research/, projects/, docs/ | FUTURE / NOT IMPLEMENTED | WORKING or FUTURE | To be created only when approved | Planned future structure | Medium | Owner approval | PENDING REVIEW | Directory review |
| Branch work | branch names like phase-1-institutional-memory, phase-1-planning | UNKNOWN | UNKNOWN | Only if approved | May represent draft work or planning branches | Medium | Owner review | PENDING REVIEW | Branch metadata review |

## Migration rules

- Preserve root constitutional documents unless a formal governance decision changes them.
- Do not move a document without a traceable reason and a corresponding record.
- Any migration must be reviewed for duplicate authority or conflicts with the Constitution.
- Future directories should be created only when there is a clear purpose and defined content.
- Draft material must be clearly marked as WORKING or RESEARCH and not silently treated as canonical.
- A document may not be labeled CANONICAL solely because it appears to be a core policy document. It requires current review and explicit governance status.

## Existing material to preserve unchanged

The following should remain authoritative unless a future, approved change requires revision:
- README.md
- CONSTITUTION.md
- CONTRIBUTING.md
- CODE_OF_CONDUCT.md
- SECURITY.md
- ROADMAP.md
- LICENSE
- .github/CODEOWNERS

## Remaining migration uncertainties

- Whether any unmerged branch contains actual Phase 1 documents not visible in main
- Whether the owner intends to populate the future directories now or defer them
- Whether phase names correspond to actual work or only planning
- Whether the root documents should be formally classified as CANONICAL without a current governance review
```

{"path":"docs/phase-1-exit-checklist.md","content":"# Phase 1 Exit Checklist

## Purpose

This checklist defines what evidence must exist before Phase 1 can be considered complete.

Phase 1 does not mean “all future plans are complete.” It means the institutional-memory foundation has been established in a reviewable, traceable, and constitutionally consistent manner.

## Minimum completion criteria

### Institutional-memory model
- [ ] The repository defines the categories CANONICAL, WORKING, RESEARCH, PROJECT, and ARCHIVED
- [ ] The distinction between classification and epistemic status is documented
- [ ] The difference between evidence, inference, hypothesis, proposal, and decision is documented
- [ ] The record lifecycle includes draft, review, approval, supersession, and archival states
- [ ] The model explicitly states that these are conceptual record types and not proof of automated workflow infrastructure

### Record templates
- [ ] Research and evidence record template exists and is usable
- [ ] Decision record template exists and is usable
- [ ] Source and provenance requirements are documented
- [ ] Action and outcome tracking is documented
- [ ] Each template distinguishes source provenance, interpretation, uncertainty, and approval state

### Migration and preservation
- [ ] Existing canonical documents are accounted for in a migration register
- [ ] Existing materials have clear classification or are explicitly pending review
- [ ] No duplicate source of authority is created without documentation
- [ ] Owner or maintainer review is recorded for any moved or renamed material
- [ ] The migration register distinguishes current evidence from proposed classification

### Governance and ownership
- [ ] CODEOWNERS remains the governing authority for ownership
- [ ] Review process is clear
- [ ] Approval requirements are documented
- [ ] Ownership responsibilities are explicit
- [ ] Unapproved or draft records are clearly marked
- [ ] No required approval field is applied to a proposed or rejected decision unless that status explicitly requires it

### Traceability
- [ ] Every research record can be traced to sources
- [ ] Every decision can be traced to evidence or rationale
- [ ] Every action links to a decision and outcome when known
- [ ] Historical records are preserved rather than overwritten

### Risks and uncertainty
- [ ] Material risks are recorded
- [ ] Unknowns are explicitly listed
- [ ] Deferred work is clearly marked as deferred, not approved
- [ ] Assumptions are distinguished from evidence

### Review and final human signoff
- [ ] A human reviewer has checked the migration register
- [ ] The final repository state has been reviewed
- [ ] Remaining gaps and approval requirements are documented
- [ ] The decision to complete Phase 1 is explicitly recorded
- [ ] The exit checklist is based on evidence and not just documentation creation

## Evidence required for completion

The Phase 1 package is not complete unless the repository contains:
- traceable institutional-memory definitions
- usable templates
- a migration register
- a documented review process
- a human-readable list of unresolved issues
- no contradiction with the Constitution
- evidence that the package was reviewed and not merely added

## Explicit non-approval

This checklist does not automatically approve:
- application implementation
- technology stack decisions
- deployment or cloud decisions
- product release
- complex AI or automation features

Those remain separate approval gates.
```
}]} , 