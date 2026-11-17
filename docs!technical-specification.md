# CELL-0.2 — Foundational Technical Specification

**Status:** Draft for discussion. This document records the author's clarified concept and separates it from implementation choices still to be validated. It is not a transcription of `docs/Documentazione originale/`. The transcriptions are in `docs/Documentazione originale/trascrizioni/`.

## 0. Relation to the original papers

The names below are CELL-0.2 proposals. The papers use other words, listed in `docs!glossary.md` and `docs!vision.md`.

- **DNA.** The papers do not use this word. One sheet calls the executable code genotipo. Section 3 keeps the CELL-0.2 definition: DNA is the code.
- **Replication.** The printed manual calls the copy operation mitosi. The notes say `CLONE`. The mitochondria analogy belongs to the later recollection, not to those pages.
- **NeuralCore.** The papers do not describe a neural component. The nearest mechanisms are dream, an area labelled intelligence that checks a calculation, evaluative memory, and the decision table on the THE THREAD CELL sheet. That sheet is dated 16/10/1998, with the last digit uncertain. The printed manual says a cell is not an entity with its own intelligence. On 15 November 2026 Leonardo placed the neural network inside dream, at each level. Its weights are opcode functions, not constants. It does not place work and it does not assign fitness.
- **Fitness.** Dream can test code in the background. The papers do not define a fitness function or a promotion policy. On 15 November 2026 the declared objective of placement is resilience, not speed. A local dream may still compare its answer with a recomputation.
- **Migration.** The notes describe virtual residence on unequal machines and cloning work across a network. They do not describe checkpoint, fencing, and resume of one running instance. On 15 November 2026 the goal was named liquidity: any Cell computation can live on any connected machine able to run it, and the network weighs itself toward resilience. Section 9 remains a proposal for how a running calculation moves.

## 1. Core definition

The working definition of what the papers describe, and of what remains a proposal, is in `docs!vision.md` under "Working definition". This section states the CELL-0.2 proposal that the later recollection adds on top of those papers.

CELL is a programming language and runtime for computational units whose **DNA is the executable code itself**. DNA is represented in a language designed for machine-oriented execution and recombination; it need not be optimized for direct human authoring. The printed manual, kept on 15 November 2026, says a cell is not an entity with its own intelligence. The author writes the behavior.

A CELL can preserve its DNA, duplicate it into operational copies when work is needed, execute those copies locally or on compatible peer nodes, and generate candidate mutations. At defined intervals or evaluation triggers, candidate variants are tested. Placement of a running computation follows liquidity: the network weighs itself and prefers the more resilient machine, not the faster one. The neural network inside dream does not place that work and does not assign fitness.

The biological metaphors are design inspirations, not claims that software cells behave exactly like biological cells.

## 2. Core components

Each logical CELL includes:

- **DNA:** the executable program representation, including its compositional structure and permitted recombination points.
- **Replication mechanism:** creates an operational copy of DNA when execution capacity is required.
- **Execution instance:** a running copy with its own runtime state and declared access to memory and resources.
- **Memory:** records selected experience, outcomes, context, and prior fitness measurements.
- **NeuralCore:** the neural network inside dream, together with memory and response time. It does not assign fitness and does not place work. An earlier draft of this list said it may help select strategies, propose changes, or estimate outcomes. That role conflicts with the decision of 15 November 2026.
- **Evolution controller:** proposes mutations or recombinations, schedules evaluations, and manages candidate promotion. Whether this authored cycle remains beside the kernel laboratory is open. See section 5.
- **Fitness evaluator:** the environment's priority among tissues. An earlier draft calculated a declared score from correctness, performance, resource use, robustness, and task-specific objectives. The later decision says the authors do not choose the ranking of opcode functions. Whether a declared score remains as a correctness gate is open.
- **Runtime / peer layer:** schedules instances and can migrate a copy and its supported state between compatible nodes.

The collisions that remain between this draft and the decisions of 15 November 2026 are listed in `docs!vision.md` under "Incongruenze ancora aperte".

## 3. DNA representation

DNA is code, not merely metadata describing code. The implementation should define a machine-oriented representation that is executable by the CELL runtime and structured enough to support safe recombination.

Candidate representation families include a typed intermediate representation, a bytecode with explicit instruction boundaries, or a domain-specific instruction graph. The project should not commit to one until a small prototype compares execution, validation, portability, and mutation complexity.

The DNA format should support:
- stable identifiers and version lineage;
- explicit boundaries for recombination and mutation;
- declared inputs, outputs, effects, and resource limits;
- validation before execution;
- deterministic serialization where practical;
- compatibility/version information.

A fuzzy or approximate logic style can be supported where useful, but should not make the instruction format ambiguous. Fuzzy values and operators need explicit semantics, precision rules, and tests.

## 4. Replication and execution

The conceptual model distinguishes a persistent DNA lineage from disposable or temporary execution instances.

1. The runtime receives a work request.
2. It selects a suitable DNA version.
3. It duplicates or instantiates that DNA into an execution instance.
4. The instance runs within resource and capability limits.
5. Selected outcomes and metrics are recorded in memory.
6. The instance is retained, checkpointed, or discarded according to its lifecycle policy.

