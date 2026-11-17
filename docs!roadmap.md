# CELL Roadmap

## Phase 0 — Preserve the idea
- Capture the author's recollection of the early design.
- Keep the photographed papers in `docs/Documentazione originale/` separate from CELL-0.2 proposals. The recollection, the printed manual, and the handwritten notes do not use the same names.
- Transcribe those papers into the repository. A diplomatic transcription of all 49 photographs is in `docs/Documentazione originale/trascrizioni/`, each file opening with its photograph. Integrating that text into the new notes, and settling uncertain readings, is still open.
- Mark original concepts separately from new engineering decisions.
- Draft a working definition that keeps the papers and the later recollection apart. Drafted on 14 November 2026 in `docs!vision.md`. On 15 November 2026 Leonardo decided the split: a cell's behavior stays written, dream stays local memory, and the network places work by liquidity toward resilience rather than speed. Later the same day he called dream the cytoplasm, set maturation from genotype answers to faster dream answers and then a subdivision, and set a quorum: three agreeing outputs eliminate disagreeing cells. He then scaled dream across groups. Later still, tissues nest, each level has its own dream, and each dream is the built neural network, the memory, and the response time. Many tissues and inter-tissues form an organ. Many organs form an individual. Every further abstraction still has a dream. Fitness stays with the environment and prefers heavier tissues, in a pyramid. A weight is an opcode function, initially defined and able to change, not a constant. Which function ranks above another is not an authorial choice of a named opcode: the kernel can mutate, and a mutant wins only if it responds better inside the global function. On 17 November 2026 he stated that test. The kernel tests a sample by level against the accumulated dream. Significant mutations hardly occur at the start. When dream is sufficient, groups that win 90% or 100% of the results can be sent to test and mutated again. True fitness is less time at equal results, and the same outputs for the same input. Validation stays on the cells, so a tissue can span one machine per cell. The biological names are a human reading aid. A program starts with one cell; the classic first problem he names is a cell that knows how to count. Input makes the CVM reproduce it faster, and saturation pushes it to seek other places. On 17 November 2026 a stimolo was defined as an input. The CVM also has a human-only editor: three-dimensional navigation of resilience and functions, optional coloring, and a view of the dream of a selected area. The programmer and a specialized AI may both edit cell opcode. The editor stays human. FraAgo's identity, whether two agreeing cells are enough, and whether tessuto is the old cellular group remain open. So do the collisions still open in `docs!vision.md` under "Incongruenze ancora aperte": input against resilience, acceptance before three cells, what "identical" means, what a copy carries, dynamic opcode against a persisting weight, a constant variable against a changing function, macro-group against tissues of tissues, and which demonstration comes first. What counts as sufficient dream, and which clock measures fitness time, are unsaid.
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
