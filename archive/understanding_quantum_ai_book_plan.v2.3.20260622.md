# Understanding Quantum AI
## Complete Book Plan, Description, Focus, and Table of Contents (v2.3)

> Version 2.2 of the plan. The original is preserved at
> `archive/understanding_quantum_ai_book_plan.v1.20260616.md`.
> v2 added a mathematical onramp, the parameterized-gate machinery that all of
> quantum machine learning depends on, a stronger intellectual-honesty track
> (dequantization, classical surrogates, the barren-plateau / simulability link),
> error correction, a 2026 hardware reality chapter, complete front and back
> matter, and a version-pinned companion code base.
> v2.1 closed the QML learning-theory and model-class gaps (expressivity and
> generalization, kernel concentration, power-of-data and provable separations,
> BQP; tensor networks, geometric/equivariant QML, quantum transformers, reservoir
> computing, Boltzmann machines, QRAM).
> v2.2 reflects a live 2025-2026 web scout: it adds a Neural Quantum States
> chapter, strengthens the AI-for-quantum chapter with neural QEC decoders
> (AlphaQubit) and LLM circuit-coding, makes the hardware and error-correction
> chapters concrete to 2024-2026 milestones (below-threshold codes, logical-qubit
> demos, qLDPC vs surface codes, magic-state distillation), adds the standard
> honest-benchmarking suite to the advantage chapter, and corrects the tooling
> stack (Qiskit 2.x, PennyLane 0.45 + 2026 API change, CUDA-Q elevated, TFQ noted
> as maintained-but-legacy rather than dead). See section 22 for the full list.

## Working Title

**Understanding Quantum AI: From Qubits to Quantum Machine Learning**

## Recommended Final Title

**Understanding Quantum AI: From Qubits to Quantum Machine Learning**

Clear, broad, academic, and readable. It signals both the beginner-friendly
quantum-computing foundation and the advanced machine-learning direction.

---

# 1. Book Vision

**Understanding Quantum AI** is a formal but plain-language textbook that
introduces quantum computing from first principles and develops it toward
quantum artificial intelligence and quantum machine learning.

The book begins with the **rules of quantum computing**, not with physics
history, physical motivation, or hardware details. It treats quantum computing
as a computational model with its own rules:

- What is a qubit?
- What is a quantum state?
- What operations are allowed?
- What does measurement do?
- How are circuits built?
- Why are quantum algorithms different from classical algorithms?
- How can these ideas be used in AI and machine learning?
- And, just as important: **when can a classical computer do the same thing?**

The book is designed to be both rigorous and highly accessible. Every concept is
explained in plain language before formal notation is introduced. The reader
should be able to understand each idea intuitively, visually, mathematically,
and computationally.

The book combines basic quantum computing, quantum algorithms, a classical
machine-learning refresher, quantum data encoding, quantum kernels, variational
quantum circuits, quantum neural networks, quantum generative models, quantum
optimization, quantum reinforcement learning, quantum AI applications, practical
programming, visual explanation, assignments, and research-style capstones.

The book is usable in three ways:

1. As a **basic quantum computing textbook**.
2. As an **advanced quantum AI / quantum machine learning textbook**.
3. As a **full-year integrated course** from zero quantum background to
   quantum AI research readiness.

---

# 2. Core Book Promise

By the end of the book, the reader should be able to:

- understand the basic computational rules of quantum computing,
- read and write quantum notation (Dirac notation, state vectors, operators),
- represent qubits and quantum states mathematically and in code,
- simulate quantum gates and circuits, including parameterized gates,
- explain measurement, superposition, interference, and entanglement,
- implement basic quantum algorithms,
- understand the role of quantum computing in search, optimization, and sampling,
- encode classical data into quantum circuits and reason about its true cost,
- build and train hybrid quantum-classical models,
- implement quantum kernel methods,
- implement variational quantum classifiers,
- understand quantum neural networks and how they relate to kernels,
- reason about what quantum models can and cannot represent (expressivity) and
  how well they generalize from limited data,
- recognize when a quantum model is in fact classically simulable (tensor
  networks, dequantization, classical surrogates),
- understand quantum generative models,
- evaluate quantum ML models against honest classical baselines,
- understand noise, density matrices, barren plateaus, and device limits,
- understand error mitigation versus error correction,
- critically evaluate claims about quantum advantage in AI, including
  dequantization, classical-surrogate, and power-of-data results,
- design small quantum AI experiments using Python libraries and simulators.

The central message is:

> Quantum AI is not magic AI. It is machine learning built on a different
> computational substrate, and its advantage on classical data is something to
> be demonstrated, not assumed.

---

# 3. Pedagogical Framework

## 3.1 The central commitment: accessible AND rigorous, never one at the cost of the other

The book's defining promise is a refusal of the usual tradeoff. Most quantum
books are either intuitive-but-shallow or rigorous-but-impenetrable. This book is
built on the claim that the two are not in tension when the order is right:

> Every concept is explained in plain English, with intuition, analogies, mental
> models, diagrams, and fun illustrations, and then carried all the way through
> to full depth, formalism, and coverage. The intuition is the on-ramp to the
> mathematics, not a replacement for it.

Accessibility and rigor are sequenced, not traded. Intuition comes first so the
formalism, when it arrives, lands on prepared ground. The formalism then arrives
in full: no concept is left at the analogy stage, and no equation is presented
without the mental model that makes it readable.

## 3.2 The seven forms

Every important concept is made understandable in seven complementary forms.
A concept is not considered "covered" until it has been expressed in all of them.

| Form | Role in understanding |
|---|---|
| Plain English | A first, jargon-free statement anyone can follow |
| Intuition and mental model | A durable picture the reader can reason *with* later |
| Analogy | A familiar anchor that makes the unfamiliar feel approachable |
| Diagram and fun illustration | The structure made visible and memorable, lightly playful so it sticks |
| Equation and formal definition | Full mathematical precision, nothing hand-waved |
| Code | The concept made executable and inspectable |
| Classical check | "Could a classical computer do this?", the running skeptic |

The diagram-and-illustration form is deliberately allowed to be **fun**: a
well-judged visual metaphor or light illustration is a memory hook, not a
distraction, as long as it is accurate. Playfulness in the picture, seriousness
in the math.

## 3.3 Depth and coverage are non-negotiable

Plain language is the entry, never the ceiling. Three guardrails keep
accessibility from quietly eroding rigor:

- **No concept stops at intuition.** Every analogy is followed by the formal
  definition it was preparing the reader for, and analogies are explicitly
  marked where they break down (an analogy that is never qualified becomes a
  misconception).
- **Full coverage is preserved.** The accessible framing does not let topics be
  skipped. Hard but essential material (density matrices, barren plateaus,
  expressivity theory, dequantization, error correction) is made approachable,
  not omitted.
- **Formalism is supported, not deferred forever.** The mathematical onramp
  (Chapter 0 and Appendix A) means notation never arrives unsupported, so the
  book can be fully formal without being inaccessible.

## 3.4 How concepts are sequenced (cognitive-load design)

Within each concept the order is fixed and deliberate, managing cognitive load by
building the mental model before adding symbolic load:

1. plain-English statement and why it matters,
2. intuition, analogy, mental model, and an illustrating diagram,
3. a tiny worked example,
4. the formal definition and equations,
5. from-scratch code, then library code,
6. the classical check and common misconceptions,
7. active practice.

This is the spine of the chapter template in section 12.

## 3.5 Learning design that makes it stick

Presentation alone is not pedagogy. The book also commits to the mechanics that
turn exposure into durable understanding:

- **Per-chapter learning objectives.** Each chapter opens with measurable "you
  will be able to ..." statements, so activities and assessment stay aligned with
  stated goals (constructive alignment).
- **Formative self-checks with revealed answers.** Short mid-chapter checks let
  readers catch a misunderstanding immediately, which is essential for the
  self-learner audience, rather than waiting for end-of-chapter assignments.
- **Worked-example fading.** Each skill moves from a fully worked example, to a
  partially completed one, to an independent problem, instead of jumping from one
  demonstration straight to unaided practice.
- **Misconception-first design.** Chapters on troublesome ideas start from the
  predictable wrong mental model (superposition as parallelism, entanglement as
  ordinary correlation, measurement as merely looking) and are designed to
  dislodge it.
- **Threshold-concept scaffolding.** The known "troublesome but transformative"
  ideas (superposition, measurement, entanglement, the data-loading cost,
  dequantization) are flagged and given extra intuition, illustration, and
  practice.
- **Retrieval and spacing.** The recurring concept-bridge table and deliberate
  callbacks bring earlier ideas back for retrieval, so hard concepts do not
  decay between parts.
- **Metacognition prompts.** Readers are periodically asked to explain a concept
  back in their own words, the cheapest high-leverage comprehension check.

## 3.6 Differentiated paths

The two core audiences are routed explicitly, not just told that a part is
"skippable": the front-matter dependency graph gives an "if you came from
classical ML, read X and skip Y" and "if you came from physics, read X and skip
Y" path, so each reader gets the accessibility they need without being slowed by
material they already own.

---

# 4. Target Audience and Assumed Background

The book is for graduate students in AI, ML, data science, CS, and engineering;
advanced undergraduates; AI engineers; classical-ML researchers; instructors;
and technically curious readers with Python experience.

## Assumed Background

- basic Python programming,
- basic vectors and matrices,
- basic probability,
- basic machine-learning intuition.

## Not Assumed

- prior quantum computing,
- prior quantum mechanics or physics,
- hardware knowledge,
- complex-number fluency, Dirac notation, or tensor products
  (these are taught from scratch in Chapter 0 and Appendix A),
- advanced functional analysis,
- prior quantum information theory.

A short **diagnostic self-test** in the front matter lets readers locate
themselves and decide which onramp material they need.

---

# 5. Book Positioning

The book occupies a middle position between three common types of books, and
combines their strengths:

- **Traditional quantum-computing textbooks** are rigorous but assume strong
  physics or theory background.
- **Quantum-ML introductions** assume the reader already knows quantum computing.
- **Popular quantum books** are intuitive but too shallow for implementation.

