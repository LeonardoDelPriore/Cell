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

The sections above record the author's current recollection. They are not a transcription of the papers in `docs/Documentazione originale/`. The diplomatic transcriptions, each opened by its photograph, are in `docs/Documentazione originale/trascrizioni/`. The photographs remain the source: uncertain words stay in brackets and are not corrected. New implementation decisions should be labelled as proposals rather than silently presented as historical features.

## What the papers show

`docs/Documentazione originale/` contains 49 photographs taken on 13 October 2026 of an older paper archive. Two layers are visible. Neither layer uses the words DNA, NeuralCore, fitness function, mitochondria, or checkpoint migration.

### Printed manual

A typed manual, "Regole sullo sviluppo del linguaggio Cell", is signed FraAgo and addressed to Leo. It defines a cellular paradigm in which every variable is a constant function, compared there to Visual Basic `Property Set` / `Property Let`. The runtime is the CVM (Cell Virtual Machine): an opcode interpreter, a meta-opcode interpreter, an anomaly manager, a thread interpreter, and a coordinator. A cell is declared with `New Dynamic Cell` and `Begin Executable Code` / `End Executable Code`. Mitosis creates a cell with the same executable code as its mother. Reuse is single containment, not multiple inheritance. Source is split into `.CELL` (references), `.CEX` (opcode), and `.CBK` (backup). The manual says the biological impression must not be read as an entity with its own intelligence: the programmer still defines the behavior.

### Handwritten machine notes

One sheet is titled "THE THREAD CELL" and names a LEOSOFT project about ActiveX controls for new Visual Basic interfaces. The date on that sheet reads 16/10/1998; the last digit is small enough that an earlier reading saw 1999. The year is not settled. The same archive describes CELL'S MACHINE: a `VITA` process, `ADD` / `KILL` / `CLONE` process, a kernel, input, output, and a dream area. Dream is a dynamic memory used to search and test associations in the background. Streams are treated as the data container. A dynamic opcode is removed after it runs; a static opcode remains. Cells may clone work onto other machines when a network exists. One hello-world sheet labels executable code as genotipo and mentions `MODE LAN` and `PROTO INTER`. Another sheet sketches a later language still to be built. The word written on it is PROLOGATTA, above a linker, a virtual motor, and execution. That sketch is a proposal on the sheet, not the language defined by the printed manual, and it is not yet evidence that the control layer is Prolog.

CELL-0.2 maps later names onto some of these mechanisms. The mapping stays a proposal until Leonardo confirms it. Genotipo is the only original word close to what the recollection calls DNA. Dream, evaluative memory, and the decision table on the THE THREAD CELL sheet are the nearest originals to NeuralCore and to a fitness loop. Virtual residence and clone-across-the-network are the nearest originals to migration.

## Working definition (proposal, 14 November 2026)

This reading comes from the transcriptions and from the later recollection. It is not a new historical fact. On 15 November 2026 Leonardo confirmed the intent in the next section. The reading of the papers below stays a reading.

**What CELL is, on the papers.** A language whose unit is the cell, not the class and not the isolated function. A cell holds executable code — the manual's executable code, called genotipo on one sheet — communicates through explicit channels, and is run by a machine: the CVM in the printed manual, CELL'S MACHINE in the notes.

The manual's cell is not an intelligent being. The programmer writes the behavior. A variable is a constant function. Copying is mitosis: the daughter carries the mother's executable code. Reuse is containment, not inheritance. A cell's text is split into references (`.CELL`), opcode (`.CEX`), and backup (`.CBK`).

The notes describe a machine the manual does not name in the same words. A cell has a kernel, input, output, and a stream as its data container. Dream is a dynamic memory that stores and tests input/output associations in the background, and can answer from that memory instead of recomputing. `VITA` is the process that stays alive and manages the others. A dynamic opcode is removed after it runs; a static opcode remains. Cells can clone work onto other machines. One sheet calls the result virtual residence: a program can live on more than one machine without a guarantee of which machines, in a given interval.

**What it wants to be.** On the papers, programs that are not tied to one machine, that answer a known stimulus from dream instead of recomputing it, and that can drop instructions after they have run. The later recollection adds recombination of that code, a test against an objective, a neural component, and migration of a running instance with a checkpoint. The papers do not contain those four mechanisms. The author decision of 15 November 2026 says what the objective and the network are.

**How the intelligence tension is split.** The manual says the cell has no intelligence of its own. The notes say cells evaluate requests, learn stimuli, and catalog them. Both stay. They apply to different layers, as decided below.

## Author decisions, 15 November 2026

