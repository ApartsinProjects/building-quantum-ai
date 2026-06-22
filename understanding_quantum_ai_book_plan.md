# Building Quantum AI
## Complete Book Plan, Description, Focus, and Table of Contents (v2.5)

> Version 2.5 of the plan. Earlier versions are preserved under `archive/`
> (`...v1.20260616.md`, `...v2.3.20260622.md`).
> v2.5 rebands the book into the **Hands-On AI Science** series ("Building Quantum
> AI: From Qubits to Quantum Machine Learning"), adds cover-page and ToC HTML
> matching series house style, integrates 2024-2026 research findings (Lie-algebra
> barren-plateau theory, Microsoft Majorana 1 topological qubits, Quantinuum Helios
> 48-logical-qubit milestone, IBM bivariate-bicycle qLDPC, entanglement-induced
> learning advantage, robust dequantization, ICLR 2025 generalization bounds,
> AlphaQubit 2, Qiskit 2.3 C++ transpiler, drug-discovery as leading application
> domain), and creates the GitHub repository at ApartsinProjects. See section 22.
> v2.4 turns the book into a deep scientific AND software-grade reference: a new
> Part X ("Quantum AI Software, Hardware Access, and Research Practice") with
> chapters on the development environment and AI-assisted ("vibe") coding,
> compilation and real-hardware access, performance / GPU / differentiable
> quantum programming, and datasets-benchmarks-statistics; recurring Recipe,
> AI-Copilot, and Research-Frontier boxes woven through every part; a
> reproduce-a-result capstone built with an AI copilot; and new appendices (a
> Cookbook and a Reproduce-the-Paper index + research-practice checklist). See
> section 22 for the full list. The book now has Chapter 0 plus 69 numbered
> chapters.
> v2 added a mathematical onramp, the parameterized-gate machinery that all of
> quantum machine learning depends on, a stronger intellectual-honesty track
> (dequantization, classical surrogates, the barren-plateau / simulability link),
> error correction, a 2026 hardware reality chapter, complete front and back
> matter, and a version-pinned companion code base.
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

## Series

**Hands-On AI Science** (apartsin.com) &#183; Volume 5

Other books: Building Language AI (llmbook.apartsin.com) &#183; Building Vision AI
(visionbook.apartsin.com) &#183; Building Temporal AI (temporalbook.apartsin.com) &#183;
Building Scalable AI (scalablebook.apartsin.com)

## Title

**Building Quantum AI: From Qubits to Quantum Machine Learning**

The title follows the series pattern ("Building [Domain] AI: From [X] to [Y]").
It signals the build-it-yourself ethos of Hands-On AI Science, the beginner-
friendly quantum-computing foundation, and the advanced machine-learning
destination. Domain URL: **quantum.apartsin.com**.

---

# 1. Book Vision

**Building Quantum AI** is a formal but plain-language textbook that
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
- design small quantum AI experiments using Python libraries and simulators,
- **engineer quantum software to a research standard**: reproducible pinned
  environments, automated tests for quantum code, continuous integration for
  notebooks, and experiment tracking,
- **work with an AI coding copilot** to scaffold, translate, and debug quantum
  code, while verifying everything it produces against the rules of the model,
- **compile, transpile, and run circuits on real hardware** (IBM Quantum, Amazon
  Braket, IonQ/Quantinuum), estimate resources and cost, and apply an error-
  mitigation toolkit,
- **scale experiments** with GPU-accelerated and JIT-compiled simulation,
  differentiable programming, and circuit cutting,
- **report results with honest statistics**: shot-noise error bars, bootstrap
  confidence intervals, and tests for whether a claimed advantage is real,
- **reproduce a published quantum-ML result** end to end and state precisely how
  it could be dequantized or classically surrogated.

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

## 3.7 Software is a first-class spine, not an appendix

The book serves two doers as much as two learners: the **researcher** who must
produce reproducible, publishable results, and the **practitioner** who must ship
working quantum code. Three threads run continuously from the front matter to the
capstones so that "understand it" and "build it correctly" are never separated:

- **The recipe thread.** A recurring **Recipe Box** gives copy-paste,
  parameterized, problem-first code (encode a tabular dataset, estimate a Pauli
  expectation with calibrated shots, diagnose a barren plateau, align ideal /
  noisy / hardware runs). Recipes are consolidated in Appendix E (the Cookbook)
  so the book is usable as a daily reference, not only a read-through.
- **The AI-copilot ("vibe coding") thread.** A recurring **Build-With-AI Box**
  teaches the reader to use an LLM copilot to scaffold circuits, translate between
  SDKs, propose ansatze, and explain errors, **and then to verify everything it
  produces** with the book's classical-check and testing discipline. The standing
  warning: copilots routinely emit deprecated Qiskit 0.x/1.x APIs and hallucinate
  gate signatures, so generated quantum code is a draft to be checked, never an
  answer to be trusted. This thread is introduced in the front matter, exercised
  per part, and made the subject of a capstone.
- **The research-frontier thread.** A recurring **Research Frontier Box** in the
  advanced chapters names the two or three genuinely open questions, so a graduate
  student can find a thesis-scale problem and a practitioner can see where the
  field is still unsettled.

Engineering rigor (reproducible environments, automated tests for quantum code,
continuous integration for every listing, experiment tracking, honest statistics)
is taught explicitly in Part X and enacted everywhere: every code listing maps to
a tested, version-pinned notebook in the companion repository.

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

**Building Quantum AI** aims for accessible explanation, formal definition,
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

Programming is a way to understand ideas, not only to implement them, and also a
deliverable in its own right. The path moves through five stages, with software
engineering and AI-assisted coding treated as skills the reader actively builds.

- **Stage 0 - A reproducible, tested workspace.** A pinned environment
  (`uv`/`conda` lockfile, a ready container, one-click Colab/Codespaces), seed
  conventions, automated tests for quantum code (assert unitarity and
  normalization, statevector golden tests, property-based testing), and
  continuous integration that runs every notebook. Purpose: make results
  reproducible and code trustworthy from the first listing. Taught in Chapter 58.
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
  evaluation, ablation, noise analysis, report, with experiment tracking and
  honest statistics. Purpose: turn quantum AI into disciplined experimental
  research.

Running across all five stages is the **AI-copilot discipline**: the reader is
shown how to have an LLM scaffold, translate, and debug quantum code, and then
how to verify it (run the tests, check the math, reject deprecated APIs). The
copilot accelerates the typing; the reader still owns the correctness.

Every code listing in the book corresponds to a runnable, version-pinned, and
**tested** notebook in the companion repository (see Appendix C), and common
patterns are lifted into the Cookbook (Appendix E).

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

## Software-engineering and research-practice tooling (Part X)

The book treats these as part of the stack, not an afterthought:

- **Environments and packaging:** `uv` or `conda` with a committed lockfile, plus
  a ready Docker image and Colab/Codespaces config for one-click runs.
- **Testing and CI:** `pytest` and `Hypothesis` (property-based tests for
  unitarity/normalization), `nbmake`/`papermill` to execute notebooks in CI, so
  "every listing runs" is enforced rather than promised.
- **Differentiation and acceleration:** `JAX`, **PennyLane Catalyst**
  (`qml.qjit`), `lightning.gpu`, and CUDA-Q for JIT-compiled and GPU-accelerated
  circuits and gradients.
- **Error mitigation:** **Mitiq** and the mitigation built into Qiskit primitives.
- **Scaling utilities:** Qiskit circuit-cutting / knitting addons; `quimb` +
  `cotengra` for tensor-network simulation (also listed above).
- **Experiment tracking and config:** `MLflow` or `Weights & Biases`, with
  `Hydra` or simple typed config for reproducible sweeps and seed control.
- **Resource estimation and IR:** the Azure Quantum Resource Estimator;
  OpenQASM 3 and QIR as interchange formats; the Qiskit primitives
  (Sampler/Estimator) execution model.

These are introduced concretely in Part X and pinned in Appendix C.

## Version and maintenance note

Targets are pinned in Appendix C and reflect a 2026 snapshot:
- **Qiskit 2.x** (v2.3+ line). Qiskit 1.0/2.0 removed the pre-1.0 API
  (`execute`, `Opflow`, `QuantumInstance`) and split `aer`, `algorithms`, and
  `machine-learning` into separate packages. **Qiskit 2.3 introduced a C++
  transpiler backend** delivering HPC-accelerated transpilation and, via primitives,
  built-in error mitigation. Code must not use 0.x/1.x APIs.
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

Parts IV-VII, Part IX, Part X (software and research practice), and Part XI
(capstones), with Parts I-III as a review/onramp.
Outcome: students implement, evaluate, and critically analyze quantum ML models
and quantum AI pipelines, with reproducible code and honest statistics.

## Integrated Full-Year Course

Semester 1: quantum-computing foundations and algorithms (Parts I-III, VIII).
Semester 2: quantum AI and machine learning (Parts IV-VII, IX), software and
research practice (Part X), and capstones (Part XI).

A **chapter-dependency graph** in the front matter shows prerequisites so
self-learners and instructors can chart a path.

---

# 11. Complete Book Structure

The book has a Foundations onramp, eleven parts, and six appendices.

```text
Front Matter   Preface, how to read, diagnostic self-test, notation guide,
               dependency graph, "running the code and coding with a copilot"
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
Part X         Quantum AI Software, Hardware Access, and Research Practice
Part XI        Capstone Projects
Back Matter    Appendices A-F, glossary, bibliography, index
```

Chapter numbering note: the book has Chapter 0 plus **69 numbered chapters**.
New chapters relative to v1 are flagged **[NEW]**; the rest are revised. Part X
(software and research practice) and one new capstone are the v2.4 additions;
they sit before and within the capstone block so every cross-reference in
Parts I-IX is unchanged. Section 23 (Topic Coverage Map) traces every major topic
to its chapter.

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
- **Running the code, and coding with a copilot** - a two-page on-ramp: how to
  open the companion notebooks (one-click Colab/Codespaces or a local pinned
  environment), and a first look at the AI-copilot workflow and its verification
  discipline that recurs as **Build-With-AI Boxes** throughout. Points to Chapter
  58 and Appendix C for the full treatment.
- **About the Hands-On AI Science Series** - how this volume fits in the series,
  and brief descriptions of the other books (Building Language AI, Building Vision
  AI, Building Temporal AI, Building Scalable AI). Mirrors F8 in every series
  volume.

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

**v2.5 additions:**
- **Lie-algebraic barren-plateau theory (2024, Nature Communications):** the
  Dynamical Lie Algebra (DLA) of a parameterized circuit now predicts, from the
  circuit structure alone, whether barren plateaus exist, replacing empirical
  gradient-variance heuristics with a rigorous algebraic criterion. The DLA is
  the set of all operators generatable by the circuit's generators; when it is
  exponentially large, barren plateaus are guaranteed.
- **Phase-of-matter link (2025):** certain phases of the loss landscape in
  analog VQAs correspond to known phases of matter, providing a statistical-
  mechanics lens on trainability.
- A **Research Frontier Box**: open questions include whether the DLA criterion
  has a computationally efficient test for practical circuit sizes, and whether
  the simulability implication has an exception for structured non-Clifford
  circuits.

- **Programming demonstration:** measure gradient variance for circuits of
  different depth; compute the DLA dimension for a small circuit and relate it to
  the observed gradient variance.
- **Assignment:** design a shallower or more structured ansatz and compare
  trainability; check whether the DLA shrinks and discuss the simulability
  tradeoff.

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

**v2.5 addition:** An **ICLR 2025 generalization-bounds result** derives tight
sample-complexity bounds comparing quantum kernel machines and QNNs to classical
random Fourier feature (RFF) models on the same data distribution. The main
finding: quantum models do not generalize better than RFF baselines on generic
classical data; an advantage requires the data distribution itself to have quantum
structure. This is the rigorous version of the "power of data" argument and lands
here as the quantitative capstone of the expressivity-vs-generalization section.

### Diagrams

- Fourier-spectrum plots that widen as encoding repetitions increase.
- A train-versus-test error curve against model expressivity.
- A sample-complexity comparison table: quantum kernel / QNN vs classical RFF.

### Programming Demonstration

Fit a one-dimensional function with a variational model; show the accessible
Fourier spectrum changing with encoding repetitions; plot the generalization gap;
compare sample complexity against an RFF baseline on the same dataset.

### Assignment

Vary encoding richness, measure the accessible frequencies, relate them to the
train/test gap, and compute the RFF sample complexity needed to match the
quantum model's expressivity.

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
  **cat / bosonic codes** (AWS Ocelot). **New (v2.5): IBM bivariate bicycle
  (BB) qLDPC codes** (Nature, 2024) encode 12 logical qubits in 144 data and 12
  ancilla physical qubits, a factor-of-10 overhead reduction vs surface codes,
  with logical error rates below 10^-4 at code distance 12.
- **Quantinuum Helios milestone (2024-2025, with Microsoft):** 48 logical qubits
  from 98 physical (color code), demonstrating logical-level entanglement with
  99.9%+ fidelity, currently the highest-fidelity logical-qubit demonstration.
- **Magic-state distillation and T-gates** as the real remaining bottleneck:
  error correction gives Clifford gates almost for free, but universality needs
  distilled magic states. First logical-level demos appeared in 2025.
- **Machine-learned decoders** (AlphaQubit and real-time neural decoders) as the
  link to Chapter 56. **New (v2.5): AlphaQubit 2** achieves near-optimal logical
  error rates for both surface and color codes at scale, and runs orders of
  magnitude faster than competing high-accuracy classical decoders, enabling the
  microsecond-latency real-time decoding that fault-tolerant hardware requires.
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

- **Six live modalities**, each with a different error profile:
  superconducting (fast gates, finite coherence; Google Willow 105 qubits,
  IBM Heron), trapped-ion (highest fidelities, slower, all-to-all; Quantinuum
  Helios 48 logical qubits, IonQ), neutral-atom (reconfigurable, atom shuttling;
  QuEra, Pasqal, Atom Computing), photonic (room-temperature, manufacturable,
  loss-dominated; PsiQuantum, also the home of continuous-variable computing, a
  sidebar), silicon-spin (CMOS-manufacturable; Diraq/imec crossed the error-
  correction fidelity threshold in foundry-made qubits, Nature 2025), and
  **topological / topoconductor (v2.5 new): Microsoft Majorana 1 (Feb 2025)**,
  the first processor powered by topological qubits; 8-qubit Topological Core
  built from InAs/Al topoconductor nanowires hosting Majorana zero modes; roadmap
  to 1 million+ physical qubits with intrinsically lower error rates. Carries a
  "first demonstration, not yet a working computer" caveat, but represents a
  qualitatively different noise model from all other modalities and deserves
  explicit placement in any 2025/2026 hardware map.
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
- **v2.5 new: entanglement-induced quantum learning advantage (npj Quantum
  Information, 2025):** a noise-robust, unconditional proof of quantum advantage
  in expressivity and training efficiency for specific entanglement-dependent
  model classes. This is placed here as the strongest current positive result:
  it is real and unconditional, but it applies only where the data distribution
  has the required entanglement structure, exactly the "quantum-native data"
  regime that Chapter 50 identifies as the strongest near-term bet.
- **v2.5 new: robust dequantization (Springer, 2024):** extends classical
  dequantization to the sample-and-query model with constant additive error,
  recovering classical algorithms that match quantum ML speedups for a broader
  class of input access assumptions. Read alongside the 2025 advantage result,
  these two define the current boundary: advantage requires both structured
  data and quantum-native access; generic classical-data ML is dequantizable.
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
correction decoders (**AlphaQubit** Nature 2024 and **AlphaQubit 2** 2025, near-
optimal and orders of magnitude faster than classical high-accuracy decoders, now
meeting the microsecond real-time latency for fault-tolerant hardware), calibration,
noise prediction, circuit design and architecture search, and LLMs as quantum-
programming assistants (the **Qiskit Code Assistant**, agentic circuit synthesis,
and code-generation benchmarks such as Qiskit HumanEval). Privacy-oriented
directions (blind and federated quantum computing) are noted briefly as a sidebar.

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
  targets, because the problems are quantum-native, and **the fastest-growing
  quantum AI application domain** by market projection ($638M by 2035). Concrete
  applications: QSAR (structure-activity prediction), quantum VAEs for molecular
  generation, virtual screening, and DFT acceleration. Links to VQE in Chapter 18,
  scientific ML in Chapter 54, and neural quantum states in Chapter 55.
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

# Part X - Quantum AI Software, Hardware Access, and Research Practice  **[NEW]**

## Focus of Part X

The engineering and research-practice spine the rest of the book leans on,
gathered into one place so it can be taught deliberately: a reproducible, tested
development environment and AI-assisted coding; compiling and running on real
hardware; performance, GPU acceleration, and differentiable quantum programming;
and datasets, benchmarks, and the statistics that make a result trustworthy. This
part serves the researcher (reproducibility, honest statistics, paper-grade
artifacts) and the practitioner (shipping working code, hardware access, cost)
equally, and every chapter is recipe-driven.

---

## Chapter 58 - The Quantum AI Development Environment and AI-Assisted Coding  **[NEW]**

### Description

How to set up a workspace where quantum code is reproducible and trustworthy, and
how to use an AI copilot as a force multiplier without surrendering correctness.
This is the home of the **Build-With-AI ("vibe coding")** thread that recurs
throughout the book.

### Focus

- Reproducible environments: `uv`/`conda` lockfiles, a ready container,
  one-click Colab/Codespaces, and seed conventions.
- An SDK decision map: when to reach for PennyLane, Qiskit, CUDA-Q, Cirq, or
  `quimb`, as a practical table.
- **Testing quantum code:** asserting unitarity and normalization, statevector
  golden tests, property-based testing with Hypothesis, and sensible tolerances.
- **Continuous integration for notebooks** (`nbmake`/`papermill`) so every
  listing is executed on every change.
- **Coding with an AI copilot:** prompting patterns to scaffold circuits,
  translate between SDKs, propose ansatze, and explain errors; and the
  verification discipline that follows, including the standing warning that
  copilots emit deprecated Qiskit 0.x/1.x APIs and hallucinate gate signatures.

### Programming Demonstration

Bootstrap the companion environment; write and run a property-based test that a
generated gate is unitary; use a copilot to translate a PennyLane circuit to
Qiskit 2.x and verify equivalence by statevector comparison.

### Assignment

Take an AI-generated quantum snippet, find its bug or deprecated API with a test,
and correct it; document the prompt, the failure, and the fix.

---

## Chapter 59 - Compiling, Transpiling, and Running on Real Hardware  **[NEW]**

### Description

The path from a circuit that works in simulation to one that runs on a device,
and the practical realities (depth, connectivity, cost, queues) nobody warns
newcomers about.

### Focus

- Transpilation in depth: coupling maps, routing and SWAP insertion, basis-gate
  translation, optimization levels, and why depth grows after transpiling.
- Interchange and execution models: OpenQASM 3, QIR, and the Qiskit primitives
  (Sampler/Estimator); pulse-level control as a sidebar.
- **Resource estimation** before spending time or money (Azure Quantum Resource
  Estimator; qubit, depth, and T-count budgeting).
- **Error mitigation as a toolkit** (Mitiq, primitive-level mitigation), with
  the Chapter 45 distinction from correction kept sharp.
- Hands-on access recipes for IBM Quantum, Amazon Braket, and IonQ/Quantinuum,
  including realistic cost and queue expectations.

### Programming Demonstration

Transpile one circuit at several optimization levels and chart depth and gate
count; run it ideal, noisy-simulated, and on a real backend, then align the
results with a mitigation pass.

### Assignment

Estimate the resources for a target algorithm, then run a small version on real
hardware and explain the gap between estimate and outcome.

---

## Chapter 60 - Performance, Scale, and Differentiable Quantum Programming  **[NEW]**

### Description

How to make experiments bigger and faster: choosing the right simulator,
GPU-accelerating and JIT-compiling circuits and gradients, and pushing the
classical-simulation boundary with tensor networks and circuit cutting.

### Focus

- Simulator backends and when each wins: statevector, MPS / tensor-network,
  stabilizer, and density-matrix (callback to Chapters 35, 43, 48).
- **GPU and JIT:** PennyLane Catalyst (`qml.qjit`), JAX backends,
  `lightning.gpu`, and CUDA-Q; batching many circuits.
- Differentiable quantum programming and why end-to-end differentiation changes
  how hybrid models are written (callback to Chapter 30).
- **Shot budget as an optimization:** trading variance against runtime and cost.
- **Circuit cutting / knitting** to run larger circuits on smaller devices.

### Programming Demonstration

Benchmark the same variational workload on CPU statevector, an MPS backend, and a
JIT/GPU backend; show the shot-versus-variance tradeoff curve.

### Assignment

Profile a quantum-ML training loop, identify the bottleneck, and cut wall-clock
with a backend, JIT, or batching change; report the speedup honestly.

---

## Chapter 61 - Datasets, Benchmarks, and the Statistics of Quantum Experiments  **[NEW]**

### Description

The measurement and evidence layer that makes a quantum-ML result mean something:
which datasets and benchmark suites to use, which anti-patterns to avoid, and the
statistics needed to separate a real effect from shot noise and selection bias.
This chapter operationalizes the honesty stance of Chapter 49 into a toolset the
capstones import directly.

### Focus

- The standard QML benchmark suites and the shared evaluation harness the
  capstones reuse; the downscaled-MNIST anti-pattern and dataset-selection bias.
- **The statistics of shots:** binomial/multinomial error on estimates, bootstrap
  confidence intervals on expectation values, and propagating shot noise into
  metrics.
- **Testing for advantage, not asserting it:** hypothesis tests, effect sizes,
  multiple-comparison correction, and pre-registered protocols.
- **Experiment tracking:** logging configs, seeds, metrics, and artifacts
  (MLflow / Weights & Biases, typed or Hydra configs) so a sweep is reproducible
  and construct-matched (one config, one pass, one artifact).

### Programming Demonstration

Run a quantum-versus-classical comparison through the shared harness with
bootstrap error bars; show how a naive point comparison can flip once shot noise
and a tuned baseline are included.

### Assignment

Design a pre-registered, statistically honest benchmark for a small QML claim,
including baselines, error bars, and a dequantization check.

---

# Part XI - Capstone Projects

## Focus of Part XI

Project-based learning: design, implement, evaluate, and explain complete
quantum AI experiments with honest baselines, reproducible code, and the
software / statistics practice of Part X.

---

## Chapter 62 - How to Build a Quantum ML Experiment

Experimental discipline: research question, dataset, baseline, quantum model,
metrics, ablation, noise analysis, reproducibility. References the companion
repo, the shared benchmark suite and harness (Chapter 61), experiment tracking,
and the dequantization mindset from Chapter 49.

- **Assignment:** write a complete experimental protocol.

---

## Chapter 63 - Capstone 1: Quantum Kernel Classifier

Dataset, classical baselines, quantum feature map, quantum kernel matrix, SVM,
evaluation, report. **Deliverable:** a short paper-style report comparing
classical and quantum kernels.

---

## Chapter 64 - Capstone 2: Variational Quantum Classifier

Data encoding, ansatz design, measurement output, loss, optimizer, training
curves, classical comparison. **Deliverable:** a reproducible notebook and report.

---

## Chapter 65 - Capstone 3: Quantum Generative Model

Target distribution, circuit sampler, training objective, sample evaluation,
visualization, failure analysis. **Deliverable:** a report comparing generated
and target distributions.

---

## Chapter 66 - Capstone 4: Quantum Optimization for AI

Formulate an AI-related optimization problem via QUBO, Ising, QAOA, or a
quantum-inspired solver: feature selection, clustering, scheduling, assignment,
hyperparameters, routing. **Deliverable:** a full optimization experiment with
classical comparison.

---

## Chapter 67 - Capstone 5: Noise-Aware Quantum ML Study  **[NEW in v2.2]**

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

## Chapter 68 - Capstone 6: Reproduce a Published Result with an AI Copilot  **[NEW]**

### Description

The capstone that fuses the research and software spines: take one published
quantum-ML result and reproduce it end to end, using an AI copilot for scaffolding
and translation while holding the line on correctness, statistics, and honest
baselines. This is where the Build-With-AI thread (Chapter 58), the statistics
toolset (Chapter 61), and the dequantization lens (Chapter 49) come together.

### Required Components

- a target result from the literature (for example the Bowles-Ahmed-Schuld
  benchmark, a kernel-concentration scaling, a barren-plateau variance law, or a
  classical-surrogate demonstration),
- a reproduction built in the tested companion environment, with the copilot's
  contributions and the reader's corrections both documented,
- error bars and a statistical comparison against a tuned classical baseline,
- an explicit statement of how the result could be dequantized or classically
  surrogated.

### Deliverable

A reproducible repository plus a short paper-style report: what was reproduced,
where the copilot helped or misled, and where the claimed advantage actually
stands.

---

## Chapter 69 - Final Perspective: What Quantum AI Is Today

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
results the book uses, with worked proofs and a quick-reference summary. **Also
collects the proof sketches** for the results the chapters use intuitively: the
parameter-shift rule, parameterized circuits as a truncated Fourier series, the
barren-plateau gradient-variance scaling, no-cloning, and the kernel/variational
equivalence, each with full references.

## Appendix B - Notation, Symbols, and Dirac Notation Reference

A complete table of symbols and conventions used in the book, with Dirac notation
explained alongside the equivalent vector/matrix forms.

## Appendix C - Environment Setup and the Companion Repository  **[NEW]**

How to set up a reproducible environment: pinned versions (Python, NumPy,
Matplotlib, scikit-learn, PennyLane, Qiskit 2.x and its split packages, a
tensor-network library, plus the Part X tooling: testing, CI, JIT/GPU,
mitigation, and tracking), random-seed conventions, how to run on real hardware
(IBM Quantum, Amazon Braket, IonQ/Quantinuum), and how the companion repository is
organized (with its test suite and CI). Every code listing maps to a runnable,
tested notebook here. Notes the Qiskit 1.0/2.0 API break and why TensorFlow
Quantum is not used. The hands-on treatment lives in Chapter 58.

## Appendix D - Solutions and Instructor Resources  **[NEW]**

Solution sketches for representative assignments of each type, suggested grading
rubrics, the chapter-dependency graph in full, and pointers to slides and
problem sets in the companion repository.

## Appendix E - The Quantum AI Cookbook  **[NEW]**

Every **Recipe Box** in the book, consolidated and indexed by task, so the book
doubles as a working reference. Recipes are copy-paste, parameterized, and
problem-first, for example: encode a tabular dataset with angle encoding and data
re-uploading; estimate a Pauli expectation with a calibrated shot budget and
error bars; build a quantum-kernel SVM with a tuned classical baseline in one
script; diagnose a barren plateau (gradient variance versus depth) in a few
lines; run the same circuit ideal then noisy then on hardware and align the
results; stand up an experiment-tracking harness with seeds, config, and a single
metrics artifact. Each recipe links back to the chapter that derives it.

## Appendix F - Reproduce-the-Paper Index and Research-Practice Checklist  **[NEW]**

For researchers and advanced students: a curated index of "reproduce this result"
exercises (the benchmark of Bowles-Ahmed-Schuld, kernel-concentration scaling, the
barren-plateau variance law, a classical-surrogate demonstration, a tiny neural
decoder), each with the target claim, the minimal setup, and the honest-baseline
and dequantization check it requires. Closes with a one-page research-practice
checklist: pinned environment, tests, seeds, construct-matched metrics computed in
one pass, error bars, tuned baselines, and an explicit advantage assessment.

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
9.  Library implementation, with a test that pins the expected behavior
10. "Can a classical computer do this?" check
11. Common misconceptions (misconception-first for threshold concepts)
12. Exercises (worked -> faded -> independent)
13. Further reading
14. Forward link to later chapters

Woven through, not numbered:
 -  Mid-chapter self-checks with revealed answers (formative feedback)
 -  Occasional "explain it back in your own words" metacognition prompts
 -  A Recipe Box when the chapter yields a reusable, parameterized snippet
    (collected in Appendix E)
 -  A Build-With-AI Box where a copilot can scaffold the code and the reader
    verifies it
 -  A Research Frontier Box in advanced chapters (open questions)
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
- **Type 5 - Engineering and reproduction:** write a test that pins a quantum
  property; set up CI for a notebook; transpile and run a circuit on real
  hardware and explain the gap; profile and accelerate a training loop; take an
  AI-generated snippet, find its bug or deprecated API, and fix it; reproduce a
  published result end to end with honest baselines and error bars.

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
- **Part X:** environment / CI pipeline diagram, **copilot-and-verify loop**,
  transpilation before/after (depth growth), simulator-backend decision tree,
  shot-versus-variance and speedup curves, **bootstrap error-bar** and
  benchmark-harness schematics.
- **Part XI:** capstone architecture, experimental workflow, report templates,
  reproduce-the-paper provenance diagram.

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
| 14 | Dev environment, hardware access, and project presentations | 58-59, selected |

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
| 14 | Software, hardware access, performance, benchmarking; capstone kickoff | 58-61 |
| (projects) | Capstones, run as graded projects | 62-69 |

---

# 17. Suggested Full-Year Course

## Semester 1 - Quantum Computing Foundations

Chapter 0, Part I, Part II, Part III, and Part VIII (Chapters 43-49).

## Semester 2 - Quantum AI and Machine Learning

Part IV, Part V, Part VI, Part VII, Part IX, Part X (software and research
practice), and Part XI (capstones).

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
9. **A reproducible, tested software artifact** for any of the above: pinned
   environment, automated tests for the quantum code, CI, and experiment
   tracking, with at least one circuit run on real hardware.
10. **A faithful reproduction of a published result**, built with an AI copilot
    and corrected by hand, reported with error bars, a tuned classical baseline,
    and an explicit dequantization assessment.

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
- **Recipe Box** - a reusable, parameterized, copy-paste code snippet, collected
  in Appendix E (the Cookbook).
- **Build-With-AI Box** - how an AI copilot can scaffold or translate the code,
  paired with the verification the reader must still do.
- **Research Frontier Box** - the open questions around the idea (advanced
  chapters), so a graduate student can find a problem worth working on.
- **Test Box** - the assertion or property test that pins a concept's expected
  behavior in code.

---

# 21. Final Book Identity

**Building Quantum AI** should be a bridge textbook: not only a quantum
computing book, not only a quantum machine-learning book, not only a popular
explanation, and not only a mathematical reference.

It should be:

> A complete, visual, programmable, plain-language, graduate-level path from the
> rules of quantum computing to quantum AI and quantum machine learning, with an
> evaluation-first conscience and a software-and-reproducibility spine that lets
> the reader not only understand results but build, run, and reproduce them.

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
How do I build, test, accelerate, and run all of this as trustworthy software?
        v
How do I reproduce a published result and report it with honest statistics?
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

## From v2.4 to v2.5 (series rebranding + 2024-2026 research integration)

- **Rebranded as "Building Quantum AI: From Qubits to Quantum Machine Learning"**,
  following the Hands-On AI Science series naming convention ("Building [X] AI:
  From [Y] to [Z]"). Series context and URL (quantum.apartsin.com) added.
- **Series front-matter entry** added (About the Hands-On AI Science Series,
  matching F8 in VisionAI and LanguageAI).
- **Cover page (index.html) and Table of Contents (toc.html)** created, matching
  the series house style (dark navy cover, Cinzel/Cormorant Garamond, gradient
  part cards, quantum-wave interference background motif).
- **GitHub repository** created at ApartsinProjects/building-quantum-ai.
- **Research findings integrated (2024-2026):**
  - Ch 31: Lie-algebraic barren-plateau theory (DLA criterion, Nature Comm 2024);
    phase-of-matter link for analog VQAs (2025); Research Frontier Box.
  - Ch 32: ICLR 2025 tight generalization bounds (quantum kernels/QNNs vs RFF);
    sample-complexity comparison added to programming demo and assignment.
  - Ch 46: IBM bivariate bicycle qLDPC codes (Nature 2024, 12 logical in 144
    physical); Quantinuum Helios (48 logical in 98 physical, 99.9%+ fidelity);
    AlphaQubit 2 (near-optimal, real-time, microsecond-latency decoder).
  - Ch 47: Microsoft Majorana 1 (Feb 2025) added as a 6th hardware modality
    (topological/topoconductor), with honest "first demo, not yet a computer"
    framing.
  - Ch 49: Entanglement-induced quantum learning advantage (npj Quantum Info 2025,
    unconditional for structured quantum data); robust dequantization (Springer
    2024, classical matching with sample-and-query access).
  - Ch 56: AlphaQubit 2 highlighted as achieving real-time microsecond latency.
  - Ch 57: Drug discovery elevated as fastest-growing application domain, with
    specific QML application types (QSAR, quantum VAEs, virtual screening, DFT).
  - §9 tooling: Qiskit 2.3 C++ transpiler backend noted.
- **Coverage map (§23)** updated with topological qubits row and new finding rows.

## From v2.3 to v2.4 (a software-and-research-grade spine)

The book grows from 64 to **69 numbered chapters**, gains a new part and two
appendices, and weaves three new recurring devices throughout. The goal: equal
value for the researcher (reproducibility, proofs, honest statistics,
paper-reproductions) and the practitioner (shipping code, AI-assisted coding,
hardware access, performance), without disturbing the conceptual arc. Placement
is deliberate: the new chapters sit before and within the capstone block, so
every cross-reference in Parts I-IX is unchanged; only the capstone numbers
shift.

- **New Part X - Quantum AI Software, Hardware Access, and Research Practice**
  (Chapters 58-61):
  - **Ch 58 - The Development Environment and AI-Assisted Coding:** reproducible
    pinned environments, an SDK decision map, testing quantum code (unitarity /
    normalization / property-based), CI for notebooks, and the AI-copilot
    ("vibe coding") workflow plus its verification discipline.
  - **Ch 59 - Compiling, Transpiling, and Running on Real Hardware:**
    transpilation depth, OpenQASM 3 / QIR / primitives, resource estimation,
    error-mitigation toolkits (Mitiq), and access recipes (IBM, Braket,
    IonQ/Quantinuum) with real cost and queue expectations.
  - **Ch 60 - Performance, Scale, and Differentiable Quantum Programming:**
    simulator-backend selection, GPU and JIT (Catalyst, JAX, lightning.gpu,
    CUDA-Q), shot-budget optimization, and circuit cutting.
  - **Ch 61 - Datasets, Benchmarks, and the Statistics of Quantum Experiments:**
    standard suites and a shared harness, shot-noise statistics, bootstrap CIs,
    tests for advantage, and experiment tracking.
- **New Chapter 68 - Capstone 6: Reproduce a Published Result with an AI Copilot**
  fuses the research and software spines; the prior capstones and the Final
  Perspective renumber to 62-67 and 69.
- **New recurring devices (section 20):** Recipe Box, Build-With-AI Box, Research
  Frontier Box, and Test Box, woven from the front matter to the capstones
  (section 3.7).
- **New appendices:** **E - The Quantum AI Cookbook** (all recipes, indexed by
  task) and **F - Reproduce-the-Paper Index and Research-Practice Checklist.**
  Appendix A now also gathers the book's proof sketches.
- **Programming philosophy (section 8)** gains a **Stage 0** (reproducible,
  tested workspace) and the AI-copilot discipline; the chapter template
  (section 12) gains a test step and the new boxes; assignment design (section 13)
  gains a **Type 5** (engineering and reproduction).
- **Tooling (section 9)** adds a software-engineering and research-practice stack
  (uv/conda, pytest/Hypothesis, nbmake/papermill, JAX/Catalyst, lightning.gpu,
  Mitiq, circuit-cutting, MLflow/W&B, Hydra, Resource Estimator, OpenQASM 3/QIR).
- **Updated** the structure block, both course tables, the full-year course, the
  illustration plan, the capstone-outcomes list, the final-identity arc, and the
  coverage map (new section-23 rows for software, hardware, performance, and
  statistics) accordingly.

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
| Software, hardware access, performance, datasets/benchmarks/statistics | 58-61 |
| Capstones and final perspective | 62-69 |

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
| Tooling: Qiskit 2.x (C++ transpiler 2.3+), PennyLane 0.45, CUDA-Q, quimb/cotengra | 9, Appendix C |
| AI-assisted ("vibe") coding; copilot scaffolding and verification | 3.7, 58, 68 |
| Lie-algebraic barren-plateau theory; DLA criterion for trainability | 31 |
| ICLR 2025 generalization bounds (quantum vs RFF); sample-complexity comparison | 32 |
| IBM bivariate bicycle qLDPC codes (12 logical in 144 physical) | 46 |
| Quantinuum Helios 48-logical-qubit milestone | 46, 47 |
| AlphaQubit 2; real-time microsecond-latency neural decoders | 46, 56 |
| Microsoft Majorana 1 topological qubits (6th hardware modality) | 47 |
| Entanglement-induced quantum learning advantage (npj 2025) | 49, 50 |
| Robust dequantization (Springer 2024, sample-and-query access) | 49 |
| Drug discovery as fastest-growing QML application domain (QSAR, quantum VAEs) | 57 |
| Reproducible environments, testing quantum code, CI for notebooks | 58, Appendix C |
| Transpilation, OpenQASM 3 / QIR, primitives, pulse-level control | 59 |
| Resource estimation; error-mitigation toolkits (Mitiq) | 59 |
| Real-hardware access (IBM, Braket, IonQ/Quantinuum), cost and queues | 59 |
| GPU / JIT simulation, Catalyst/JAX, differentiable programming, circuit cutting | 60 |
| Datasets and benchmark suites; downscaled-MNIST anti-pattern; shared harness | 61 |
| Statistics of shots; bootstrap CIs; tests for advantage; experiment tracking | 61 |
| Reproduce-the-paper exercises; research-practice checklist | 68, Appendix F |
| Recipes / cookbook | Appendix E, Recipe Boxes throughout |

## Deliberately sidebarred (not full chapters)

Continuous-variable / photonic QML, quantum privacy / federated / blind QML, and
cryptographic impact (Shor / post-quantum security), per section 11.1.
```