**Understanding Quantum AI** aims for accessible explanation, formal definition,
a complete quantum-computing foundation, AI/ML orientation, runnable code,
visual pedagogy, and graduate-level depth, with a strong skeptical, evaluation-
first spine throughout.

---

# 6. The Conceptual Bridge

The book repeatedly connects quantum-computing concepts to AI/ML concepts. This
table appears in the front matter and recurs, specialized, at the head of each
part.

| Quantum Computing Concept | AI/ML Interpretation |
|---|---|
| Quantum state | Representation |
| Qubit | Smallest quantum information unit |
| Amplitude | Hidden computational weight before measurement |
| Measurement | Sampling / probabilistic output |
| Quantum gate | Transformation of representation |
| Parameterized (rotation) gate | Trainable weight |
| Circuit | Model / computation graph |
| Parameterized circuit | Trainable model |
| Observable | Measured output quantity |
| Expectation value | Prediction or feature |
| Hamiltonian | Objective / cost function |
| Ansatz | Model architecture |
| Shots | Stochastic estimation budget |
| Density matrix | State under uncertainty / noise |
| Noise | Hardware-induced uncertainty |
| Quantum feature map | Nonlinear feature embedding |
| Quantum kernel | Similarity in quantum feature space |
| Variational quantum circuit | Hybrid quantum-classical model |
| Expressivity (Fourier spectrum) | Function class a model can represent |
| Generalization | Performance on unseen data |
| Equivariant ansatz | Symmetry-aware inductive bias |
| Tensor network | Classically tractable model / simulation |
| Quantum reservoir | Fixed nonlinear feature map with trained readout |
| QAOA | Quantum approximate optimization |
| VQE | Quantum optimization of energy/objective |
| Barren plateau | Trainability failure / vanishing gradients |
| Dequantization | Classical algorithm matching a quantum one |
| Quantum advantage | Demonstrable practical or theoretical improvement |

---

# 7. Visual and Diagram Requirements

Diagrams are a core teaching mechanism, not decoration. Each chapter should
contain several of: concept diagrams, circuit diagrams, state-vector diagrams,
Bloch-sphere illustrations, rotation-as-Bloch-rotation diagrams, measurement-
sampling diagrams, amplitude and probability bar plots, interference diagrams,
tensor-product diagrams, entanglement diagrams, algorithm-flow diagrams, hybrid
loop diagrams, quantum-ML pipeline diagrams, kernel-matrix heatmaps, Fourier-
spectrum plots, tensor-network diagrams, training curves, density-matrix / noise
diagrams, ideal-versus-noisy comparison plots, classical-versus-quantum
comparison tables, and capstone architecture diagrams.

**Diagram principle:** every abstract concept should be made visible. A qubit is
shown as a state vector and as a Bloch sphere; a rotation gate as a rotation on
the sphere; measurement as repeated sampling; interference as amplitudes adding
and canceling; entanglement as a non-decomposable dependency; a quantum kernel
as data flowing through a feature map into a similarity matrix; a variational
classifier as a hybrid loop; a tensor network as a graph of linked tensors.

---

# 8. Programming Philosophy

Programming is a way to understand ideas, not only to implement them. The path
moves through four stages.

- **Stage 1 - Manual simulation with NumPy.** State vectors, normalization,
  measurement, gates (including rotation gates), tensor products, multi-qubit
  states, simple circuits, Bell states, density matrices, small algorithms.
  Purpose: make the rules transparent.
- **Stage 2 - Quantum SDKs.** PennyLane (primary, differentiable) and Qiskit
  (2.x). Purpose: move from toy implementation to practical workflow.
- **Stage 3 - Classical ML integration.** scikit-learn, NumPy, Matplotlib,
  optionally PyTorch. Purpose: prevent fake quantum advantage by requiring
  honest baselines.
- **Stage 4 - Full experiments.** Dataset, model, baseline, training,
  evaluation, ablation, noise analysis, report. Purpose: turn quantum AI into
  disciplined experimental research.

Every code listing in the book corresponds to a runnable, version-pinned
notebook in the companion repository (see Appendix C).

---

# 9. Main Python Libraries

## Required

- **NumPy** - vectors, matrices, tensor products, from-scratch simulation.
- **Matplotlib** - probability plots, training curves, heatmaps, visuals.
- **scikit-learn** - classical ML baselines, toy datasets, kernels, metrics.
- **PennyLane** - differentiable quantum circuits, hybrid models, variational
  quantum ML. The primary spine for trainable models.
- **Qiskit 2.x** - circuits, simulators (`qiskit-aer`), gates, measurement,
  quantum algorithms (`qiskit-algorithms`), and quantum ML
  (`qiskit-machine-learning`).

## Recommended additions

- **CUDA-Q (NVIDIA)** - now a first-class hybrid framework (v0.14 line, 2026),
  with GPU-accelerated simulation and tight GPU-QPU coupling (NVQLink /
  `cudaq-realtime`). Worth a sidebar as the emerging HPC-quantum stack.
- **A tensor-network library** - `quimb` (with `cotengra` for contraction-path
  optimization) for the tensor-network and classical-simulation chapters.

## Optional

- **PyTorch** - neural-network baselines, neural quantum states, and hybrid
  classical-quantum models (integrates with PennyLane via `qml.qnn.TorchLayer`).
- **NetworkX** - graphs, MaxCut, QAOA, graph-learning experiments.
- **Cirq** - Google ecosystem; also the dependency of TensorFlow Quantum.

## Version and maintenance note

Targets are pinned in Appendix C and reflect a 2026 snapshot:
- **Qiskit 2.x** (v2.3/2.4 line). Qiskit 1.0/2.0 removed the pre-1.0 API
  (`execute`, `Opflow`, `QuantumInstance`) and split `aer`, `algorithms`, and
  `machine-learning` into separate packages. Code must not use 0.x/1.x APIs.
- **PennyLane 0.45+**, noting the **2026 PennyLane v2 API change**: older online
  tutorials use the previous API, so the book follows the migration guide.
- **Amazon Braket** now supports Qiskit 2.0 (Dec 2025).
- **TensorFlow Quantum** is **maintained but low-velocity** (v0.7.x, tied to
  Cirq); it is not deprecated, but it is not the book's spine and is mentioned
  only for readers already in that ecosystem. PennyLane is the primary spine.

---

# 10. Dual Course Use

## Course A - Basic Quantum Computing

Parts I-III, Part VIII, and selected Part VII chapters (QAOA, VQE).
Outcome: students understand the computational model and can build, simulate,
and explain basic quantum circuits and algorithms.

## Course B - Advanced Quantum AI / Quantum Machine Learning

Parts IV-VII, Part IX, Part X (with Parts I-III as a review/onramp).
Outcome: students implement, evaluate, and critically analyze quantum ML models
and quantum AI pipelines.

## Integrated Full-Year Course

Semester 1: quantum-computing foundations and algorithms (Parts I-III, VIII).
Semester 2: quantum AI and machine learning (Parts IV-VII, IX, X).

A **chapter-dependency graph** in the front matter shows prerequisites so
self-learners and instructors can chart a path.

---

# 11. Complete Book Structure

The book has a Foundations onramp, ten parts, and four appendices.

```text
Front Matter   Preface, how to read, diagnostic self-test, notation guide,
               dependency graph
Chapter 0      Mathematical Foundations You Actually Need
Part I         The Rules of the Quantum Computing Game
Part II        Essential Quantum Ideas for AI
Part III       Building Quantum Algorithms
Part IV        Classical Machine Learning Refresher for Quantum AI
Part V         Encoding Data into Quantum Circuits
Part VI        Quantum Machine Learning Models
Part VII       Quantum Optimization for AI
Part VIII      Reality Check: Noise, Hardware, and Limits
Part IX        Advanced Topics in Quantum AI
Part X         Capstone Projects
Back Matter    Appendices A-D, glossary, bibliography, index
```

Chapter numbering note: the book has Chapter 0 plus **64 numbered chapters**.
New chapters relative to v1 are flagged **[NEW]**; the rest are revised. Section
23 (Topic Coverage Map) traces every major topic to its chapter.

## 11.1 Deliberate scope boundaries

To keep "comprehensive" honest, a few areas are intentionally out of the main
arc and treated only as sidebars in the relevant chapters, with pointers to the
literature rather than full chapters:

- **Continuous-variable / photonic quantum ML** (a separate computational
  paradigm; the book is gate-model and qubit-based). Noted in the hardware
  chapter and the generative chapter.
- **Quantum privacy, federated, and blind quantum ML.** Noted briefly in the
  AI-for-quantum and advanced sections.
- **Cryptographic impact (Shor) and post-quantum security.** Touched in the QFT
  chapter; a full security treatment is out of scope.

These boundaries are stated so the reader knows what is covered, what is
sidebarred, and where to look further.

---

# Front Matter

- **Preface and how to read this book** - the seven-forms method, the
  evaluation-first stance, and how to use the dependency graph.
- **Diagnostic self-test** - short checks on Python, linear algebra, probability,
  and ML so readers can decide what onramp material to read.
- **Notation guide** - Dirac notation, state vectors, operators, common symbols,
  and conventions, in one place for reference.
- **Chapter-dependency graph** - a DAG of prerequisites with suggested paths for
  the three courses.

---

# Chapter 0 - Mathematical Foundations You Actually Need  **[NEW]**

### Description

A focused, plain-language onramp that teaches exactly the mathematics the rest
of the book uses, and nothing more. Written so an ML engineer or CS graduate can
read Chapter 2 without hitting a wall.

### Focus

- Complex numbers: modulus, phase, Euler form, why phase matters.
- Vectors, inner products, norms, orthonormal bases.
- Matrices as linear maps; matrix-vector and matrix-matrix products.
- Special matrices: Hermitian, unitary, why unitarity preserves probability.
- Eigenvalues and eigenvectors, and why they are the measurable quantities.
- The tensor product as an operation on vectors and matrices.
- Probability essentials: distributions, expectation, sampling, variance.
- Dirac notation introduced gently as a bookkeeping convenience.

### Programming Demonstration

Implement complex arithmetic, inner products, unitarity checks, and a tensor
product in NumPy; verify each property numerically.

### Assignment