Replication does not automatically mean that every copy should mutate independently. The runtime must define which copies are immutable execution snapshots and which are eligible to become evolutionary candidates.

## 5. Evolution cycle

Evolution can be triggered after a configured number of execution cycles, a time interval, sufficient new observations, or a detected performance opportunity.

A proposed cycle is:

1. **Baseline:** identify the current accepted DNA version and its fitness record.
2. **Proposal:** generate one or more candidates through bounded mutation or recombination.
3. **Validation:** reject malformed, unsafe, or incompatible DNA.
4. **Testing:** run correctness, regression, safety, and performance tests in an isolated environment.
5. **Scoring:** calculate fitness using a versioned objective function and representative workloads.
6. **Selection:** promote a candidate only if it meets correctness constraints and the acceptance policy.
7. **Lineage:** record parent version(s), transformations, measurements, and the selection decision.
8. **Rollback:** preserve the ability to restore the prior accepted version.

An earlier draft said NeuralCore and memory can influence which candidates are proposed or which tests are prioritized, without bypassing validation or hard correctness and safety constraints. That influence conflicts with the later decision that the neural network stays out of fitness. Whether any of this authored cycle remains is one of the open collisions.

Later on 15 November 2026 Leonardo set a maturation order and an agreement test. A cell answers first from its opcode, also called genotipo. Dream, which he calls cytoplasm, holds memory, products, and the part that builds the cell. Later answers come from dream and become faster. The path ends in a subdivision. The manual's mitosis is the nearest named split; the two are not yet declared identical.

The CVM compares groups of identical cells. In the case he stated, three cells that return the same output for the same input define the accepted answer. On 17 November 2026 a stimolo was defined as an input. Cells that return a different output are treated as bad mutations and are eliminated. He compared the check to a small blockchain. The stated rule is a quorum on identical input and output. It does not require a ledger. He did not say what happens when fewer than three cells agree. This test is a correctness gate. It does not replace the resilience objective of placement.

The same day he scales dream above the cell. Cells form a tissue. Tissues form a macro-network of macro-groups. Dream runs from group to group, and from macro-group to macro-group, so the tissue stays coherent and fitness is controlled at those scales. The notes already have a public dream inside one group. The manual already has a cellular group (`.CELG`). Tissue and macro-group are the author's names for the wider scales. They are not yet declared identical to those older names.

Later the same day the scales nest. Tissues can contain tissues, and the levels interconnect. Each level has its own dream. Each dream is the neural network built at that level, the memory, and the response time. The union of many tissue functions and many inter-tissue functions is an organ. The set of many organs is an individual. Every further abstraction still has a dream attached. The individual is not declared to be the last level. Fitness stays with the environment, which gives priority to the tissue or set of tissues with greater weight, as in a pyramid. A weight is not a constant. It is an opcode function: initially defined, and able to change because of the nature of the network that holds it. The manual's constant function remains the historical rule for a variable. The authors do not choose which opcode function ranks above another. The kernel is a laboratory: a mutation can be introduced, and it wins if it responds better than the previous copy. "Responds better" belongs to the global function and emerges slowly. The agreement compared to a blockchain also applies between tissues. The validation stays on the cells, so a tissue still works when its cells have moved to different machines. His example is one hundred validated cells on one hundred machines.

The biological names are a view for a human editor. CELL is not limited to the nesting of an earthly organism. Separate cells may live inside higher groups, and the system duplicates the whole. A program starts with one cell. The classic first problem he names is a cell that knows how to count. The more input that cell receives, the faster the CVM reproduces it, because the work is needed. If the environment saturates, the CVM pushes it to seek other places to live. More input on an area, more the network, and its performance, develop in that direction. A stimolo is an input. Saturation is the push to look elsewhere. Resilience remains the stated criterion of where work lives.

The CVM includes an editor for the human only. In it the human designs the Cell language and navigates the network in three dimensions, seeing where it is resilient and where its functions are. The human may color areas. A selected area shows the dream and its data. The programmer may edit cell opcode. A specialized AI may edit cell opcode in the same way. He does not identify that AI with the assistant whose computations live as cells, and he does not say it may rewrite its own cells. The editor stays human.

On 17 November 2026 Leonardo stated how that laboratory ranks a mutation. The kernel tests a sample by level, against the dream accumulated at that level. A system at the start hardly has significant mutations. When dream is sufficient, groups that win 90% or 100% of the results can be sent to test and mutated again. He said those rates with "magari". True fitness is less time at equal results, and the same outputs for the same input. A mutation that changes the output loses. The three agreeing cells of 15 November remain the case he gave for a disagreeing answer. Placement toward resilience stays the separate statement of 15 November. What counts as sufficient dream, and which clock measures the time, are unsaid.

## 6. Fitness

On 15 November 2026 Leonardo set the placement objective: equilibrium by resilience. On 17 November 2026 the fitness of a mutation under test is less time at equal results, together with the same outputs for the same input. Agreement of those outputs stays the gate.

