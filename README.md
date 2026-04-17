<div align="center">

<br/>

```
 ██████  ██    ██  █████  ███    ██ ████████ ██    ██ ███    ███
██    ██ ██    ██ ██   ██ ████   ██    ██    ██    ██ ████  ████
██    ██ ██    ██ ███████ ██ ██  ██    ██    ██    ██ ██ ████ ██
██ ▄▄ ██ ██    ██ ██   ██ ██  ██ ██    ██    ██    ██ ██  ██  ██
 ██████   ██████  ██   ██ ██   ████    ██     ██████  ██      ██
    ▀▀
██████  ███████ ███████ ███████  █████  ██████   ██████ ██   ██
██   ██ ██      ██      ██      ██   ██ ██   ██ ██      ██   ██
██████  █████   ███████ █████   ███████ ██████  ██      ███████
██   ██ ██           ██ ██      ██   ██ ██   ██ ██      ██   ██
██   ██ ███████ ███████ ███████ ██   ██ ██   ██  ██████ ██   ██

██       █████  ██████
██      ██   ██ ██   ██
██      ███████ ██████
██      ██   ██ ██   ██
███████ ██   ██ ██████
```

<br/>

**An interactive game-based platform for learning Quantum Computing — no equations, no code, just intuition.**

<br/>