Verify that given matrices are unitary or Hermitian; compute eigenvalues;
construct tensor products by hand and confirm in code.

> Readers fluent in linear algebra can skim this and use it as reference;
> Appendix A holds the fuller treatment and proofs.

---

# Part I - The Rules of the Quantum Computing Game

## Focus of Part I

Quantum computing as a new rule-based model of computation: qubits, state
representation, measurement, gates (including the parameterized rotation gates
that all later machine learning depends on), and circuits, with Python
simulation and forward links to AI/ML.

---

## Chapter 1 - Quantum Computing Without Physics

Quantum computing presented as a computational model rather than a physics
story. Why it matters for AI, what "Quantum AI" can and cannot mean, common
misconceptions, and the scope of the book.

- **Programming demonstration:** represent deterministic bits, random bits, and
  simple probability distributions in Python.
- **Assignment:** compare classical deterministic, probabilistic, and quantum
  computation in writing.

---

## Chapter 2 - Qubits: The Smallest Quantum Data Object

The qubit as a vector of amplitudes, not a tiny physical object. Amplitude
versus probability, why normalization matters, why amplitudes can be negative or
complex. Concepts: |0>, |1>, state vector, amplitude, probability, normalization.

- **Diagrams:** state-vector diagram, probability bar plot, Bloch-sphere preview.
- **Programming demonstration:** represent one-qubit states in NumPy and check
  normalization.
- **Assignment:** build valid and invalid qubit states and compute measurement
  probabilities.

---

## Chapter 3 - Measurement: From Quantum State to Classical Output

Measurement as the process that turns quantum information into classical data.
Why it is probabilistic and why repeated measurement is necessary. Concepts:
measurement, Born rule, sampling, shots, collapse, output distribution.
**Now also introduces measuring in a chosen basis and the idea of an observable
expectation value**, so VQE and variational classifiers have foundations early.

- **Diagrams:** measurement pipeline, repeated-sampling histogram,
  before/after-measurement state.
- **Programming demonstration:** simulate repeated measurements of a one-qubit
  state; estimate a Pauli expectation value from shots.
- **Assignment:** estimate probabilities from repeated measurements and study
  the effect of sample size and shot noise.

---

## Chapter 4 - Quantum Gates: Legal Moves in the Game

Gates as unitary matrix transformations. Reversibility, common one-qubit gates,
phase. Concepts: identity, X, Y, Z, H, S, T, phase, unitarity.

- **Diagrams:** gate-action diagrams, matrix-vector visualizations,
  before/after probability plots.
- **Programming demonstration:** implement one-qubit gates in NumPy.
- **Assignment:** build a one-qubit gate simulator.

---

## Chapter 5 - The Bloch Sphere and Rotation Gates  **[NEW]**

### Description

The single-qubit state visualized on the Bloch sphere, and single-qubit gates
seen as rotations. This chapter introduces the **parameterized rotation gates
RX, RY, RZ** that are the trainable building blocks of every model in Part VI.
Without this chapter, variational circuits arrive unexplained.

### Focus

- Bloch-sphere coordinates and what points mean.
- X, Y, Z, H as specific rotations.
- RX(theta), RY(theta), RZ(theta) as continuous, parameterized rotations.
- Global versus relative phase.
- Rotation angle as a trainable weight (forward link to variational models).

### Diagrams

- Bloch sphere with state vector.
- Rotation arcs for RX/RY/RZ.
- Gate sequence as a path on the sphere.

### Programming Demonstration

Implement rotation gates in NumPy; animate or plot how a state moves on the
Bloch sphere as the angle changes.

### Assignment

Find rotation angles that map |0> to a target state; verify on the sphere and in
code.

---

## Chapter 6 - Quantum Circuits: Programs Made of Gates

Circuits as programs built from gates and measurements. Circuit notation,
translating a diagram into code, circuits as model architectures. Concepts:
circuit, wire, gate, measurement register, state preparation, execution.

- **Diagrams:** simple circuit diagrams, circuit-to-code mapping, circuit as
  computation graph.
- **Programming demonstration:** build simple circuits in PennyLane and Qiskit.
- **Assignment:** implement equivalent circuits in NumPy, PennyLane, and Qiskit.

---

# Part II - Essential Quantum Ideas for AI

## Focus of Part II

The ideas that make quantum computation different: superposition, interference,
multi-qubit state spaces, tensor products, multi-qubit gates, entanglement,
reversibility, no-cloning. AI/ML focus: representation, dependency, feature
transformation, computational structure.

---

## Chapter 7 - Superposition: Representation Before Computation

Superposition without exaggeration: a way of representing possibilities through
amplitudes, not "all answers for free." Why it is not classical uncertainty, why
measurement limits extraction, connection to distributed representations.

- **Programming demonstration:** create superposition with the Hadamard gate.
- **Assignment:** compare measurement statistics for basis states and
  superposition states.

---

## Chapter 8 - Interference: Making Some Answers Louder and Others Quieter

Interference as the mechanism behind quantum algorithms: amplitudes add or
cancel. Constructive and destructive interference, phase and sign, why algorithm
design depends on interference. **Introduces phase kickback** as the recurring
mechanism behind later algorithms.

- **Diagrams:** amplitude arrows, cancellation diagrams, interfering circuit
  paths, phase-kickback diagram.
- **Programming demonstration:** circuits where probabilities appear and vanish
  through interference.
- **Assignment:** design a circuit that suppresses one outcome and amplifies
  another.

---

## Chapter 9 - Multiple Qubits, Tensor Products, and Multi-Qubit Gates

How states grow with multiple qubits; tensor products visually and
computationally; exponential state spaces; connection to high-dimensional
feature spaces. **Now also covers the essential multi-qubit gates** (CNOT,
controlled-U, SWAP, Toffoli) and entangling layers, which Part VI relies on.

- **Diagrams:** state-space growth, tensor-product grid, basis-state tree,
  controlled-gate diagrams.
- **Programming demonstration:** implement tensor products and multi-qubit gates
  in NumPy.
- **Assignment:** construct two- and three-qubit states and apply controlled
  gates.

---

## Chapter 10 - Entanglement: Dependencies Beyond Classical Correlation

Entanglement as a multi-qubit state that cannot be separated into independent
parts, without mystery. Product states, entangled states, Bell states,
measurement dependency, entanglement versus ordinary correlation.

- **Diagrams:** product-state, entangled-state, Bell-pair measurement outcomes.
- **Programming demonstration:** create and measure Bell states.
- **Assignment:** test whether simple two-qubit states are separable or entangled.

---

## Chapter 11 - Reversibility, No-Cloning, and Information Flow

Why quantum operations are reversible and why unknown states cannot be copied,
and what that means for data handling and algorithm design. Reversible
computation, no-cloning, information flow, uncomputation of ancillas.

- **Diagrams:** reversible-gate diagram, attempted-copying circuit, classical
  copying versus no-cloning.
- **Programming demonstration:** show that CNOT copies classical basis states
  but not arbitrary quantum states.
- **Assignment:** experiment with attempted copying of different input states.

---

# Part III - Building Quantum Algorithms

## Focus of Part III

The structure of quantum algorithms: preparation, transformation, interference,
measurement. The AI/ML connection is search, optimization, feature extraction,
sampling, and objective minimization. This part now also confronts the
algorithm (HHL) that motivated much early quantum-ML hype, and names Shor's
algorithm as the canonical payoff of the QFT.

---

## Chapter 12 - Quantum Algorithm Design Pattern

The general pattern: prepare, transform, interfere, measure, repeat. Oracles,
interference as a design tool, measurement as output extraction, why quantum
algorithms are hard to design. Uncomputation and phase kickback revisited.

- **Programming demonstration:** implement a small oracle-based circuit.
- **Assignment:** analyze circuits according to the prepare-transform-measure
  pattern.

---

## Chapter 13 - Deutsch-Jozsa Algorithm

The first clean demonstration of algorithmic advantage on a structured problem.
Oracle problem, constant versus balanced functions, interference revealing
global structure, conceptual advantage.

- **Programming demonstration:** implement Deutsch-Jozsa in Qiskit.
- **Assignment:** create different oracles and verify the algorithm.

---

## Chapter 14 - Grover Search and Amplitude Amplification

Quantum search that amplifies desired answers. Marked solutions, amplitude
amplification, quadratic speedup, relevance to AI search and optimization.

- **Programming demonstration:** run Grover search on a small database.
- **Assignment:** vary the number of marked solutions and observe the effect.

---

## Chapter 15 - Quantum Fourier Transform, Phase Estimation, and Shor in Brief

The QFT as a way to extract periodic and phase structure; phase estimation;
relevance to hidden structure and spectral methods. **A short, honest section on
Shor's factoring algorithm** closes the loop on why QFT and phase estimation
matter, without a full derivation, and notes the post-quantum-security
implication.

- **Programming demonstration:** implement the QFT on small inputs and run phase
  estimation.
- **Assignment:** compare classical Fourier intuition and QFT circuit behavior.

---

## Chapter 16 - Quantum Linear Algebra and the HHL Algorithm  **[NEW]**

### Description

The quantum linear-systems algorithm (HHL) and the broader idea of "quantum
linear algebra," because so many early quantum-ML speedup claims rest on it, and
because its later **dequantization** is one of the most instructive episodes in
the field. Presented conceptually, with its assumptions and caveats made
explicit.

### Focus

- Solving linear systems as a computational primitive in ML.
- What HHL promises and the fine print (sparsity, condition number, state
  preparation, reading out the answer).
- The role of **QRAM** and why efficient data loading is an unproven assumption.
- Why "exponential speedup" claims need every assumption on the table.
- Forward link to the dequantization discussion in Part VIII.

### Programming Demonstration

Run a tiny HHL example on a simulator and compare with a direct classical solve.

### Assignment

List the assumptions HHL needs and explain which ones are hard to meet in
practice.

---

## Chapter 17 - Hamiltonians, Energy, and Objective Functions

Hamiltonians as mathematical descriptions of objectives or energies, preparing
for VQE, QAOA, and quantum optimization. Energy as objective, Hamiltonian as
cost, ground state as optimum, mapping problems to objectives, observables.

- **Programming demonstration:** represent a simple binary objective as an energy
  function.
