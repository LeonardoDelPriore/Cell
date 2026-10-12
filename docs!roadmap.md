# CELL Roadmap

## Phase 0 — Preserve the idea
- Capture the author's recollection of the early-2000s design.
- Mark original concepts separately from new engineering decisions.
- Publish the vision and foundational specification.

## Phase 1 — Local language prototype
- Select an implementation language.
- Define a minimal grammar and parser.
- Execute a basic cell locally.
- Add automated tests and a small example suite.

## Phase 2 — Memory and DNA
- Define a versioned DNA schema.
- Add explicit memory scopes and checkpoint serialization.
- Add deterministic test fixtures and rollback.

## Phase 3 — Controlled evolution
- Implement a small set of allowed transformations.
- Evaluate candidates against correctness tests and an objective function.
- Record lineage, metrics, and promotion decisions.

## Phase 4 — Two-node migration
- Define a minimal peer protocol.
- Authenticate peers and validate transferred packages.
- Implement checkpoint, transfer, handoff, and resume.
- Test node loss, timeout, duplicate delivery, and incompatible runtimes.

## Phase 5 — Research and community
- Benchmark against a non-evolving baseline.
- Document limitations and threat models.
- Invite contributors to review the language and runtime specifications.

Each phase should end with a runnable demonstration and tests before the next layer is added.