Fitness is not a single universal notion of “better.” Two weights stay distinct. The tissue-priority weight is an opcode function. On 17 November 2026 the measure of the mutation test was stated: same outputs for the same input, and less time among equal results. The kernel applies that measure by level, against the dream accumulated there. The formula of the placement weight, the one that seeks resilience, is still undefined.

An earlier draft of a fitness function may consider:
- correctness and invariant satisfaction (hard constraints);
- latency or throughput;
- CPU, memory, network, and energy cost;
- robustness across representative inputs;
- generalization to held-out tests;
- stability and failure rate.

Correctness and safety should normally be gates, not merely small weighted terms that can be traded away for speed. Performance comparisons should use repeatable workloads and account for noise.

## 7. NeuralCore and memory

NeuralCore is the neural network built inside a dream at a given level, together with memory and response time. On 15 November 2026 it was kept out of fitness and out of placement. Fitness stays with the environment. Liquidity decides where work lives. Its weights start defined and can change. Each weight is an opcode function, not a constant. The precise training process and ownership scope remain open.

Memory can hold prior inputs or features, outcomes, fitness history, useful strategies, and lineage references. It must have explicit retention, privacy, synchronization, and migration policies. Raw data should not be copied to a peer merely because the DNA migrates.

## 8. Recombination and fuzzy-oriented code

The original concept calls for code that can be recombined and need not be human-oriented. The specification therefore treats machine readability, composability, and valid recombination as first-class design goals.

“Fuzzy” should be defined precisely during language design. It may mean fuzzy logic operators, approximate decision rules, or tolerance-based evaluation; these are different mechanisms. The prototype should avoid using the word as a substitute for formal semantics.

Recombination must preserve required interfaces and type/effect constraints. Candidate code is never trusted solely because it was derived from a valid parent.

## 9. Peer-to-peer migration

Liquidity, decided on 15 November 2026, is the goal. Any Cell computation can live on any connected machine able to run it. The network weighs itself and moves work toward resilience. A migration package is the proposed means, not the goal. It may include:
- DNA identifier, version, and executable representation;
- required runtime and instruction-set version;
- checkpointed execution state where supported;
- memory references or explicitly permitted state snapshots;
- declared capabilities and resource budgets;
- integrity and provenance metadata.

The destination validates the package and runs it in a sandbox. Ownership and mutable state require a handoff/fencing mechanism so that a failed transfer does not leave two active authoritative instances. Start with checkpoint-and-resume migration; transparent transfer of arbitrary live machine state is out of scope for the first prototype.

## 10. Security and containment

Mutation and remote execution create a large attack surface. CELL should require:
- sandboxed execution;
- explicit capabilities;
- CPU, memory, storage, and network quotas;
- authenticated peer identity and integrity-checked packages;
- validation of DNA and all candidates;
- bounded mutation operators;
- audit logs, cancellation, quarantine, and rollback;
- protection against resource exhaustion and malicious candidate generation.

No automatic network discovery or successful mutation should imply trust.

## 11. Illustrative syntax

The following is only a conceptual sketch; the final language may be machine-oriented and may not use this human-readable syntax. Its `neural` role (`candidate-ranking`) and its latency term belong to the earlier draft. They conflict with the decision that the neural network stays inside dream and out of fitness and placement.

```cell
cell optimizer {
    dna {
        representation = "portable-ir"
        mutation_policy = "bounded"
        recombination = "validated"
    }

    memory {
        scope = "lineage"
        retain = ["fitness", "strategy", "outcome"]
    }

    neural {
        role = "candidate-ranking"
        budget = "small"
    }

    evolution {
        trigger = "every_n_cycles"
        evaluate = ["correctness", "latency", "resource_cost"]
        promote = "only_if_valid_and_fitter"
        rollback = true
    }
}
```

## 12. Minimal proof of concept

The first meaningful prototype should demonstrate:
1. a DNA representation that can be loaded and executed;
2. replication into isolated execution instances;
3. an explicit memory and fitness record;
4. a bounded mutation operator that produces a candidate;
5. test-based candidate evaluation and promotion/rejection;
6. lineage tracking and rollback;
7. later, transfer of a checkpointed instance between two peer nodes.

## 13. Open decisions

- DNA representation: typed IR, bytecode, instruction graph, or another form;
- precise meaning and scope of fuzzy logic;
- mutation and recombination operators;
- definition and scheduling of “cycles”;
- fitness metrics and task-specific objective format;
- whether neural state belongs to the lineage, DNA version, or instance;
- memory retention, privacy, and migration policies;
- runtime implementation language and execution engine;
- peer identity, protocol, and compatibility strategy;
- the open collisions in `docs!vision.md` under "Incongruenze ancora aperte". Closed on 17 November 2026: a better mutation against the quorum, and an authored score against emergence. Still open: input against resilience, acceptance before three cells, what "identical" means, what a copy carries, dynamic opcode against a persisting weight, a constant variable against a changing function, macro-group against tissues of tissues, which demonstration comes first, and who can read a dream above the cell. Also unsaid: what counts as sufficient dream, and which clock measures fitness time.