- **Assignment:** encode a small optimization problem as a Hamiltonian-like cost.

---

## Chapter 18 - VQE: Variational Quantum Eigensolver

VQE as a hybrid quantum-classical algorithm minimizing an energy objective.
Parameterized circuits, energy expectation, classical optimizer, the hybrid
loop, connection to trainable ML models.

- **Programming demonstration:** implement a small VQE example.
- **Assignment:** change the ansatz and study optimization behavior.

---

# Part IV - Classical Machine Learning Refresher for Quantum AI

## Focus of Part IV

A compact ML refresher focused on concepts that map directly to quantum ML.
**Explicitly skippable** for ML-literate readers and flagged as a prerequisite
for physics-literate readers, per the dependency graph.

---

## Chapter 19 - Machine Learning as Function Learning

ML as learning functions from data: data, labels, models, loss, generalization,
evaluation. Concepts: classification, regression, loss, training, validation,
generalization.

- **Programming demonstration:** train a simple classifier with scikit-learn.
- **Assignment:** create classical baselines for toy datasets.

---

## Chapter 20 - Feature Spaces and Kernels

Feature maps and kernels, preparing for quantum kernels. Feature
transformations, similarity, the kernel trick, SVMs, kernel matrices.

- **Programming demonstration:** train linear, polynomial, and RBF-kernel SVMs.
- **Assignment:** visualize and compare kernel matrices.

---

## Chapter 21 - Neural Networks and Trainable Models

Trainable models, parameters, gradients, optimization, preparing for variational
circuits. Concepts: parameter, gradient, optimizer, neural network,
backpropagation.

- **Programming demonstration:** train a small neural network or a simple
  differentiable model.
- **Assignment:** compare learning curves for different model sizes.

---

## Chapter 22 - Generative Models and Sampling

Generative modeling and sampling, preparing for quantum generative models.
Probability distributions, sampling, discriminative versus generative models,
distribution learning.

- **Programming demonstration:** train or simulate a simple probabilistic
  generator.
- **Assignment:** compare target and learned distributions.

---

# Part V - Encoding Data into Quantum Circuits

## Focus of Part V

How classical data becomes input to quantum circuits, one of the most important
and underestimated problems in quantum ML, including its true cost.

---

## Chapter 23 - The Data Loading Problem

Why loading classical data is not free and why encoding choices affect
performance. Basis, angle, and amplitude encoding; state preparation.
**Now states plainly that general amplitude encoding is exponentially expensive
in circuit depth**, and **names QRAM and the open question of its physical
feasibility**, since many speedup claims silently assume efficient data loading.
This sets up the honesty track and links forward to HHL (Chapter 16) and the
advantage chapter.

- **Programming demonstration:** encode simple vectors with several methods and
  measure the circuit cost.
- **Assignment:** compare encodings on a toy classification dataset.

---

## Chapter 24 - Quantum Feature Maps

Data-dependent circuits that map classical inputs into quantum states. Feature
maps, data-dependent gates, circuit depth, expressivity, **data re-uploading**.

- **Programming demonstration:** implement feature maps in PennyLane and Qiskit.
- **Assignment:** study how feature-map depth changes classification performance.

---

## Chapter 25 - Measurement as Feature Extraction

How measurement results and expectation values become features for classical ML.
Observables, expectation values, measurement features, shot noise, classical
post-processing.

- **Programming demonstration:** extract quantum features and train a classical
  classifier.
- **Assignment:** analyze the effect of shot count on feature stability.

---

# Part VI - Quantum Machine Learning Models

## Focus of Part VI

The core quantum-ML section: quantum kernels (and their exponential
concentration), the result that **variational models are kernel methods**,
variational circuits, quantum neural networks, gradient methods, barren plateaus,
**what quantum models can actually learn (expressivity and generalization)**,
structured and **equivariant** models, **tensor networks** as the classical/
quantum bridge, **reservoir computing**, generative models (Born and Boltzmann
machines), and reinforcement learning.

---

## Chapter 26 - Quantum Kernels

Quantum circuits computing similarity in a quantum feature space. Quantum feature
space, kernel estimation, SVM with a quantum kernel, classical comparison.
**Now also covers exponential concentration of quantum kernels**, the kernel-
method analog of barren plateaus, so quantum kernels are not presented as a free
lunch.

- **Programming demonstration:** build a quantum-kernel classifier with
  `qiskit-machine-learning`.
- **Assignment:** compare quantum kernels with RBF and polynomial kernels, and
  measure how kernel values concentrate as the qubit count grows.

---

## Chapter 27 - Variational Quantum Circuits

Parameterized quantum circuits as trainable models. Trainable rotation gates
(callback to Chapter 5), ansatz design, hybrid optimization, measurement-based
prediction.

- **Programming demonstration:** train a variational classifier with PennyLane.
- **Assignment:** study how ansatz depth affects training and accuracy.

---

## Chapter 28 - Variational Models Are Kernel Methods  **[NEW]**

### Description

A short, unifying chapter on the result that any data-encoding variational
quantum model can be viewed as a kernel method, with the encoding fixing the
kernel and the trainable part acting in that fixed feature space. This bridges
Chapters 26 and 27, sharpens intuition, and frames why expressivity alone does
not guarantee advantage.

### Focus

- The feature map induced by data encoding.
- Why the variational part operates inside a fixed kernel-defined space.
- What this implies for generalization and for advantage claims.
- Practical consequence: encoding choices may matter more than ansatz choices.

### Programming Demonstration

Show empirically that a trained variational classifier and a quantum-kernel SVM
with the same encoding behave similarly on a toy dataset.

### Assignment

Hold the encoding fixed and vary the ansatz; observe how much the decision
boundary actually changes.

---

## Chapter 29 - Quantum Neural Networks

What QNNs are and how they relate to classical neural networks. QNN structure,
input encoding, trainable quantum layers, classical output layers, hybrid models.

- **Programming demonstration:** implement a small QNN classifier (PennyLane +
  optional PyTorch layer).
- **Assignment:** compare QNN and classical neural-network baselines.

---

## Chapter 30 - Gradients, Parameter-Shift, and Training

How quantum models are trained and how gradients are estimated. Parameter-shift
rule, finite differences, automatic differentiation, sampling noise,
optimization difficulty.

- **Programming demonstration:** compute gradients manually and with PennyLane.
- **Assignment:** compare gradient-estimation methods.

---

## Chapter 31 - Barren Plateaus and Trainability

Barren plateaus as a major limitation of trainable quantum models. Vanishing
gradients, circuit depth, random initialization, local versus global costs,
ansatz design. **Now connects to the recent result that the absence of barren
plateaus often implies classical simulability**, a sobering and current point,
and links to the kernel-concentration result in Chapter 26.

- **Programming demonstration:** measure gradient variance for circuits of
  different depth.
- **Assignment:** design a shallower or more structured ansatz and compare
  trainability; discuss the simulability tradeoff.

---

## Chapter 32 - What Can Quantum Models Learn? Expressivity and Generalization  **[NEW]**

### Description

The learning-theory pillar that complements trainability (barren plateaus). It
answers two questions the rest of Part VI raises but does not settle: what
functions can a parameterized quantum model represent (expressivity), and how
well does it generalize from limited data (generalization)?

### Focus

- Parameterized circuits as a **truncated Fourier series** in the input, with the
  accessible frequency spectrum set by the data encoding (callback to Chapter 24).
- How encoding richness, not ansatz depth alone, controls the function class.
- Generalization and sample complexity for quantum models; why more expressivity
  is not automatically better (overfitting, the expressivity-versus-trainability
  tension).
- The link to the kernel view (Chapter 28) and to advantage claims (Chapter 49).

### Diagrams

- Fourier-spectrum plots that widen as encoding repetitions increase.
- A train-versus-test error curve against model expressivity.

### Programming Demonstration

Fit a one-dimensional function with a variational model; show the accessible
Fourier spectrum changing with encoding repetitions; plot the generalization gap.

### Assignment

Vary encoding richness, measure the accessible frequencies, and relate them to
the train/test gap.

---

## Chapter 33 - Quantum Convolutional and Structured Models

Structured quantum models: quantum convolutional ideas, local-circuit inductive
biases, pooling analogies, hierarchy. QCNNs are notable for being among the few
ansaetze provably free of barren plateaus. **The honest flip side, current to
2025:** that same structure makes QCNNs effectively classically simulable (PRX
Quantum 2025), a concrete instance of the trainability-versus-advantage tension
from Chapter 31. The chapter presents both faces.

- **Programming demonstration:** build a small structured quantum classifier.
- **Assignment:** compare local and fully connected circuit patterns, and discuss
  why provable trainability and classical simulability tend to arrive together.

---

## Chapter 34 - Geometric and Equivariant Quantum Machine Learning  **[NEW]**

### Description

Building the symmetries of a problem directly into the circuit so the model
respects the structure of its data, the quantum analog of geometric deep
learning. Symmetry-aware ansatze are a leading route to models that are both
trainable and useful, and they generalize the structured idea of Chapter 33.

### Focus

- Inductive bias and symmetry (permutation, rotation, label symmetries).
- Equivariant ansatze and symmetry-preserving gates.
- Why respecting symmetry can avoid barren plateaus and improve generalization.
- Connection to QCNN (a special structured case) and to classical geometric deep
  learning.

### Diagrams

- A symmetry acting on data and the matching equivariant circuit.
- Trainability comparison: symmetric versus unstructured ansatz.

### Programming Demonstration

Build a small permutation-equivariant circuit and compare it with an unstructured
ansatz on a symmetric task.

### Assignment

Identify a symmetry in a toy dataset and design a circuit that respects it.

---

## Chapter 35 - Tensor Networks: The Bridge Between Quantum and Classical ML  **[NEW]**

### Description

Tensor networks (matrix product states, PEPS, MERA) as a third lens on quantum
machine learning. They are how we classically simulate quantum circuits, why some
"quantum" models are in fact classically tractable (linking dequantization and
the barren-plateau / simulability result), and a trainable model class in their
own right.

### Focus

- Tensor-network diagrams as a visual language for multi-qubit states.
- Matrix product states and **bond dimension** as a measure of entanglement and
  of simulability.