Leonardo states these as the author of the intuition, about thirty years after the papers. They are current intent. They are not sentences found on the sheets.

- He is the author of the intuition. Realizing it should also be able to carry an evolution of the assistant that helps build it, by letting that assistant's computations live as cells. This does not identify FraAgo, and it does not make the assistant a cell that writes its own behavior.
- The system is a distributed network. Adaptation is not only a neural network. A second mechanism adapts the network to the environment.
- That mechanism is liquidity. Any computation written in Cell can live on any connected machine able to compute it.
- The network weighs itself and distributes itself. The equilibrium it seeks is resilience, not speed.

The split this gives:

| Layer | What it decides | Source |
| --- | --- | --- |
| What a cell does | The author writes the behavior. A cell is not an autonomous mind. | Printed manual, kept |
| What a cell remembers | Dream stores and tests associations, and can answer without recomputing. On one sheet a dream that loses a speed comparison gives way. That local comparison stays a local rule. Later the same day Leonardo named this area cytoplasm and set the maturation order below. | Handwritten notes, kept, then extended |
| Where a computation lives | Liquidity. The network weighs itself and moves work toward resilience, even when another machine would be faster. | Decision of 15 November 2026 |
| What a neural component is | It lives inside dream at each level, together with memory and response time. It does not assign fitness and it does not place work. | Decision of 15 November 2026, refined later the same day |

Checkpoint, fencing, and a concrete weight function remain implementation proposals. The decision fixes the goal of placement, not the protocol.

### Maturation and agreement, later on 15 November 2026

Leonardo adds this direction. It is still current intent, not a sentence from the sheets.

Dream, after his later study, is the cytoplasm of the cell. It holds the cell's memory, what the cell produces, and the part of the cell that builds itself. That produces a cell whose first answers are mechanical and come from the opcode, which he also calls genotipo. Later answers to the same work come from dream and become faster. The path ends in a subdivision. The manual's name for a split that carries the mother's executable code is mitosi. He used suddivisione. The two words are not yet declared to be the same operation.

The CVM is the environment that compares groups of identical cells and can decide which group performs better. The concrete test he stated is agreement, not speed. If three cells answer the same stimuli with the same output, cells that answer differently are treated as mutations that went wrong and are eliminated. On 17 November 2026 he defined a stimolo as an input, so that comparison is on the same input. He compared the check among cells to a small blockchain. The rule he stated is a quorum on identical input and output. It does not, by itself, require a ledger, a token, or a chain of blocks. He gave three agreeing cells as the case. He did not say what happens when only two agree.

The same day he extends dream beyond one cell. Cells form a tissue, and tissues form a macro-network of macro-groups. Dream then also runs from group to group, including from macro-group to macro-group, so the tissue stays coherent and fitness stays under control at those scales. The handwritten notes already make a public dream visible to the processes of one group. The manual already names a cellular group, with the extension `.CELG`. Tessuto and macrogruppo are his words today. They are not yet declared identical to cellular group and to a group of groups.

This sits beside liquidity. Placement of work across machines still seeks resilience, not speed. Speed belongs to the maturation of one cell: genotype first, then dream. The CVM's comparison of groups uses agreement of outputs. Fitness control at tissue and macro-group scale is the new scope of dream. The weight used for placement is still undefined.

### Levels, later still on 15 November 2026

Tissues can contain tissues. The levels interconnect. Each level has its own dream. A dream, at whatever level, is the whole of three things: the neural network built at that level, the memory, and the response time.

The union of many tissue functions and many inter-tissue functions is an organ. The set of many organs is an individual. Inter-tissue is his name for the connection between tissues. As further levels are abstracted, each one still has a dream attached. He does not declare the individual to be the last level. The papers do not use organ, inter-tissue, or individual.

Fitness stays with the environment. The environment gives priority to the tissue, or to the set of tissues, that has the greater weight, as in a pyramid. That comparison is not the same statement as the resilience weight of placement across machines.

The comparison he gives for these weights is a neural network that starts with defined weights and can change them. A weight is not a constant. It is an opcode function. The printed manual says that a variable in Cell is a constant function, like Visual Basic `Property Set` and `Property Let`. That sentence stays on the papers. The weight decided today is a different object: executable opcode, initially defined, and able to change because of the nature of the network that holds it.

He then says that which function ranks above another is not a decision the authors make. It is a consequence. The kernel of the cell is a laboratory: a mutation can be introduced there. If the mutant responds better than the previous copy, it wins. "Responds better" belongs to the global function, not to a local score the authors write. The win is a slow emergence of that function. The placement weight across machines stays a separate statement: work moves toward resilience, not speed. It is not this ranking.

