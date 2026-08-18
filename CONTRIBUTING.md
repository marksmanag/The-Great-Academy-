# Contributing to The Great Academy

## Welcome

Thank you for your interest in contributing to The Great Academy. This document explains how to participate, submit changes, and engage with our community.

## Core Principles

Before contributing, please understand:

1. **The Great Academy is teachable** — We learn from evidence and adapt
2. **No fabrication** — All claims are traceable to sources
3. **Clarity of authority** — We distinguish canonical, working, research, project, and archived material
4. **Governance matters** — Changes follow a deliberate process
5. **Long-term thinking** — We design for systems that outlive their creators

Read [CONSTITUTION.md](./CONSTITUTION.md) to understand our foundational principles.

## How to Contribute

### 1. Start with an Issue

Before submitting code, documentation, or significant changes:

1. **Check existing issues** — Is this already being discussed?
2. **Open a new issue** — Describe what you want to contribute
3. **Provide context** — Explain the problem, your proposed solution, and why it matters
4. **Include evidence** — Link to research, prior art, or reference material
5. **Wait for feedback** — Discuss with maintainers before investing significant effort

### 2. Fork and Branch

```bash
# Clone the repository
git clone https://github.com/marksmanag/The-Great-Academy-.git
cd The-Great-Academy-

# Create a feature branch from main
git checkout -b feature/your-contribution-name
```

**Branch naming:**
- `feature/` — New features or documentation
- `research/` — Research or experiments
- `fix/` — Bug fixes
- `docs/` — Documentation improvements

### 3. Make Your Changes

**For documentation:**

- Use clear, concise language
- Cite your sources
- Distinguish evidence from inference
- Follow the repository structure
- Include context and examples

**For code or architecture:**

- Include an Architecture Decision Record (ADR) explaining the decision
- Document your reasoning
- Include tests or evidence of correctness
- Consider maintainability and teachability

**For research:**

- Place in `research/` directory
- Cite all sources
- Distinguish evidence, inference, and hypothesis
- Explain methodology
- Make findings reproducible

### 4. Commit Your Work

**Commit messages should:**

- Use clear, descriptive language
- Explain *why* not just *what*
- Reference related issues: `Fixes #123` or `Relates to #456`
- Keep commits atomic (one logical change per commit)

**Example:**
```
Add ADR for knowledge architecture decision

Document the decision to use [approach] for knowledge representation.
Based on research in research/knowledge-systems/.

Reasoning:
- Evidence from external research supports this approach
- Aligns with principle of teachability
- Enables future expansion

Fixes #42
```

### 5. Submit a Pull Request

**When opening a pull request:**

1. **Title** — Clear, descriptive, references issue
2. **Description** — Explain what and why
3. **Evidence** — Link to research, reasoning, or prior discussion
4. **Impact** — What changes, what could break?
5. **Testing** — How was this validated?

**Template:**
```markdown
## Description

[What does this change do?]

## Related Issue

Fixes #123

## Type of Change

- [ ] Documentation
- [ ] Research
- [ ] Architecture or governance
- [ ] New principle or amendment
- [ ] Project implementation
- [ ] Other: ___

## Evidence & Reasoning

[Why is this change needed? What evidence supports it?]

[Link to research, discussion, or prior art]

## Impact

- [ ] This changes a canonical principle
- [ ] This affects how projects implement Academy principles
- [ ] This is working/experimental material
- [ ] This is research or evidence

## Checklist

- [ ] My changes are consistent with The Great Academy constitution
- [ ] I have cited my sources
- [ ] I have clearly distinguished evidence, inference, and hypothesis
- [ ] I have considered long-term maintainability
- [ ] I have explained why this change matters
```

### 6. Review Process

**All pull requests:**

1. Are reviewed by CODEOWNERS
2. Must pass any automated checks
3. Require at least one approval
4. Cannot merge without approval
5. Require all feedback to be addressed

**CODEOWNERS may:**

- Request clarification or changes
- Ask for additional evidence or research
- Suggest alternatives
- Require discussion in an issue first
- Request revision before merging

**Reviewers consider:**

- Consistency with Great Academy principles
- Quality of evidence and reasoning
- Impact on canonical material vs. working material
- Long-term maintainability
- Alignment with governance rules

## Repository Structure

When contributing, place your work in the appropriate directory:

```
constitution/    — Canonical constitutional documents
academy/         — Learning, methodology, governance
architecture/    — System design, knowledge structures, AI methodology
research/        — Evidence, experiments, references, decision records
projects/        — Implementations applying Academy principles
docs/            — Supporting documentation
```

**Each directory has a README.md explaining its purpose.**

## What We're Looking For

### Canonical Contributions

Changes to constitutional principles or core architecture need:

1. Strong evidence and reasoning
2. Community discussion and consensus
3. Clear documentation of the decision
4. Consideration of long-term impact
5. Amendment process (see CONSTITUTION.md)

### Working/Research Contributions

Experimental material, research, and evaluation needs:

1. Clear labeling as working/research/experimental
2. Documentation of methodology
3. Sources and references
4. Distinction between evidence and speculation
5. Path to validation or integration

### Project Contributions

Implementations and applications need:

1. Clear connection to Academy principles
2. Documentation of how principles are applied
3. Evidence of correctness or quality
4. Maintainability considerations
5. Governance structure

## Code of Conduct

Contributors must follow our [CODE_OF_CONDUCT.md](./CODE_OF_CONDUCT.md).

Expected behaviors:
- Respect and professionalism
- Evidence-based discussion
- Openness to correction
- Focus on ideas, not individuals
- Assume good intent

## Questions?

1. **Check existing issues** — Your question may already be answered
2. **Open an issue** — Ask questions there
3. **Review CONSTITUTION.md** — Understand our principles
4. **Read ROADMAP.md** — See where we're headed

## Recognition

Contributors to The Great Academy are recognized through:

- Credit in commit history
- CODEOWNERS listing
- Repository README (for significant contributions)
- Acknowledgment in relevant documentation

## Thank You

Thank you for helping build The Great Academy. We're grateful for your time, thought, and commitment to creating something that outlives us.