![Status](https://img.shields.io/badge/status-in%20development-cyan?style=flat-square&color=00e5ff)
![Modules](https://img.shields.io/badge/modules-7-blue?style=flat-square&color=0a0f1e)
![Type](https://img.shields.io/badge/type-undergraduate%20project-blueviolet?style=flat-square)
![License](https://img.shields.io/badge/license-MIT-green?style=flat-square)

<br/>

[**Live Demo**](#) · [**Documentation**](#architecture) · [**Modules**](#modules) · [**Contributing**](#contributing)

<br/>

---

</div>

## What is this?

**Quantum Research Lab** is a web-based interactive learning platform designed to teach core quantum computing and quantum physics concepts through games, simulations, and puzzles — with zero mathematics exposure required.

Every module is built around a single principle: **understanding through doing, not reading**. Instead of equations on a slide, you fire particles through slits and watch interference emerge. Instead of reading about Grover's algorithm, you race it against a classical search and discover over-rotation the hard way. Instead of a diagram of quantum teleportation, you play the spy who has to send a secret state without letting the interceptor learn anything useful.

This is a 4-credit undergraduate mini-project in Computer Science, focused on the intersection of quantum computing education, interactive design, and game-based learning.

<br/>

---

## Modules

Seven lab stations, each teaching a distinct concept through a distinct interaction model.

<br/>

### 🌊 Station 01 — Young's Double Slit Experiment
> **Concept:** Wave-particle duality · Superposition · Observer effect

A fully physics-accurate interactive simulation. Fire quantum particles one at a time or in streams, watch the interference pattern build up statistically, and toggle the which-path detector to collapse it into classical behavior in real time.

**8 coupled parameters:** Wavelength · Slit Width · Slit Height · Slit Separation · Slit Gap · Screen Distance · Path Difference probe · Refractive Index (slab)

**Reverse engineering:** Adjusting fringe width β back-calculates and updates your choice of λ, D, or d automatically. All parameters are bidirectionally coupled — changing the slit gap updates slit width, changing slit separation propagates through fringe width, and the wavelength shifts the color of the entire simulation in real time.

```
Intensity pattern: I(y) = cos²(πdy/λD) · [sin(πay/λD) / (πay/λD)]²
Fringe width:      β = λD/d
Fringe shift:      Δy = (μ−1)t · D/d
```

<br/>

### 🎯 Station 02 — Heisenberg's Dilemma
> **Concept:** Uncertainty Principle · Position-momentum trade-off

A turn-based strategy game on a 15-cell grid. Each turn you choose to measure position (collapses the probability cloud, randomizes momentum) or momentum (reveals direction, spreads the cloud). You have 10 turns to get the particle into the target zone — and the physics makes it provably impossible to cheat by measuring both.

The game is **unwinnable by brute force**. Optimal play requires alternating between measurement types, and even then success is probabilistic. Students don't just understand the uncertainty principle — they feel it.

<br/>

### 🔌 Station 03 — Quantum Circuit Builder
> **Concept:** Quantum Gates · Superposition · Entanglement

A drag-and-drop puzzle game. Build circuits using **X · Y · Z · H · S · T · CNOT** gates to transform input qubit states into target states. The circuit runner animates step-by-step state transformations. Three tiers: single-qubit basics, phase-sensitive puzzles, and two-qubit Bell state construction.

This is the most foundational module — the gate vocabulary built here underpins Teleportation, Grover's, and Error Correction.

<br/>

### 📡 Station 04 — Operation Entangle
> **Concept:** Quantum Teleportation · Entanglement as resource · No-FTL communication

A hybrid spy-puzzle game. In the narrative levels, the player is Alice — a field agent who must teleport a secret quantum state to Bob using a pre-shared entangled pair and exactly two classical bits, while interceptor Eve watches the channel and learns nothing. In the relay levels, the player manages a multi-hop quantum network, consuming entangled pairs at each node.

The moment Eve intercepts the classical bits and her speech bubble says *"I received: 01. But I don't know what the package was"* is the single best teaching moment in the entire platform.

<br/>

### 🔍 Station 05 — Grover's Hunt
> **Concept:** Amplitude amplification · Quantum search speedup · Over-rotation

A real-time race between a classical random search agent and the player running Grover's algorithm on the same N-tile grid. The player manually applies oracle → amplify cycles, watching amplitude bars grow toward the marked tile. The twist: running too many iterations causes the amplitude to **decrease** again (over-rotation), costing you the race.

At N=64, the classical agent takes ~32 steps on average. Grover's takes 8. The race makes the quadratic speedup visceral rather than theoretical.

<br/>

### 🛡️ Station 06 — Quantum Error Warden
> **Concept:** Error correction · Syndrome measurement · No-cloning theorem · Code distance

A real-time error correction game. A 5-qubit register (3 data + 2 syndrome qubits) is under constant noise. Syndrome measurements reveal which qubit is corrupted — without collapsing the data — and the player must apply the correct corrective gate before the decoherence timer runs out. Later levels introduce phase-flip errors, simultaneous multi-qubit errors that exceed the code's capacity, and the concept of code distance as a natural consequence of failure.

The no-cloning theorem is enforced mechanically: attempting to copy a qubit tile is blocked with a brief explanation.

<br/>

### 🤖 Station 07 — QML Showdown
> **Concept:** Quantum ML · NISQ limitations · Conditional quantum advantage

An analytical comparison module built around a **real variational quantum circuit classifier** and its classical counterpart, running on the same dataset. The quantum model achieves ~70% accuracy vs the classical model's ~90% — and the module makes *that gap the entire point*.

Interactive controls let students adjust training sample size, hardware noise level, and circuit depth, watching confusion matrices and decision boundaries update live. A hypothesis mode asks students to predict which model will suffer more before each parameter change. A dynamic analysis panel explains *why* the result occurred in plain language.

> This is the only quantum education module we know of that shows a quantum model **losing** and treats that honestly as a richer teaching moment than a rigged demo.

<br/>

---

## Architecture

```
quantum-research-lab/
│
├── shell/                    # Lab dashboard, navigation, progress tracking
│   ├── LabDashboard
│   ├── ProgressManager
│   └── NavigationRouter
│
├── core/                     # Shared engine, used by all modules
│   ├── QuantumStateEngine    # Qubit math: gates, measurement, entanglement
│   ├── VisualizationLib      # Shared renderers: probability bars, grids, patterns
│   ├── GameStateManager      # Turn logic, scoring, level progression
│   └── EventBus              # Cross-module communication
│
├── modules/
│   ├── double-slit/          # Station 01 — Physics simulation
│   ├── heisenberg/           # Station 02 — Turn-based game
│   ├── circuit-builder/      # Station 03 — Puzzle game
│   ├── teleportation/        # Station 04 — Spy/relay hybrid
│   ├── grovers-hunt/         # Station 05 — Race game
│   ├── error-warden/         # Station 06 — Real-time defense game
│   └── qml-showdown/         # Station 07 — Analytical module
│
└── backend/                  # Module 07 only
    ├── models/
    │   ├── classical_model.py
    │   └── quantum_model.py  # Existing VQC classifier
    ├── precompute.py          # 150-point result grid (5×6×5 param space)
    └── api.py                 # FastAPI endpoints
```

### Key Design Decisions

**No 3D graphics.** Every visualization is 2D, canvas-based, or text-driven. This forces the design to live or die on conceptual clarity rather than visual spectacle.

**Bidirectional parameter coupling.** In the YDSE module, all 8 physical parameters are mathematically coupled. Changing any one of them propagates through the system. Fringe width can be set directly, with the system back-calculating whichever variable the user nominates.

**Precomputed QML result grid.** The QML backend precomputes model outputs across a 5×6×5 grid of (sample\_size × noise\_level × circuit\_depth) combinations — 150 total configurations — so slider interactions are instantaneous with zero inference latency.

**No real quantum hardware.** Everything is simulated. The quantum state engine runs on classical hardware using the correct linear algebra, making the platform deployable anywhere with no cloud dependencies.

<br/>

---

## Tech Stack

| Layer | Technology |
|---|---|
| Frontend | HTML5 · CSS3 · Vanilla JavaScript · Canvas API |
| Physics engine | Custom JS (double-slit, Grover amplitude math, gate algebra) |
| QML backend | Python · FastAPI · PennyLane / Qiskit |
| Classical ML | scikit-learn |
| Visualizations | Canvas 2D · Custom renderers |
| Fonts | Space Mono · Syne · DM Serif Display |

<br/>

---

## Module Status

| Station | Module | Status | Difficulty |
|---------|--------|--------|------------|
| 01 | Young's Double Slit | ✅ Complete | 4/10 |
| 02 | Heisenberg's Dilemma | 🔨 In Progress | 5/10 |
| 03 | Quantum Circuit Builder | 📋 Designed | 6/10 |
| 04 | Operation Entangle | 📋 Designed | 6/10 |
| 05 | Grover's Hunt | 📋 Designed | 6/10 |
| 06 | Quantum Error Warden | 📋 Designed | 7/10 |
| 07 | QML Showdown | 📋 Designed | 7/10 |

<br/>

---

## Physics Reference

### Young's Double Slit

| Formula | Description |
|---------|-------------|
| `β = λD/d` | Fringe width |
| `Δ = d·y/D` | Path difference at screen position y |
| `I(y) = cos²(πdy/λD) · sinc²(πay/λD)` | Intensity with diffraction envelope |
| `Shift = (μ−1)·t·D/d` | Fringe shift due to refractive slab |
| `n = Shift/β` | Number of fringes shifted |

### Grover's Algorithm

| Property | Value |
|----------|-------|
| Optimal iterations | `⌊π/4 · √N⌋` |
| Success probability at optimal | `≥ 1 − 1/N` |
| Classical expected steps | `N/2` |
| Quantum speedup | `O(√N)` vs `O(N)` |

### Quantum Teleportation Protocol

```
1. Alice & Bob share entangled pair |Φ⁺⟩ = (|00⟩ + |11⟩)/√2
2. Alice applies CNOT(package, her qubit), then H(package)
3. Alice measures both qubits → gets 2 classical bits (b₁b₂)
4. Alice sends b₁b₂ to Bob over classical channel
5. Bob applies: if b₂=1 → X; if b₁=1 → Z
6. Bob's qubit is now identical to the original package state
```

<br/>

---

## Getting Started

```bash
# Clone the repository
git clone https://github.com/yourusername/quantum-research-lab.git
cd quantum-research-lab

# Open the shell (no build step needed for frontend modules)
open index.html

# For the QML backend (Module 07 only)
cd backend
pip install -r requirements.txt
python precompute.py          # Run once to generate result grid (~2 min)
uvicorn api:app --reload
```

### Requirements

**Frontend modules (01–06):** Any modern browser. No dependencies, no build step.

**QML backend (Module 07):**
```
python >= 3.9
fastapi
uvicorn
pennylane          # or qiskit
scikit-learn
numpy
pandas
```

<br/>

---

## Design Philosophy

> *"The goal is not to replace a quantum computing textbook. The goal is to make someone curious enough to open one."*

Three principles guided every design decision:

**1. Mechanics over metaphors.** A student who has lost Grover's race by over-rotating understands amplitude amplification better than a student who has read about it. The game mechanic *is* the concept.

**2. Honest complexity.** The QML module shows a quantum model losing. The Error Warden shows code failure when two errors exceed the code distance. Real quantum computing has real limitations, and pretending otherwise is a disservice.

**3. Minimal UI, maximum clarity.** No 3D graphics. No particle shaders. No decorative complexity. Every visual element earns its place by communicating something about the physics.

<br/>

---

## Contributing

This project is an active undergraduate research submission. Issues, suggestions, and pull requests are welcome after the initial submission deadline.

If you're a student or educator who wants to use or extend these modules, please open an issue — we'd love to hear how this is being used.

<br/>

---

## Team

Built as a 4-credit undergraduate mini-project.

> *"Design of Interactive Simulations and Game-Based Models for Quantum Computing Education"*

<br/>

---

## License

MIT License — see [LICENSE](LICENSE) for details.

<br/>

---

<div align="center">

*Made with unreasonable enthusiasm for quantum mechanics and good UI.*

<br/>

⬡

</div>
