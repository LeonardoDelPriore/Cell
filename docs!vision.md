# CELL — Vision and origin

## Origin

CELL began as a programming-language idea in the early 2000s, during the author's first year studying computer science. The initial inspiration included Java and the idea of executing work across multiple machines in a peer-to-peer model.

The original intuition was that each function would have three intrinsic elements:

1. a small neural network;
2. its own memory;
3. DNA that is the executable code itself, written in a machine-oriented language that can be recombined and evolve.

The author further envisioned a replication mechanism analogous to mitochondria: DNA can be duplicated into operational copies when needed for execution. At defined intervals or cycles, mutations can be proposed and evaluated through performance tests and a fitness process informed by neural components, memory, and other signals.

Functions should also be able to migrate between machines during execution.

These biological analogies describe the intended architecture; they do not imply literal biological behavior.

## Core principles

- DNA is the code, not only metadata describing code.
- Code should be machine-oriented and structured for recombination, even if not optimized for human readability.
- DNA can be replicated into operational instances when work is needed.
- Neural adaptation and memory can inform candidate generation and evaluation.
- Mutations are tested and compared against a declared fitness objective.
- Accepted versions retain lineage and a path to rollback.
- Execution instances can migrate across compatible peer nodes.

## Preserve the original idea

This document records the author's current recollection. New implementation decisions should be labelled as proposals rather than silently presented as historical features.

## Open questions

- What exactly counts as a cycle that triggers mutation?
- Which code units can be recombined?
- Does each operational copy have independent memory, shared lineage memory, or both?
- Can two DNA lineages combine, and under what compatibility rules?
- Which fitness signals were part of the original idea?
- Does migration move only an execution instance, or can the DNA lineage itself move or replicate across peers?
