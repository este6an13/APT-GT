### ♟️ APT Counterplay: Game-Theoretic Defense Framework Under Uncertainty

Implemented in code the game-theoretic defense framework proposed in [Rass, König & Schauer (2017) [1]](https://doi.org/10.1371/journal.pone.0168675), modeling **Advanced Persistent Threats (APTs)** as generalized matrix games under deep uncertainty.

Instead of scalar payoffs, each defense–attack interaction was represented as a **probability distribution over losses**, derived from simulated expert polls. Kernel Density Estimation (KDE) transformed discrete assessments into continuous payoff functions.

Constructed the game as a stack of matrices:

* **Order 0** — KDE evaluated at a risk threshold.
* **Higher orders (k ≤ 20)** — derivatives of the KDE (via Hermite polynomials).

Strategies were compared **lexicographically across derivative vectors**, resolving ties by progressively inspecting higher-order sensitivities at the chosen risk level.

Equilibrium behavior was approximated using a modified **fictitious play** algorithm executed “in parallel” across all derivative matrices, producing mixed strategies consistent with the paper’s Section 9 experiment.

Extended the framework with topology-dependent experiments:

* Random network generation (workstations, routers, servers).
* Topological Vulnerability Analysis (TVA).
* Exponential attack-path construction with bounded sampling.
* Control selection mapped from exploit sets.

This transformed qualitative cyber-risk assessments into **distributional zero-sum games**, where uncertainty itself becomes part of the payoff structure.

The replication reproduced the published equilibrium proportions and demonstrated how network topology reshapes optimal defensive allocations.

### Referencias

[1] Rass S, König S, Schauer S (2017) Defending Against Advanced Persistent Threats Using Game-Theory. PLOS ONE 12(1): e0168675. https://doi.org/10.1371/journal.pone.0168675
