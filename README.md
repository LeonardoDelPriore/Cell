# CELL — Cellular Evolutionary Language

**Status:** Concept. No interpreter or tests exist. The draft specification is labeled `CELL-0.2` and is not a transcription of the original papers.

CELL is a research project exploring a programming language and runtime in which the unit of computation is a cell:

- executable code;
- a structured, evolvable representation called **DNA**;
- memory, with dream as the original name for associative memory;
- a neural network inside dream, which does not assign fitness and does not place work;
- liquidity: any cell computation can live on any connected machine able to run it, placed for resilience rather than speed.

The concept originated as an earlier design, preserved in photographs under `docs/Documentazione originale/` and in the author's later recollection. One sheet, THE THREAD CELL, refers to Visual Basic and ActiveX; the written date reads 16/10/1998 and the last digit is uncertain. Diplomatic transcriptions sit beside the photographs in `docs/Documentazione originale/trascrizioni/`. This repository aims to keep that record separate from a testable modern specification and prototype.

> CELL is currently a concept and specification project. The syntax and runtime described here are proposals, not a claim that a working implementation already exists.

## Core idea

A cell's **DNA is the executable code itself**. The runtime can replicate DNA into operational instances and let them live on any connected machine able to run them. Placement seeks a resilience equilibrium, not the fastest machine. A cell answers first from its genotype and later from dream. Three cells that return the same output for the same input define the accepted answer; cells that disagree are eliminated. A stimolo is an input. The names tissue, organ, and individual are a view for a human reader. CELL is not limited to that nesting: separate cells may live in higher groups, and the system duplicates the whole. A program starts with one cell. The more input it receives, the faster the environment reproduces it; if the environment fills, the cell is pushed to seek other places to live. More input on an area, more the network develops there. A human-only editor in the CVM designs the language and navigates the network in three dimensions, showing resilience, functions, and the dream of a selected area. The programmer and a specialized AI may both edit cell opcode. The environment gives fitness priority to the heavier tissues. A weight there is an opcode function that starts defined and can change, not a constant number. On 17 November 2026 the measure of that judgment was stated. The kernel tests a sample by level against the dream accumulated there. A system that is just starting hardly has significant mutations. When dream is sufficient, groups that win 90% or 100% of the results can be sent to test and mutated again. True fitness is less time at equal results, and the same outputs for the same input. Validation stays on the cells, so a tissue still works when each cell lives on its own machine. Bounded mutations stay a separate proposal.

## Project principles

1. **The cell is the unit** — code, DNA, and memory belong to a cell. The early recollection spoke of functions. The papers and the working definition use the cell.
2. **Peer-to-peer execution** — compatible nodes can exchange work without requiring every execution to pass through one central server.
3. **Liquidity** — a computation can live on any connected machine able to run it. The network weighs itself and moves work toward resilience, not speed.
4. **Controlled evolution** — a mutation under test is kept when it returns the same outputs for the same input and, among those results, takes less time. Placement across machines seeks resilience.
5. **Inspectable behavior** — versions, migrations, and evolution events should be traceable and reproducible where possible.
6. **Safety first** — remote code is untrusted by default; capabilities and resource limits must be enforced by the runtime.

## Example (illustrative syntax only)

```cell
cell calculate {
    dna {
        representation = "portable-ir"
        mutation_policy = "bounded"
        recombination = "validated"
    }

    memory {
        scope = "cell"
        persistence = "checkpointed"
    }

    neural {
        model = "small"
        purpose = "strategy-selection"
    }

    fn run(input) {
        return optimize(input)
    }

    evolution {
        trigger = "every_n_cycles"
        promote = "only_if_valid_and_fitter"
    }

    migrate {
        policy = "runtime-selected"
    }
}
```

The example is illustrative and is not yet a parser-supported language definition. The `neural` block and the promotion line are an earlier sketch: the decision of 15 November 2026 keeps the neural network inside dream, out of fitness and out of placement.

## Repository layout

```text
.
├── README.md
├── LICENSE
├── CONTRIBUTING.md
├── CODE_OF_CONDUCT.md
├── docs!vision.md
├── docs!technical-specification.md
├── docs!roadmap.md
├── docs!glossary.md
├── examples!hello-cell.cell
├── assets/
│   └── logo.svg
└── docs/
    └── Documentazione originale/    49 photographs of the original papers
        └── trascrizioni/            one transcription per photograph, each opening with the photo
```

There is no `src/` tree and no `tests/` tree. The specification files are in the repository root; their names contain `!`.

## Roadmap

- [x] Record the author's later recollection and a first technical draft.
- [x] Photograph the original papers.
- [x] Transcribe the photographed papers beside the original photos.
- [ ] Confirm uncertain readings and which names belong to the papers rather than to CELL-0.2.
- [ ] Define the minimal language grammar.
- [ ] Build a local interpreter for ordinary CELL functions.
- [ ] Add explicit memory and versioned DNA representations.
- [ ] Prototype controlled evolution in a single process.
- [ ] Implement a two-node migration proof of concept.
- [ ] Add authentication, sandboxing, resource limits, and migration tests.

## Contributing

Early contributions should focus on discussion and specification before implementation. Please open an issue for proposed language features or architecture changes and explain the problem they solve.

## Stewardship

Leonardo Del Priore is the founder. Uma Innovation develops the project and provides its economic support. The only official line of CELL is the one they publish.

## License

CELL is free to use, run, and study under the [CELL Use License 1.0](LICENSE). The license reserves copyright to Leonardo Del Priore and Uma Innovation. It does not allow a public fork, a redistributed modified version, or any copy presented as official. It is not an open-source license.