- Tensor networks as classical ML models (the MPS classifier).
- Why tensor networks explain when "quantum" is classically simulable
  (forward link to Chapter 49).

### Diagrams

- State as a chain of linked tensors.
- Bond dimension growing with entanglement.

### Programming Demonstration

Represent a small state as an MPS; train a tiny MPS classifier; show how bond
dimension controls expressivity and cost.

### Assignment

Compute the bond dimension needed for a given entangled state and relate it to
classical simulation cost.

---

## Chapter 36 - Quantum Reservoir Computing  **[NEW]**

### Description

A near-term, training-light model class: a fixed (untrained) quantum system acts
as a high-dimensional reservoir, and only a simple classical readout is trained.
Because the quantum part is not optimized, reservoir computing sidesteps barren
plateaus entirely.

### Focus

- Reservoir computing and extreme learning machines, classical and quantum.
- The quantum reservoir as a fixed nonlinear feature map, including over time.
- Why no quantum gradient training is needed, and what that buys and costs.
- Temporal and sequence tasks as a natural fit.

### Programming Demonstration

Drive a small fixed quantum circuit as a reservoir and train a linear readout on
a toy time-series task.

### Assignment

Compare a quantum-reservoir readout with a classical baseline on a sequence task.

---

## Chapter 37 - Quantum Generative Models

Quantum circuits as samplers representing probability distributions. Born
machines, **quantum Boltzmann machines**, distribution learning, quantum GAN
ideas, sampling quality. **Current to 2025:** generative models are the setting
with the strongest recent advantage claim, a barren-plateau-free family that is
classically hard and was demonstrated on a 68-qubit processor (Huang et al.,
2025), set honestly against the conditions under which generative models can be
classically surrogated.

- **Programming demonstration:** train a circuit (a Born machine) to match a
  simple binary distribution.
- **Assignment:** evaluate generated samples against a target distribution and
  contrast the Born-machine and Boltzmann-machine views.

---

## Chapter 38 - Quantum Reinforcement Learning

Possible roles of quantum circuits in sequential decision-making. Policies,
value functions, quantum parameterized policies, optimization inside RL.

- **Programming demonstration:** use a small variational circuit as a policy
  model in a toy environment.
- **Assignment:** compare classical and quantum policy parameterizations.

---

# Part VII - Quantum Optimization for AI

## Focus of Part VII

Quantum and quantum-inspired optimization relevant to AI: feature selection,
clustering, scheduling, assignment, combinatorial search.

---

## Chapter 39 - QAOA: Quantum Approximate Optimization Algorithm

QAOA as a hybrid algorithm for approximate combinatorial optimization. Cost and
mixer Hamiltonians, alternating layers, the classical loop, a MaxCut example.

- **Programming demonstration:** solve a small MaxCut problem with QAOA.
- **Assignment:** vary QAOA depth and compare solution quality.

---

## Chapter 40 - QUBO and Ising Formulations

Representing AI-related optimization as binary objective functions. Binary
variables, QUBO, Ising models, mapping problems to energy functions.

- **Programming demonstration:** formulate feature selection as QUBO.
- **Assignment:** map a small scheduling or assignment problem into QUBO form.

---

## Chapter 41 - Quantum Annealing and Quantum-Inspired Optimization

Quantum annealing and how it differs from gate-based computing. Annealing
intuition, energy landscape, gate model versus annealing, quantum-inspired
algorithms (and where classical heuristics already win).

- **Programming demonstration:** solve a small binary optimization with classical
  and quantum-inspired solvers.
- **Assignment:** compare heuristic solutions across random problem instances.

---

## Chapter 42 - Optimization in AI Pipelines

Connecting quantum optimization to practical AI tasks: feature selection,
clustering, hyperparameter selection, architecture search, resource allocation.

- **Programming demonstration:** use a binary optimization formulation for
  feature selection.
- **Assignment:** compare classical greedy search, random search, and a
  QUBO-based formulation.

---

# Part VIII - Reality Check: Noise, Hardware, and Limits

## Focus of Part VIII

The practical constraints: density matrices and noise, simulators versus
hardware, error mitigation versus correction, the 2026 hardware landscape,
scaling limits, and a rigorous framework for evaluating advantage including
complexity classes and dequantization.

---

## Chapter 43 - Density Matrices and Mixed States  **[NEW]**

### Description

The minimal density-matrix machinery needed to talk about noise honestly. Pure
versus mixed states, the density matrix, partial trace and reduced states, and
why noise turns pure states into mixed ones. Kept light-touch and motivated by
the noise chapter that follows.

### Focus

- Why state vectors are not enough once there is uncertainty.
- The density matrix as a representation of "a state under uncertainty."
- Partial trace and reduced states (a second view of entanglement).
- Setting up the language for noise channels.

### Programming Demonstration

Build density matrices in NumPy; compute a partial trace; show a noisy operation
turning a pure state into a mixed one.

### Assignment

Given a two-qubit state, compute the reduced state of one qubit and interpret it.

---

## Chapter 44 - Simulators Versus Real Quantum Hardware

Ideal simulation, noisy simulation, and real hardware. Shots, connectivity,
queues, execution limits, circuit depth.

- **Programming demonstration:** compare ideal and noisy circuit simulation.
- **Assignment:** evaluate how circuit depth affects output stability.

---

## Chapter 45 - Noise and Error Mitigation

Noise as unwanted transformation, now expressible with density matrices and
noise channels. Gate noise, measurement noise, decoherence, error mitigation,
and the difference between mitigation and correction.

- **Programming demonstration:** add noise to circuits and compare outputs;
  apply a simple mitigation technique.
- **Assignment:** test quantum-classifier robustness under different noise levels.

---

## Chapter 46 - Error Correction and the Road to Fault Tolerance  **[NEW]**

### Description

What error correction is and why it differs from mitigation. Logical versus
physical qubits, redundancy, the threshold theorem, surface-code intuition, and
why fault tolerance, not raw qubit count, is the real milestone. Written
conceptually but grounded in 2024-2026 milestones.

### Focus

- Mitigation reduces error in an answer; correction removes it from the
  computation.
- Logical qubits built from many physical qubits; the threshold theorem in plain
  language.
- **"Below threshold" (Google Willow, Dec 2024):** logical error falling as code
  distance grows, for quantum *memory*. What it does and does not prove, and why
  it is not yet full fault tolerance.
- **The honest gap:** logical error rates are still around 10^-3, against the
  roughly 10^-6 a useful fault-tolerant algorithm needs.
- **Error-detected versus error-corrected** logical qubits (press releases blur
  these; the book does not).