The agreement he compared to a blockchain also applies at tissue level. Conceptually the validation stays on the cells. Cells can move. If they are validated, the tissue still works when its cells live on different machines. His example is one hundred cells on one hundred machines. The tissue does not have to sit on one host.

### Names for a human reader, later on 15 November 2026

The names tissue, inter-tissue, organ, and individual are a view for a human editor of a CELL network. They are a parallel with a human body, so a reader can follow the levels. CELL can do things more complex than an organism on Earth. Nothing in the vision forbids separate cells living inside higher groups. The names do not force a biological nesting.

That freedom leads CELL to duplicate the whole, not a fragment. The classic first problem he names is a program that starts with one cell, a cell that knows how to count. He mentions other cells in the same problem and does not describe them.

The CVM also has an editor, and the editor is for the human only. There the human designs the Cell language and sees the schemas of the network: where it is resilient, and where its functions are. The view is navigable in three dimensions, so the nodes of the space can be imagined. The human may color areas as they wish. Selecting those areas shows the dream and its data. The programmer may act on the opcode of cells. A specialized AI may act on that opcode in the same way. He does not say that this AI is the assistant whose computations live as cells, nor that it may rewrite its own cells. The editor itself stays a human instrument.

The CVM reacts to input. A stimolo is an input, as stated on 17 November 2026. The more input a cell receives for its work, the faster the CVM tends to reproduce it, because the work is needed. If that reproduction saturates the environment, the CVM pushes the cell to seek other places to live. Growth of the network, and of performance, follows the input. More input on an area, more the network develops in that direction. This is the growth rule. It does not replace the earlier statement that placement across machines seeks resilience rather than speed. Saturation is the push to look elsewhere. Resilience remains the stated criterion of where work lives.

### Fitness of a mutation, 17 November 2026

Leonardo states how the kernel keeps the mutation that responds better in the global function. The kernel tests a sample according to the level, in response to the dream accumulated there. A system that is just starting hardly has significant mutations. When the dream is sufficient, it becomes possible to send groups to test and to mutate them again. He names, with "magari", groups that win 90% or 100% of the results.

At equal results, the higher fitness is less time. He calls the true fitness time, or, at equal input, the same outputs. A mutation that changes the output does not win that test. A mutation that returns the same outputs in less time does. The three agreeing cells stated on 15 November stay the case he gave for eliminating a disagreeing answer. The 90% and 100% are the win rates he gave for sending a group back to test and mutation. He did not say that those rates replace the three cells.

What counts as sufficient dream, and which clock measures the time, are unsaid. Dream at each level already includes a response time. He did not say that the fitness clock is that field.

Placement of work across machines stays the resilience equilibrium of 15 November. This fitness is the ranking of a mutation under test.

### Incongruenze ancora aperte, 15 November 2026

These are collisions between decisions already written above, or between those decisions and the papers. Items 1 and 6 were resolved on 17 November 2026. The others stay open.

1. **Resolved on 17 November 2026.** The kernel tests a sample by level against the accumulated dream. A different output loses, because true fitness requires the same outputs for the same input. Among equal results, less time wins. Same outputs are part of that fitness, so a heavier tissue does not outrank a failed agreement. The 90% and 100% rates, and what "sufficient dream" means, are in "Fitness of a mutation".

2. **Input and resilience.** A stimolo is an input. More input makes the network grow in that area. Liquidity places work on the more resilient machine. Nothing says which rule wins when the area that receives the input is not the more resilient place.

3. **One cell, then three.** A program starts with one cell. The stated quorum is three agreeing cells. Nothing says who accepts the output before the third copy exists. Reproduction follows input because the work is needed, so copies can multiply before that check runs. On 17 November 2026 significant mutations wait until dream is sufficient. That does not say who accepts the first output.

4. **Identical.** The CVM compares groups of identical cells. Nothing says whether the word identical means the same genotype or the same output. The test of 17 November 2026 decides by outputs and by time, so a mutant can differ in opcode and still enter that test.

5. **What a copy carries.** Mitosis, in the manual, gives the daughter the mother's executable code. The same day's decision says CELL duplicates the whole, and cytoplasm holds memory and products. Nothing says whether a stimulated copy inherits the dream or only the opcode. An inherited dream continues maturation. A code-only copy starts again from mechanical answers.

6. **Resolved on 17 November 2026.** True fitness is time at equal results, and the same outputs at equal input. The multi-factor score still printed in the specification is the earlier draft. The test, by level and on accumulated dream, selects the winner. The measure is stated. The winning opcode is the one the test keeps.

