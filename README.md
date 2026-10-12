# CELL — Cellular Evolutionary Language

**Status:** Concept / early specification (`CELL-0.1`)

CELL is an open-source research project exploring a programming language and runtime in which functions are autonomous computational units with:

- executable code;
- a structured, evolvable representation called **DNA**;
- function-associated **memory**;
- a lightweight **NeuralCore** for adaptive decisions;
- the ability to migrate between peer-to-peer runtime nodes.

The concept originated as an idea in the early 2000s, inspired in part by Java. This repository aims to preserve that original vision while developing a testable modern specification and prototype.

> CELL is currently a concept and specification project. The syntax and runtime described here are proposals, not a claim that a working implementation already exists.

## Core idea

A CELL function's **DNA is the executable code itself**. The runtime can replicate DNA into operational instances, execute them locally or migrate them to compatible peer nodes, and periodically evaluate bounded mutations or recombinations against a fitness objective.

## Project principles

1. **Function as a Cell** — code, DNA, memory, and adaptive component are associated with a function.
2. **Peer-to-peer execution** — compatible nodes can exchange work without requiring every execution to pass through one central server.
3. **Mobility** — a function can migrate with an explicit execution state and a declared transfer policy.
4. **Controlled evolution** — candidate variants are evaluated against tests, constraints, and performance objectives before promotion.
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

The example is illustrative and is not yet a parser-supported language definition.

## Repository layout

```text
.
├── README.md
├── LICENSE
├── CONTRIBUTING.md
├── CODE_OF_CONDUCT.md
├── docs/
│   ├── vision.md
│   ├── technical-specification.md
│   ├── roadmap.md
│   └── glossary.md
├── examples/
│   └── hello-cell.cell
├── src/
└── tests/
```

## Roadmap

- [x] Record the foundational concept.
- [x] Draft the first technical specification.
- [ ] Confirm the original design goals and terminology.
- [ ] Define the minimal language grammar.
- [ ] Build a local interpreter for ordinary CELL functions.
- [ ] Add explicit memory and versioned DNA representations.
- [ ] Prototype controlled evolution in a single process.
- [ ] Implement a two-node migration proof of concept.
- [ ] Add authentication, sandboxing, resource limits, and migration tests.

## Contributing

Early contributions should focus on discussion and specification before implementation. Please open an issue for proposed language features or architecture changes and explain the problem they solve.

## License

See [LICENSE](LICENSE).