- **Codes:** surface codes versus **qLDPC codes** (IBM's lower-overhead bet) and
  **cat / bosonic codes** (AWS Ocelot).
- **Magic-state distillation and T-gates** as the real remaining bottleneck:
  error correction gives Clifford gates almost for free, but universality needs
  distilled magic states. First logical-level demos appeared in 2025.
- **Machine-learned decoders** (AlphaQubit and real-time neural decoders) as the
  link to Chapter 56.
- What "fault-tolerant" would change for quantum ML.

### Programming Demonstration

Simulate a tiny repetition or bit-flip code and show error suppression.

### Assignment

Explain, with the threshold idea, why error rates below a threshold make
arbitrarily long computation possible, and distinguish below-threshold memory
from full fault tolerance.

---

## Chapter 47 - The 2026 Hardware Landscape  **[NEW]**

### Description

A grounded snapshot of real quantum hardware so the reader's mental model
matches reality. The main platforms, their tradeoffs, and what "utility-scale"
experiments have and have not shown. Hardware-agnostic in spirit, concrete once,
with the explicit caveat that exact numbers date quickly.

### Focus

- **Five live modalities**, each with a different error profile:
  superconducting (fast gates, finite coherence; Google Willow 105 qubits,
  IBM Heron), trapped-ion (highest fidelities, slower, all-to-all; Quantinuum
  Helios, IonQ), neutral-atom (reconfigurable, atom shuttling; QuEra, Pasqal,
  Atom Computing), photonic (room-temperature, manufacturable, loss-dominated;
  PsiQuantum, also the home of continuous-variable computing, a sidebar), and
  silicon-spin (CMOS-manufacturable; Diraq/imec crossed the error-correction
  fidelity threshold in foundry-made qubits, Nature 2025).
- Qubit counts, error rates, connectivity, and clock speeds as a comparison,
  with the warning that headline qubit counts are the least informative number.
- The distinction between physical, error-detected, and error-corrected logical
  qubits in vendor announcements.
- **Vendor fault-tolerance roadmaps** cluster around 2029-2030 (IBM Starling
  2029 on qLDPC codes; Quantinuum, IonQ, PsiQuantum near 2030): roadmaps, not
  guarantees.
- What recent utility-scale and early error-corrected results actually
  demonstrate, stated without hype.
- How to access real devices (IBM Quantum, Amazon Braket, Azure Quantum).

### Assignment

Pick a platform and summarize its strengths, weaknesses, and current scale, and
explain why qubit count alone is a poor figure of merit.

---

## Chapter 48 - Scaling Problems and Simulation Limits

Why simulating quantum systems becomes expensive and why it matters for learning
experiments. Exponential state space, memory and runtime scaling, depth,
practical limits, and how tensor-network methods (Chapter 35) push the boundary.

- **Programming demonstration:** measure runtime and memory growth for small
  simulated systems.
- **Assignment:** estimate resource requirements for increasing qubit numbers.

---

## Chapter 49 - What Would Quantum Advantage Mean? Complexity, Dequantization, and Honest Baselines

### Description

A disciplined, current framework for evaluating advantage claims, the single most
important honesty chapter in the book.

### Focus

- A plain-language treatment of **complexity classes (BQP)** and what is actually
  believed about quantum speedups, so "a quantum computer tries all answers at
  once" is retired for good.
- Speed, sample, representation, and practical advantage.
- Baseline comparison, benchmarks, ablation, statistical caution.
- **Dequantization:** classical algorithms that matched quantum-ML speedups
  (recommendation systems and quantum linear algebra), and what they teach.
- **Classical surrogates** of variational models, and the link from Chapter 31:
  absence of barren plateaus often implies the model is classically simulable
  (and the tensor-network view from Chapter 35).
- **The standard honest-benchmarking protocol** (Bowles, Ahmed, and Schuld,
  2024): tuned classical baselines, no downscaled-MNIST, ablate entanglement to
  see whether it even helps, report dataset-selection bias, and use a shared
  open suite. This is the practical template the capstones follow.
- **Sampling advantage is real but is not ML**: random-circuit-sampling advantage
  has largely survived classical refutation, yet it is a contrived task, the
  cross-entropy benchmark itself can be spoofed, and several "utility" claims
  (IBM 2023, some 2025 results) were later simulated classically.
- **The open frontier:** advantage hinges on representability; tensor-network
  simulation removes many regimes, but specific structured function classes may
  remain classically intractable.
- Where the honest research consensus stands on near-term QML advantage on
  classical data.

- **Programming demonstration:** compare quantum and classical models on the same
  dataset with a fair protocol, using the shared benchmark suite.
- **Assignment:** design a fair benchmark protocol and identify how a quantum
  result could be "dequantized."

---

# Part IX - Advanced Topics in Quantum AI

## Focus of Part IX

Advanced and emerging directions, usable selectively in an advanced course.

---

## Chapter 50 - Quantum Data and Learning Quantum Systems

Learning from classical data versus learning from quantum data. Quantum data,
state learning, tomography, measurement-limited learning, classical shadows.
**Now also covers the provable learning separations that genuinely favor quantum
models**: the "power of data" result (classical data can erase a claimed quantum
advantage) and "learning from experiments" (quantum memory gives an exponential
sample advantage). This is where provable quantum learning advantage most
credibly lives. **Also covers learning quantum dynamics**, not just states:
predicting the behavior of arbitrary quantum processes and agnostic process
tomography (PRX Quantum 2025), a learning paradigm distinct from "QML as a
classifier."

- **Programming demonstration:** reconstruct a simple state from simulated
  measurements; estimate properties with classical shadows.
- **Assignment:** estimate a quantum state from samples and discuss when quantum
  data confers a provable advantage.

---

## Chapter 51 - Quantum Natural Language Processing

Quantum NLP as a structured, compositional approach to language.
Compositionality, grammar and meaning, tensor structure, sentence circuits.

- **Programming demonstration:** build a toy compositional representation for
  simple sentences.
- **Assignment:** represent simple sentence structures as circuits or tensor
  diagrams.

---

## Chapter 52 - Quantum Transformers and Attention  **[NEW]**

### Description

How attention and transformer-style architectures, the dominant classical AI
design, are being adapted to quantum circuits. Early and exploratory, framed with
the appropriate skepticism: much of it is small-scale and unproven, and the
classical check is applied hard.

### Focus

- A quick recap of attention as data-dependent weighting.
- Proposed quantum self-attention and quantum-enhanced transformer blocks.
- Where a quantum subroutine could plausibly help, and where it is just
  re-labeling a classical operation.
- Honest status: examples such as hybrid quantum transformers and quantum
  self-attention are mostly small-qubit simulations or *quantum-inspired
  classical* methods, with no demonstrated advantage on real language tasks. The
  chapter is explicit about separating quantum-hardware models from
  quantum-inspired ones, which are easy to conflate.

### Programming Demonstration

Build a toy quantum attention block and compare it with a classical attention
layer on a small task.

### Assignment

Take one proposed quantum-attention scheme and apply the "could a classical
computer do this?" check rigorously, and classify it as quantum-hardware or
quantum-inspired-classical.

---

## Chapter 53 - Quantum Graph Learning

Graph-related quantum AI methods. Graph features, quantum walks, graph kernels,
graph classification, molecules and networks.

- **Programming demonstration:** generate graph features with small
  quantum-inspired constructions.
- **Assignment:** compare classical and quantum-style graph features.

---

## Chapter 54 - Quantum AI for Scientific Machine Learning

Domains where quantum computing may be especially relevant because the systems
are themselves quantum or highly complex. Chemistry, materials, simulation,
scientific ML, VQE as scientific learning. This is where near-term quantum
advantage is most plausible, and the chapter says so plainly.

- **Programming demonstration:** run a small VQE-style scientific example.
- **Assignment:** explain why some scientific domains are more natural candidates
  for quantum advantage than generic classical-data ML.

---

## Chapter 55 - Neural Quantum States: Classical Networks for Quantum Systems  **[NEW]**

### Description

The fast-rising paradigm where a classical neural network represents a quantum
wavefunction. This is the bridge in the other direction, classical deep learning
describing quantum systems, and it matters here for two reasons: it is a major
2024-2026 trend, and it is the strong classical baseline that quantum scientific
ML (Chapter 54) has to beat.

### Focus

- The wavefunction as a function a neural network can output (amplitudes from a
  network).
- **Variational Monte Carlo:** training a neural ansatz to approximate a ground
  state.
- Architectures, from restricted Boltzmann machines and autoregressive models to
  transformer and vision-transformer wavefunctions.
- **Foundation neural quantum states (2025):** a single pretrained model that
  generalizes across many Hamiltonians, "foundation model" thinking entering
  quantum many-body physics.
- Why neural quantum states both compete with and complement quantum hardware,
  and why the classical check is the whole point of the chapter.

### Programming Demonstration

Train a small neural-network wavefunction for a tiny spin system and compare its
ground-state energy with exact diagonalization.

### Assignment

Compare a neural quantum state with a VQE result (Chapter 18 / 54) on the same
small Hamiltonian, and state which is the baseline for which.

---

## Chapter 56 - AI for Quantum Computing

The reverse direction: AI used to improve quantum computing. **The most
demonstrated AI-meets-quantum results live here.** Machine-learned error-
correction decoders (**AlphaQubit**, Nature 2024, and real-time neural decoders),
calibration, noise prediction, circuit design and architecture search, and LLMs
as quantum-programming assistants (the **Qiskit Code Assistant**, agentic circuit
synthesis, and code-generation benchmarks such as Qiskit HumanEval). Privacy-
oriented directions (blind and federated quantum computing) are noted briefly as
a sidebar.

- **Programming demonstration:** train a small model to predict circuit quality
  or noisy output, or to decode a tiny error-correcting code.
- **Assignment:** analyze which circuit features correlate with execution quality,
  and contrast a learned decoder with a classical one.

---

## Chapter 57 - Quantum AI Across Domains: Where It Is Actually Used  **[NEW]**

### Description

A survey of the domains where quantum AI is actually being applied, read through
the book's evaluation-first lens: what has been demonstrated, what is a vendor
claim, and where near-term value is most plausible. It grounds the methods of
Parts VI and VII in real problems and sets up the capstones.

### Focus

- **Chemistry, materials, and drug discovery:** the most credible near-term
  targets, because the problems are quantum-native (links to VQE in Chapter 18,
  scientific ML in Chapter 54, neural quantum states in Chapter 55).
- **Optimization in industry:** logistics, scheduling, routing, and portfolio
  optimization (links to Part VII), compared honestly with strong classical
  heuristics.
- **Finance:** portfolio optimization and the 2025 vendor "quantum value" claims
  (for example HSBC-IBM bond trading and IBM-Vanguard), presented as claims with
  the classical-baseline caveat rather than settled advantage.
- **High-energy physics and scientific computing** (for example the CERN Quantum
  Technology Initiative): event classification, reconstruction, and simulation.
- **The honest pattern:** quantum-native scientific problems are the strongest
  bet; generic classical-data business ML is the weakest, and most industry
  headlines are claims awaiting independent classical baselines.

### Programming Demonstration

Run one small, realistic domain example end to end (for example a tiny molecular
VQE or a portfolio QUBO) with a classical baseline alongside it.

### Assignment

Grade a claimed industry application by strength of evidence (demonstrated on
hardware, simulated, or vendor claim) and identify the missing classical
baseline.

---

# Part X - Capstone Projects

## Focus of Part X

Project-based learning: design, implement, evaluate, and explain complete
quantum AI experiments with honest baselines.

---

## Chapter 58 - How to Build a Quantum ML Experiment

Experimental discipline: research question, dataset, baseline, quantum model,
metrics, ablation, noise analysis, reproducibility. References the companion
repo, the shared benchmark suite, and the dequantization mindset from Chapter 49.

- **Assignment:** write a complete experimental protocol.

---

## Chapter 59 - Capstone 1: Quantum Kernel Classifier

Dataset, classical baselines, quantum feature map, quantum kernel matrix, SVM,
evaluation, report. **Deliverable:** a short paper-style report comparing
classical and quantum kernels.

---

## Chapter 60 - Capstone 2: Variational Quantum Classifier

Data encoding, ansatz design, measurement output, loss, optimizer, training
curves, classical comparison. **Deliverable:** a reproducible notebook and report.

---

## Chapter 61 - Capstone 3: Quantum Generative Model

Target distribution, circuit sampler, training objective, sample evaluation,
visualization, failure analysis. **Deliverable:** a report comparing generated
and target distributions.

---

## Chapter 62 - Capstone 4: Quantum Optimization for AI

Formulate an AI-related optimization problem via QUBO, Ising, QAOA, or a
quantum-inspired solver: feature selection, clustering, scheduling, assignment,
hyperparameters, routing. **Deliverable:** a full optimization experiment with
classical comparison.

---

## Chapter 63 - Capstone 5: Noise-Aware Quantum ML Study  **[NEW]**

### Description

A capstone centered on Part VIII: take one of the earlier models and study how
noise, shots, and device constraints change its behavior, with mitigation
applied and measured.

### Required Components

- a baseline quantum model from an earlier capstone,
- ideal, noisy-simulated, and (optionally) real-hardware runs,
- a mitigation technique with before/after comparison,
- shot-count and depth sensitivity analysis.

### Deliverable

A report on how realistic noise changes the model's conclusions.

---

## Chapter 64 - Final Perspective: What Quantum AI Is Today

A balanced view: what is mature, experimental, overhyped, worth learning now,
and what may matter later, plus how to keep studying.

### Key Message

Quantum AI is an emerging field. Its value depends on careful modeling, honest
baselines, realistic hardware assumptions, and a clear understanding of both
quantum computing and machine learning. The most credible near-term advantage is
likely in quantum-native scientific problems and in learning from quantum data,
not generic classical-data ML.

---

# Back Matter

## Appendix A - Linear Algebra and Probability Reference

The fuller treatment behind Chapter 0: vector spaces, inner products, unitary and
Hermitian operators, spectral decomposition, tensor products, and the probability
results the book uses, with worked proofs and a quick-reference summary.

## Appendix B - Notation, Symbols, and Dirac Notation Reference

A complete table of symbols and conventions used in the book, with Dirac notation
explained alongside the equivalent vector/matrix forms.

## Appendix C - Environment Setup and the Companion Repository  **[NEW]**

How to set up a reproducible environment: pinned versions (Python, NumPy,
Matplotlib, scikit-learn, PennyLane, Qiskit 2.x and its split packages, a
tensor-network library), random-seed conventions, how to run on real hardware
(IBM Quantum, Amazon Braket), and how the companion repository is organized.
Every code listing maps to a runnable notebook here. Notes the Qiskit 1.0/2.0 API
break and why TensorFlow Quantum is not used.

## Appendix D - Solutions and Instructor Resources  **[NEW]**

Solution sketches for representative assignments of each type, suggested grading
rubrics, the chapter-dependency graph in full, and pointers to slides and
problem sets in the companion repository.

## Glossary

Plain-language definitions of every key term, cross-referenced to the chapter
that introduces it.

## Bibliography and Further Reading

A consolidated bibliography, plus a short, curated **further-reading list at the
end of each chapter** (the "Research Note" boxes point here).

## Index

---

# 12. Suggested Chapter Template

Each chapter follows a consistent template. It enacts the pedagogical framework
(section 3): intuition and illustration first, then full formalism, then code,
then active practice, with objectives at the top and self-checks woven through.

```text
0.  Learning objectives ("after this you will be able to ...")
1.  The idea in one sentence
2.  Why this matters for AI/ML
3.  Plain-language intuition and mental model
4.  Analogy (with a note on where it breaks down)
5.  Diagram and fun illustration
6.  Tiny worked example
7.  Formal definition and equations (full depth, nothing hand-waved)
8.  From-scratch Python implementation
9.  Library implementation
10. "Can a classical computer do this?" check
11. Common misconceptions (misconception-first for threshold concepts)
12. Exercises (worked -> faded -> independent)
13. Further reading
14. Forward link to later chapters

Woven through, not numbered:
 -  Mid-chapter self-checks with revealed answers (formative feedback)
 -  Occasional "explain it back in your own words" metacognition prompts
```

---

# 13. Assignment Design

Four types, as in v1, with a fifth integrative thread through the capstones.

- **Type 1 - Conceptual:** explain superposition versus parallelism; why
  measurement needs shots; entanglement versus correlation; why data loading is
  hard; why advantage needs strong baselines; how a result could be dequantized;
  why expressivity is not automatically good.
- **Type 2 - Mathematical:** normalize a state; compute measurement
  probabilities; apply gates and rotation gates; compute tensor products and
  partial traces; test entanglement; compute expectation values; build a kernel
  matrix; compute the bond dimension of a small state.
- **Type 3 - Programming:** one- and two-qubit simulators; measurement
  simulation; Bell states; Grover; quantum-kernel classifier; variational
  classifier; MPS classifier; quantum reservoir readout; quantum generative
  model; noisy circuits; gradient-variance study.
- **Type 4 - Research-style:** design a fair benchmark; compare quantum and
  classical models; study feature-map depth, ansatz depth, shot count, noise
  sensitivity, and the generalization gap; write a paper-style report.

Every assignment has a solution sketch in Appendix D / the companion repo.

---

# 14. Illustration Plan by Part

Per-part illustration targets, with additions:

- **Chapter 0 / Appendix A:** complex-plane and tensor-product diagrams.
- **Part I:** bit-versus-qubit, state-vector, measurement histograms, gate
  transformations, **Bloch sphere and rotation arcs**, circuit diagrams.
- **Part II:** superposition, interference and **phase-kickback** diagrams,
  tensor-product growth, **multi-qubit/controlled-gate** diagrams, entanglement,
  no-cloning.
- **Part III:** algorithm-flow, oracle, Grover amplification, QFT phase, **HHL
  assumptions and QRAM**, VQE hybrid-loop diagrams.
- **Part IV:** ML pipeline, feature-space, kernel-matrix heatmaps, NN training,
  sampling.
- **Part V:** data-encoding, feature-map circuits, **encoding-cost**,
  measurement-as-feature diagrams.
- **Part VI:** quantum-kernel pipeline and **kernel concentration**, variational
  circuits, **kernel/variational equivalence**, QNN architecture, gradient-flow,
  barren-plateau plots, **Fourier-spectrum / generalization** plots,
  **equivariant-circuit** diagrams, **tensor-network** diagrams, **reservoir**
  schematic, generative sampling (Born and Boltzmann).
- **Part VII:** QAOA layers, QUBO mapping, energy landscapes, optimization
  pipelines.
- **Part VIII:** **density-matrix/noise-channel** diagrams, ideal-versus-noisy,
  **logical-qubit/surface-code** intuition, **hardware-platform comparison**,
  scaling plots, **BQP / complexity** schematic, benchmark comparison,
  **dequantization** schematic.
- **Part IX:** quantum-data and **power-of-data** diagrams, quantum-NLP
  compositional, **quantum-attention** block, graph-learning, AI-for-quantum
  feedback-loop diagrams.
- **Part X:** capstone architecture, experimental workflow, report templates.

---

# 15. Suggested 14-Week Basic Quantum Computing Course

| Week | Topic | Chapters |
|---|---|---|
| 0 | Math onramp (optional, self-paced) | 0 |
| 1 | Quantum computing without physics; qubits | 1-2 |
| 2 | Measurement; gates | 3-4 |
| 3 | Bloch sphere, rotation gates; circuits | 5-6 |
| 4 | Superposition and interference | 7-8 |
| 5 | Multi-qubit systems, tensor products, multi-qubit gates | 9 |
| 6 | Entanglement; reversibility and no-cloning | 10-11 |
| 7 | Algorithm design; Deutsch-Jozsa | 12-13 |
| 8 | Grover; QFT and phase estimation | 14-15 |
| 9 | HHL and quantum linear algebra | 16 |
| 10 | Hamiltonians; VQE | 17-18 |
| 11 | Density matrices, noise, simulators | 43-45 |
| 12 | Error correction; 2026 hardware | 46-47 |
| 13 | Scaling, limits, and advantage | 48-49 |
| 14 | Project presentations | selected |

---

# 16. Suggested 14-Week Advanced Quantum AI / ML Course

| Week | Topic | Chapters |
|---|---|---|
| 1 | Quantum review for ML (incl. rotation gates) | 1-11 review |
| 2 | Classical ML refresher and baselines | 19-22 |
| 3 | Data encoding and its cost (incl. QRAM) | 23 |
| 4 | Quantum feature maps; measurement as features | 24-25 |
| 5 | Quantum kernels and concentration | 26 |
| 6 | Variational circuits; kernels-equal-variational | 27-28 |
| 7 | Quantum neural networks; gradients | 29-30 |
| 8 | Barren plateaus; expressivity and generalization | 31-32 |
| 9 | Structured, equivariant, and tensor-network models | 33-35 |
| 10 | Reservoir computing; generative and RL models | 36-38 |
| 11 | Quantum optimization for AI | 39-42 |
| 12 | Noise, density matrices, hardware | 43-47 |
| 13 | Scaling, advantage, dequantization; advanced topics and applications | 48-57 |
| 14 | Capstone presentations | 58-64 |

---

# 17. Suggested Full-Year Course

## Semester 1 - Quantum Computing Foundations

Chapter 0, Part I, Part II, Part III, and Part VIII (Chapters 43-49).

## Semester 2 - Quantum AI and Machine Learning

Part IV, Part V, Part VI, Part VII, Part IX, and Part X.

---

# 18. Book-Level Capstone Outcomes

A student completing the full book should be able to produce:

1. **Quantum kernel classifier** with honest RBF/polynomial comparison.
2. **Variational quantum classifier** compared with a neural network.
3. **Quantum generative sampler** approximating a target distribution.
4. **Quantum optimization for feature selection** via QUBO with classical
   comparison.
5. **Noise-aware quantum ML study** with mitigation measured.
6. **Barren-plateau and expressivity analysis** of gradient behavior and the
   generalization gap versus depth, with the simulability tradeoff discussed.
7. **Tensor-network or quantum-reservoir prototype** that probes the boundary
   between classically tractable and genuinely quantum models.
8. **A dequantization-aware benchmark** that states explicitly how a claimed
   quantum result could be matched classically.

---

# 19. Writing Style Requirements

The book should use plain English, short paragraphs, step-by-step derivations,
visual explanation, many small examples, minimal unexplained notation, formal
definitions after intuition, frequent summaries, misconception boxes, code-first
demonstrations, and assignment-driven learning.

Tone: formal, precise, calm, pedagogical, intuitive, not sensational, skeptical
of hype.

Avoid: exaggerated claims, "quantum magic" language, unnecessary physics
history, unexplained notation, long derivations without intuition, assuming a
quantum background, and treating quantum ML as automatically superior to
classical ML.

House-style mechanics: **no em-dashes or double-hyphens** (use commas, colons,
parentheses, or separate sentences).

---

# 20. Recurring Boxes and Pedagogical Devices

- **Intuition Box** - plain-language explanation.
- **Formal Box** - the mathematical definition.
- **AI/ML Connection Box** - how the concept appears in machine learning.
- **Misconception Box** - a common misunderstanding and its correction.
- **Code Box** - a minimal executable Python example.
- **Diagram Box** - a visual explanation, allowed to be fun.
- **Classical Check Box** - "could a classical computer do this?",
  the running skepticism device.
- **Research Note** - how the idea appears in current research, with a pointer to
  the chapter's further-reading list.
- **Practical Warning** - limitations, noise, scaling, or evaluation issues.
- **Forward Link** - where the concept returns later.

---

# 21. Final Book Identity

**Understanding Quantum AI** should be a bridge textbook: not only a quantum
computing book, not only a quantum machine-learning book, not only a popular
explanation, and not only a mathematical reference.

It should be:

> A complete, visual, programmable, plain-language, graduate-level path from the
> rules of quantum computing to quantum AI and quantum machine learning, with an
> evaluation-first conscience.

It should help the reader move from:

```text
What mathematics do I actually need?
        v
What is a qubit?
        v
How do quantum gates and rotations transform it?
        v
How do quantum circuits and algorithms compute?
        v
How can quantum circuits represent data, and at what cost?
        v
How can quantum circuits become trainable models?
        v
What can those models actually learn, and could they be dequantized?
        v
What is realistic Quantum AI today, and where is it actually headed?
```

---

# 22. Summary of Changes

## From v1 to v2

- **Added Chapter 0** (mathematical onramp) and full **front matter** (preface,
  diagnostic self-test, notation guide, dependency graph).
- **Added Chapter 5** (Bloch sphere and rotation gates) so parameterized gates
  are taught before they are used.
- **Folded multi-qubit gates** into the tensor-product chapter (Ch 9).
- **Added Chapter 16** (HHL / quantum linear algebra) and a **Shor-in-brief**
  section in the QFT chapter.
- **Added the kernel/variational equivalence chapter** (Ch 28).
- **Added density matrices, error correction, and a 2026 hardware chapter.**
- **Strengthened the advantage chapter** with dequantization and
  classical-surrogate results, linked to the barren-plateau chapter.
- **Made the data-loading cost** and **encoding-induced kernel** points explicit.
- **Added Capstone 5** (noise-aware study).
- **Added Appendices A-D**, a **glossary**, a **per-chapter and consolidated
  bibliography**, and an **index**.
- **Updated tooling**: PennyLane as the primary spine, **Qiskit 2.x** with its
  split packages, dropped **TensorFlow Quantum** as legacy.
- **Added a "Classical Check" device** to the chapter template.
- **Rebuilt the pedagogy** (section 3) into an explicit framework: the central
  accessible-AND-rigorous commitment, the seven forms (including intuition/mental
  model and fun illustration), depth-and-coverage guardrails, cognitive-load
  sequencing, and learning-design mechanics (per-chapter objectives, formative
  self-checks, worked-example fading, misconception-first and threshold-concept
  scaffolding, retrieval/spacing, metacognition, differentiated paths).

## From v2 to v2.1 (closing the coverage gaps)

Five new chapters (the book grows to 62 numbered chapters), plus five in-place
additions, plus a stated scope-boundaries note.

- **New Chapter 32 - Expressivity and Generalization:** the learning-theory
  pillar (parameterized circuits as truncated Fourier series, generalization and
  sample complexity) that complements barren plateaus.
- **New Chapter 34 - Geometric and Equivariant QML:** symmetry-aware ansatze, the
  quantum analog of geometric deep learning.
- **New Chapter 35 - Tensor Networks:** the classical/quantum bridge that explains
  simulability and dequantization, and a model class (MPS) in its own right.
- **New Chapter 36 - Quantum Reservoir Computing:** a training-light model class
  that sidesteps barren plateaus.
- **New Chapter 52 - Quantum Transformers and Attention:** the dominant classical
  architecture meeting QML, framed skeptically.
- **Added to Ch 23:** QRAM and the data-loading feasibility debate.
- **Added to Ch 26:** exponential concentration of quantum kernels (the kernel
  analog of barren plateaus).
- **Added to Ch 37:** quantum Boltzmann machines alongside Born machines.
- **Added to Ch 49:** complexity classes (BQP) and what is actually believed
  about quantum speedups.
- **Added to Ch 50:** the "power of data" result and provable learning
  separations (learning from quantum experiments).
- **Added section 11.1 - Deliberate scope boundaries:** continuous-variable /
  photonic QML, quantum privacy / federated / blind QML, and cryptographic impact
  are named as intentional sidebars, so "comprehensive" stays honest.
- **Renumbered** all chapters after each insertion; updated both course tables,
  the full-year course, the illustration plan, the bridge table, and the core
  promise accordingly.

## From v2.1 to v2.2 (live 2025-2026 web scout)

One new chapter (the book grows to 63 numbered chapters), several in-place
strengthenings, and tooling corrections, all driven by a web scout of 2024-2026
sources.

- **New Chapter 55 - Neural Quantum States:** classical neural networks
  representing quantum wavefunctions (variational Monte Carlo, transformer
  wavefunctions, 2025 "foundation" neural quantum states); framed as the strong
  classical baseline for quantum scientific ML. AI-for-Quantum moves to Ch 56 and
  Part X to Chapters 57-63.
- **Strengthened Ch 56 (AI for Quantum):** named neural QEC decoders (AlphaQubit)
  and real-time decoding, the Qiskit Code Assistant, agentic circuit synthesis,
  and code benchmarks, the most demonstrated AI-meets-quantum results.
- **Strengthened Ch 46 (error correction):** concrete 2024-2026 milestones,
  below-threshold codes (Willow), the 10^-3 versus 10^-6 gap, error-detected vs
  error-corrected qubits, surface vs qLDPC vs cat/bosonic codes, and
  magic-state distillation / T-gates as the bottleneck.
- **Strengthened Ch 47 (hardware):** five live modalities with concrete examples
  (incl. foundry-made silicon qubits), vendor fault-tolerance roadmaps clustering
  at 2029-2030, and the warning that qubit count is a poor figure of merit.
- **Strengthened Ch 49 (advantage):** added the standard honest-benchmarking
  suite (Bowles-Ahmed-Schuld), the "sampling advantage is real but is not ML and
  the benchmark can be spoofed" point, and the representability frontier.
- **Strengthened Ch 33 (QCNN):** QCNNs being barren-plateau-free also makes them
  effectively classically simulable (PRX Quantum 2025).
- **Strengthened Ch 37 (generative):** the 68-qubit generative-advantage claim
  and classical-surrogation conditions.
- **Strengthened Ch 50 (quantum data):** learning quantum dynamics and agnostic
  process tomography.
- **Strengthened Ch 52 (transformers):** explicit separation of quantum-hardware
  models from quantum-inspired-classical ones.
- **Corrected the tooling stack (section 9, Appendix C):** Qiskit 2.x,
  PennyLane 0.45 plus the 2026 v2 API change, **CUDA-Q elevated** to a
  recommended framework (NVQLink / real-time GPU-QPU), quimb + cotengra for
  tensor networks, Braket on Qiskit 2.0, and **TensorFlow Quantum corrected to
  maintained-but-legacy** (not dead) rather than unmaintained.

## From v2.2 to v2.3 (coverage assurance)

- **New Chapter 57 - Quantum AI Across Domains:** a cross-domain applications
  survey (chemistry, materials, drug discovery, finance, high-energy physics,
  industrial optimization) read through the claim-versus-proven lens. Closes the
  last content gap from the scout and sets up the capstones. Part X moves to
  Chapters 58-64; the book is now 64 numbered chapters.
- **Added section 23 - Topic Coverage Map:** an explicit audit tracing every
  major topic, and every 2025-2026 trend surfaced by the web scout, to the
  chapter that covers it, so nothing is left behind.

---

# 23. Topic Coverage Map (audit)

This matrix exists so coverage is auditable: every major area, and every recent
trend from the 2025-2026 web scout, maps to a concrete home.

## By theme

| Theme | Chapters |
|---|---|
| Mathematical onramp and notation | 0, Appendices A-B |
| Rules of quantum computing (qubits, measurement, gates, Bloch/rotations, circuits) | 1-6 |
| Core phenomena (superposition, interference, tensor products, multi-qubit gates, entanglement, no-cloning) | 7-11 |
| Algorithms (design pattern, Deutsch-Jozsa, Grover, QFT/phase estimation/Shor, HHL/quantum linear algebra, Hamiltonians, VQE) | 12-18 |
| Classical ML refresher | 19-22 |
| Data encoding, feature maps, QRAM, measurement-as-features | 23-25 |
| QML models | 26-38 |
| Quantum optimization for AI | 39-42 |
| Reality check: density matrices, simulators, noise, error correction, hardware, scaling, advantage | 43-49 |
| Advanced topics and applications | 50-57 |
| Capstones and final perspective | 58-64 |

## By 2025-2026 trend (scout traceability)

| Recent trend | Home chapter(s) |
|---|---|
| Expressivity as a truncated Fourier series; generalization bounds | 32 |
| Barren plateaus, and "no barren plateaus implies classical simulability" | 31, 49 |
| Exponential concentration of quantum kernels | 26 |
| Classical surrogates and dequantization | 35, 49 |
| Tensor networks (MPS, bond dimension) as model and simulation | 35, 48 |
| Geometric / equivariant QML | 34 |
| QCNNs effectively classically simulable | 33 |
| Quantum reservoir computing | 36 |
| Generative quantum advantage (68-qubit, barren-plateau-free) | 37, 49 |
| Quantum Boltzmann machines | 37 |
| Power of data; provable learning separations; learning from experiments | 50 |
| Learning quantum dynamics; agnostic process tomography; classical shadows | 50 |
| Neural quantum states; foundation NQS | 55 |
| Quantum transformers / attention (and quantum-inspired vs quantum-hardware) | 52 |
| Neural QEC decoders (AlphaQubit); real-time decoding | 46, 56 |
| LLMs for quantum coding; agentic circuit synthesis | 56 |
| Below-threshold codes; logical qubits; qLDPC, surface, cat/bosonic codes; magic-state distillation | 46 |
| 2026 hardware landscape; five modalities; fault-tolerance roadmaps | 47 |
| Honest benchmarking suite; sampling-advantage caveats; representability frontier | 49 |
| Complexity classes (BQP) | 49 |
| Application domains (chemistry, finance, HEP, drug discovery) | 54, 57 |
| Tooling: Qiskit 2.x, PennyLane 0.45, CUDA-Q, quimb/cotengra, TFQ status | 9, Appendix C |

## Deliberately sidebarred (not full chapters)

Continuous-variable / photonic QML, quantum privacy / federated / blind QML, and
cryptographic impact (Shor / post-quantum security), per section 11.1.
```