7. **An opcode that disappears, and an opcode that is a weight.** The notes remove a dynamic opcode after it runs and keep a static opcode. A weight is an opcode function that persists and can change. Nothing says which of those a weight is.

8. **A constant function, and a function that changes.** The manual says every variable is a constant function. A weight is an opcode function that changes. The two were kept as different objects. Nothing says whether the language designed in the human editor may contain a changing function, or whether the constant rule still binds every name.

9. **Macro-group and tissues of tissues.** Cells form a tissue, and tissues form a macro-network of macro-groups. Tissues can also contain tissues, and many tissues plus inter-tissues form an organ. Macro-group and tissue-of-tissues are not declared to be the same level.

10. **Three first steps.** The classic first problem is one cell that knows how to count. The nearby-work note proposes one cell, one dream, two machines, and a move toward resilience. The roadmap starts with a local grammar and leaves migration to a later phase. These are not the same first prototype.

A public dream, on the sheets, is visible to the processes of one group. Each level now has its own dream. Who can read a dream above the cell is not said.

## Nearby work, surveyed 15 November 2026

No single system found in this survey is the same stack: a cell with executable code, dream as local associative memory, liquidity onto any connected machine, and a self-weighing equilibrium whose criterion is resilience rather than speed.

Pieces that already exist:

- Liquid Software, Hartman, Manber, Peterson, and Proebsting, University of Arizona, technical report 96-11, June 1996. Code flows from machine to machine across a network. It has no cell, no dream, and no resilience equilibrium.
- Telescript, Aglets, and Obliq move running or shippable code. Their goal is mobility, not a weighed resilience equilibrium.
- Osmotic computing moves microelements across cloud, edge, and devices, often for response time and service constraints. Equilibrium in the computing continuum, including active-inference work published in 2024 and 2025, seeks a predictive balance of a service. Those systems are not a cell language.
- Membrane computing, Gamma, actors, Tierra, and Avida cover the other slices already recorded: membranes, message-passing units, and self-copying instruction sequences.

The part that still looks unoccupied is the stack itself, with resilience rather than speed as the reason a computation moves. That is a reason to build a small proof: one cell, one dream, two machines, a weight, and a move that prefers the more resilient place. It is not a reason to claim the whole field is empty.

## Open questions
- Who is FraAgo, and is the printed manual his text, Leonardo's, or a joint draft?
- Does the THE THREAD CELL sheet read 16/10/1998 or 16/10/1999, and does that date the origin of CELL or only that sheet?
- Is genotipo the same object the recollection calls DNA?
- Is dream the ancestor of memory, of NeuralCore, of the fitness loop, or of more than one of those? On 15 November 2026 Leonardo called dream the cytoplasm: memory, products, and the part that builds the cell. The papers themselves do not use the word cytoplasm.
- Is suddivisione the same operation as mitosi?
- Is tessuto the manual's cellular group, and is a macrogruppo a group of those groups? Organ, inter-tissue, and individual are further author names from the same day, not words from the papers.
- Which fitness signals were part of the original idea? The papers do not define a fitness function. The network objective decided on 15 November 2026 is resilience, not speed. Later the same day, fitness priority among tissues is greater weight, in a pyramid, and a weight is an opcode function that starts defined and can change. On 17 November 2026 the measure of the mutation test was stated: the kernel tests a sample by level against the accumulated dream; significant mutations hardly occur at the start; when dream is sufficient, groups that win 90% or 100% of the results can be sent to test and mutated again; true fitness is less time at equal results, and the same outputs for the same input. What counts as sufficient dream, and which clock measures that time, are unsaid. The placement of work toward resilience stays a separate statement. The local dream rule that compares speed stays local.
- Does migration move only an execution instance, or can the DNA lineage itself move or replicate across peers? The papers describe cloning work onto other machines, not a checkpoint handoff. The 15 November 2026 decision says any Cell computation can live on any connected machine able to run it. Checkpoint remains one proposed way to move a running calculation without losing it.
- What exactly counts as a cycle that triggers mutation?
- Which code units can be recombined?
- Does each operational copy have independent memory, shared lineage memory, or both?
- Can two DNA lineages combine, and under what compatibility rules?
- The collisions still open after 17 November 2026 are listed under "Incongruenze ancora aperte". The mutation-against-quorum collision and the authored-score collision were closed that day. Still open: input against resilience, acceptance before three cells, what "identical" means, what a copy carries, dynamic opcode against a persisting weight, a constant variable against a changing function, macro-group against tissues of tissues, and which demonstration comes first. Who can read a dream above the cell is also unsaid. What counts as sufficient dream, and which clock measures fitness time, are unsaid.
