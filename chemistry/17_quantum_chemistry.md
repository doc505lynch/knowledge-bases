# Quantum Chemistry and Computational Methods

## Foundations of Quantum Chemistry

Quantum chemistry applies quantum mechanics to chemical systems — predicting molecular structure, bonding, spectra, reactivity, and thermodynamic properties from first principles. It bridges physics and chemistry by treating electrons as wavefunctions rather than classical particles.

---

## The Schrödinger Equation

### Time-Independent Form

**ĤΨ = EΨ**

Where:
- **Ĥ** = Hamiltonian operator (total energy operator)
- **Ψ** = wavefunction (contains all information about the system)
- **E** = energy eigenvalue

### The Hamiltonian for Molecular Systems

For a molecule with M nuclei and N electrons:

**Ĥ = T̂_e + T̂_N + V̂_ee + V̂_eN + V̂_NN**

| Term | Physical meaning |
|------|-----------------|
| T̂_e | Kinetic energy of electrons |
| T̂_N | Kinetic energy of nuclei |
| V̂_ee | Electron-electron repulsion |
| V̂_eN | Electron-nucleus attraction |
| V̂_NN | Nucleus-nucleus repulsion |

Exact solutions exist only for one-electron systems (H atom, He⁺, H₂⁺). Everything else requires approximations.

---

## The Born-Oppenheimer Approximation

Nuclei are ~1836× heavier than electrons → nuclei move much slower. We can separate nuclear and electronic motion:

1. **Fix nuclei** at positions R → solve electronic Schrödinger equation → get electronic energy E(R)
2. **E(R) becomes the potential energy surface (PES)** on which nuclei move
3. **Solve nuclear motion** on the PES → vibrational/rotational states

This is the foundation of nearly all quantum chemistry. It fails for:
- Conical intersections (photochemistry)
- Very light nuclei (proton transfer, muon chemistry)
- Jahn-Teller distortions

---

## Potential Energy Surfaces (PES)

The PES maps electronic energy as a function of nuclear coordinates.

### Key Features

| Feature | Definition | Chemical significance |
|---------|-----------|----------------------|
| Minimum | ∂E/∂R = 0, all curvatures positive | Stable geometry (equilibrium structure) |
| Saddle point | ∂E/∂R = 0, one negative curvature | Transition state |
| Global minimum | Lowest energy minimum | Most stable isomer |
| Dissociation limit | E as R → ∞ | Bond dissociation energy |

### Degrees of Freedom

A nonlinear molecule with N atoms has **3N − 6** internal degrees of freedom (3N − 5 for linear). The PES is a hypersurface in this many dimensions.

- H₂O: 3 internal coordinates (2 bond lengths, 1 angle) → 3D PES
- Benzene (C₆H₆): 30 internal coordinates → 30D PES

---

## Hartree-Fock (HF) Theory

### The Independent Particle Model

Each electron moves in the average field of all other electrons. The many-electron wavefunction is approximated as an antisymmetrized product (Slater determinant):

**Ψ_HF = (1/√N!) det|χ₁(1) χ₂(2) ... χ_N(N)|**

Where χᵢ are spin-orbitals (spatial orbital × spin function).

### The Self-Consistent Field (SCF) Procedure

1. Guess initial molecular orbitals (MOs)
2. Construct the Fock matrix (one-electron + averaged two-electron terms)
3. Solve the Roothaan-Hall equations: **FC = SCε**
4. Get new MOs → rebuild Fock matrix
5. Repeat until energy converges (self-consistent)

### Basis Sets

MOs are expanded as linear combinations of **basis functions** (usually Gaussian-type orbitals, GTOs):

**φᵢ = Σ cᵢⱼ gⱼ**

| Basis set | Size | Description |
|-----------|------|-------------|
| STO-3G | Minimal | Each Slater orbital fit by 3 Gaussians. Fast, inaccurate. |
| 3-21G | Split-valence | Core: 1 function; valence: 2 functions |
| 6-31G(d) | Polarized | Adds d-functions on heavy atoms |
| 6-31+G(d,p) | Diffuse + polarized | Adds diffuse functions; good for anions |
| 6-311++G(2d,2p) | Triple-zeta | Large, flexible; near HF limit |
| cc-pVDZ/TZ/QZ | Correlation-consistent | Designed for post-HF; systematic convergence |
| aug-cc-pVTZ | Augmented | Adds diffuse functions to cc-pVTZ |
| def2-TZVP | Ahlrichs | Efficient for DFT; good balance of cost/accuracy |

**Basis set superposition error (BSSE):** Interaction energies are overestimated when basis functions of one fragment improve the description of another. Corrected by counterpoise method.

### Limitations of Hartree-Fock

- **No electron correlation** — HF accounts for exchange but not dynamic correlation
- **Correlation energy:** E_corr = E_exact − E_HF (always negative, typically 1% of total energy but chemically crucial)
- Bond dissociation: HF incorrectly dissociates H₂ to H⁺ + H⁻ mixture
- Transition metals: HF performs poorly for open-shell d-electron systems

---

## Post-Hartree-Fock Methods (Wavefunction-Based Correlation)

### Møller-Plesset Perturbation Theory (MPn)

Treats correlation as a perturbation to the HF Hamiltonian:

| Level | Scaling | Accuracy | Notes |
|-------|---------|----------|-------|
| MP2 | O(N⁵) | Good for weak interactions | Most common; captures ~80-90% of correlation |
| MP3 | O(N⁶) | Marginal improvement | Rarely used |
| MP4 | O(N⁷) | Better | Includes triple excitations |

MP2 is the workhorse for non-covalent interactions (hydrogen bonds, van der Waals).

### Configuration Interaction (CI)

Expands the wavefunction as a linear combination of Slater determinants:

**Ψ_CI = c₀Ψ_HF + Σ cₛΨₛ + Σ c_dΨ_d + Σ c_tΨ_t + ...**

| Level | Excitations included | Notes |
|-------|---------------------|-------|
| CIS | Singles only | Excited states only; no ground-state correlation |
| CISD | Singles + doubles | Common; not size-consistent |
| Full CI | All excitations | Exact within basis set; exponential scaling |

**Size consistency problem:** CISD energy of A + B at infinite separation ≠ E(A) + E(B). This is a serious flaw for dissociation curves.

### Coupled Cluster (CC) Theory

Uses an exponential ansatz: **Ψ_CC = e^T̂ Ψ_HF**

| Method | Operator | Scaling | Accuracy |
|--------|----------|---------|----------|
| CCSD | T̂ = T̂₁ + T̂₂ | O(N⁶) | Good |
| CCSD(T) | + perturbative triples | O(N⁷) | "Gold standard" of quantum chemistry |
| CCSDT | Full triples | O(N⁸) | Benchmark quality |
| CCSDTQ | + quadruples | O(N¹⁰) | Near-exact |

**CCSD(T)/CBS** (complete basis set extrapolation) typically achieves:
- Bond energies within ±1 kcal/mol
- Bond lengths within ±0.002 Å
- Vibrational frequencies within ±10 cm⁻¹

### Multi-Reference Methods

For systems where a single determinant is qualitatively wrong (bond breaking, biradicals, excited states, transition metals):

| Method | Description |
|--------|-------------|
| CASSCF | Complete Active Space SCF — full CI within an active space of selected orbitals |
| CASPT2 | CASSCF + MP2-like perturbation theory for dynamic correlation |
| MRCI | Multi-Reference CI — CI from multiple reference determinants |
| NEVPT2 | N-electron valence perturbation theory — improved CASPT2 |

**Active space selection** is the critical (and often difficult) step. Notation: CAS(m,n) = m electrons in n orbitals.

---

## Density Functional Theory (DFT)

### Hohenberg-Kohn Theorems (1964)

1. The ground-state electron density ρ(r) uniquely determines the external potential (and thus all properties)
2. The energy functional E[ρ] is minimized by the true ground-state density

**Implication:** In principle, we only need the 3D density ρ(r), not the 3N-dimensional wavefunction.

### Kohn-Sham (KS) Formalism (1965)

Map the interacting system to a fictitious non-interacting system with the same density:

**E[ρ] = T_s[ρ] + E_ext[ρ] + E_H[ρ] + E_xc[ρ]**

| Term | Meaning |
|------|---------|
| T_s[ρ] | Kinetic energy of non-interacting electrons (KS orbitals) |
| E_ext[ρ] | Electron-nucleus attraction |
| E_H[ρ] | Classical Coulomb (Hartree) repulsion |
| E_xc[ρ] | Exchange-correlation energy — everything else (unknown, must approximate) |

The KS equations are solved self-consistently, like HF but with an exchange-correlation potential v_xc = δE_xc/δρ.

### Jacob's Ladder of DFT Functionals

| Rung | Depends on | Examples | Accuracy |
|------|-----------|----------|----------|
| 1. LDA | ρ | SVWN, PW92 | Overbinds; poor for molecules |
| 2. GGA | ρ, ∇ρ | PBE, BLYP, BP86 | Better geometries and energies |
| 3. meta-GGA | ρ, ∇ρ, τ (KE density) | TPSS, M06-L, r²SCAN | Good thermochemistry |
| 4. Hybrid | + exact (HF) exchange | B3LYP, PBE0, M06-2X | Best general-purpose |
| 5. Double hybrid | + MP2 correlation | B2PLYP, DSD-BLYP, ωB97M(2) | Near-CCSD(T) accuracy |

### Popular Functionals and Their Strengths

| Functional | Type | Best for |
|------------|------|----------|
| B3LYP | Hybrid GGA (20% HF) | General organic chemistry, geometries |
| PBE0 | Hybrid GGA (25% HF) | Solids, general chemistry |
| M06-2X | Hybrid meta-GGA (54% HF) | Thermochemistry, kinetics, non-covalent |
| ωB97X-D | Range-separated hybrid + dispersion | Non-covalent, reaction barriers |
| r²SCAN | meta-GGA | Materials, solids, general |
| B2PLYP-D3 | Double hybrid + dispersion | Benchmark-quality thermochemistry |

### Dispersion Corrections

Standard DFT cannot describe London dispersion (van der Waals) forces. Corrections:

| Method | Approach |
|--------|----------|
| DFT-D3(BJ) | Empirical atom-pairwise C₆/R⁶ + C₈/R⁸ with Becke-Johnson damping |
| DFT-D4 | Charge-dependent dispersion coefficients |
| VV10 / NL | Non-local density functional for dispersion |
| XDM | Exchange-dipole moment model |

**Always use dispersion corrections** for systems with non-covalent interactions (biomolecules, crystals, adsorption).

### DFT Performance and Limitations

**Strengths:**
- O(N³) scaling — tractable for 100-1000+ atoms
- Good geometries, vibrational frequencies, reaction energies
- Reasonable barrier heights with hybrid functionals

**Weaknesses:**
- Self-interaction error: electron interacts with itself in E_H (partially corrected by exact exchange)
- Band gap underestimation (LDA/GGA)
- Charge-transfer excited states (use range-separated hybrids)
- Strongly correlated systems (transition metal clusters, Mott insulators)
- No systematic improvability — unlike wavefunction methods, you can't just go to a higher level

---

## Molecular Orbital Theory — Deep Dive

### LCAO-MO Approach

Molecular orbitals are linear combinations of atomic orbitals:

**ψ_MO = Σ cᵢφᵢ**

Coefficients cᵢ determined by variational principle (minimize energy) → secular equations.

### Hückel Theory (π-Electrons)

For conjugated π-systems, ignore σ-framework and electron-electron repulsion:

| Parameter | Value |
|-----------|-------|
| α (Coulomb integral) | Energy of electron in isolated p-orbital |
| β (resonance integral) | Interaction between adjacent p-orbitals (negative) |
| S (overlap integral) | Set to 0 (Hückel approximation) |

**Hückel 4n+2 rule:** Planar, cyclic, conjugated molecules with 4n+2 π-electrons are aromatic.

| System | π-electrons | Aromatic? |
|--------|-------------|-----------|
| Benzene | 6 (4×1+2) | Yes |
| Cyclobutadiene | 4 (4×1) | Anti-aromatic |
| Cyclopentadienyl anion | 6 | Yes |
| Cyclooctatetraene | 8 | Non-aromatic (non-planar) |

### Frontier Molecular Orbital Theory

Chemical reactivity is governed by:
- **HOMO** (Highest Occupied MO) — electron donor
- **LUMO** (Lowest Unoccupied MO) — electron acceptor
- **HOMO-LUMO gap** — relates to chemical hardness, stability, spectral properties

**Woodward-Hoffmann rules:** Pericyclic reactions (Diels-Alder, electrocyclic, sigmatropic) are controlled by orbital symmetry of HOMO/LUMO interactions.

### Natural Bond Orbital (NBO) Analysis

Transforms delocalized MOs into localized bond orbitals, lone pairs, and antibonds:
- Quantifies Lewis structure validity
- Measures hyperconjugation (donor-acceptor interactions between filled and empty NBOs)
- Gives natural charges (more robust than Mulliken)

---

## Computational Methods in Practice

### Geometry Optimization

Find the minimum on the PES by following energy gradients:

1. Calculate energy and gradient (∂E/∂R) at current geometry
2. Use optimization algorithm (quasi-Newton, BFGS) to step toward minimum
3. Repeat until gradient ≈ 0 and energy converges

**Frequency calculation** at the optimized geometry confirms it's a true minimum (all frequencies real) vs. transition state (one imaginary frequency).

### Transition State Searches

| Method | Approach |
|--------|----------|
| QST2/QST3 | Synchronous transit — requires reactant + product (+ guess) |
| Nudged Elastic Band (NEB) | Chain of images along reaction path |
| Dimer method | Follows lowest curvature mode uphill |
| IRC | Intrinsic Reaction Coordinate — follows path downhill from TS |

### Thermochemistry

From frequency calculations, compute:
- **Zero-point energy (ZPE):** (1/2)Σhνᵢ
- **Thermal corrections:** translational + rotational + vibrational contributions
- **Enthalpy:** H = E_elec + ZPE + thermal + PV
- **Entropy:** S from partition functions
- **Gibbs free energy:** G = H − TS

### Solvation Models

| Model | Type | Description |
|-------|------|-------------|
| PCM/CPCM | Implicit | Molecule in a cavity surrounded by dielectric continuum |
| SMD | Implicit | Improved cavity + non-electrostatic terms |
| COSMO-RS | Implicit | Statistical thermodynamics of surfaces |
| QM/MM | Explicit | Quantum region + classical solvent |

### Basis Set Extrapolation

Correlation energy converges slowly with basis set size. Extrapolate to the complete basis set (CBS) limit:

**E_corr(X) = E_CBS + A·X⁻³** (for cc-pVXZ, X = D,T,Q,...)

### Composite Methods

Combine multiple calculations for high-accuracy thermochemistry:

| Method | Target accuracy | Approach |
|--------|----------------|----------|
| G4 | ±1 kcal/mol | HF + MP2 + CCSD(T) with different basis sets |
| W1/W2 | sub-kcal/mol | CCSD(T)/CBS + core correlation + relativistic |
| CBS-QB3 | ±1.5 kcal/mol | HF/CBS + MP2 + CCSD(T) correction |
| HEAT | sub-kJ/mol | CCSDT(Q) + relativistic + DBOC |

---

## Modern Developments

### Resolution of Identity (RI) and Density Fitting

Approximate four-center two-electron integrals using auxiliary basis sets:
- RI-MP2: 10-100× faster with negligible error
- RI-DFT: standard in modern codes

### Domain-Based Local Pair Natural Orbital (DLPNO)

**DLPNO-CCSD(T):** Near-linear scaling coupled cluster
- Handles 100-1000+ atoms at near-CCSD(T) accuracy
- Makes "gold standard" accessible for real-world molecules

### Machine Learning in Quantum Chemistry

| Application | Method |
|-------------|--------|
| Force fields | Neural network potentials (ANI, SchNet, MACE) trained on DFT/CCSD(T) data |
| Functional design | ML-optimized DFT functionals (DM21, ωB97M-V) |
| Property prediction | Graph neural networks for HOMO-LUMO gaps, solubility |
| Wavefunction methods | FermiNet, PauliNet — neural network ansatz for variational Monte Carlo |

### Relativistic Quantum Chemistry

Important for heavy elements (5d, 6d, actinides):

| Effect | Consequence |
|--------|-------------|
| Scalar relativistic | s/p orbital contraction, d/f expansion → gold's color, mercury's liquid state |
| Spin-orbit coupling | Splits degenerate levels → fine structure, heavy-element magnetism |
| ZORA/DKH/X2C | Approximate relativistic Hamiltonians used in practice |

---

## Major Quantum Chemistry Software

| Code | Strengths |
|------|-----------|
| Gaussian | General-purpose, composite methods, user-friendly |
| ORCA | DFT, DLPNO-CCSD(T), spectroscopy, free for academics |
| Psi4 | Open-source, CC methods, Python API |
| Q-Chem | Excited states, EOM-CC, novel DFT |
| VASP | Periodic DFT, materials science |
| CP2K | Mixed Gaussian/plane-wave, molecular dynamics |
| Turbomole | RI methods, fast DFT |
| MOLPRO | Multi-reference, high-accuracy |
| NWChem | Massively parallel, open-source |
| xTB/GFN | Semi-empirical tight-binding, screening |

---

## Practical Workflow

### Choosing a Method

| System size | Recommended approach |
|-------------|---------------------|
| 1-10 atoms | CCSD(T)/CBS or composite (G4, W1) |
| 10-50 atoms | DFT (ωB97X-D or r²SCAN) + DLPNO-CCSD(T) benchmarks |
| 50-500 atoms | DFT with dispersion (B3LYP-D3BJ, PBE0-D3) |
| 500-5000 atoms | Semi-empirical (GFN2-xTB) or QM/MM |
| 5000+ atoms | Force fields (classical MD), ML potentials |

### Common Pitfalls

1. **Wrong spin state:** Always check multiplicity for transition metals
2. **Missing dispersion:** B3LYP without -D3 misses van der Waals completely
3. **Basis set too small:** Minimal basis (STO-3G) gives qualitative nonsense
4. **Symmetry traps:** Optimizer may find wrong stationary point if symmetry imposed
5. **SCF convergence:** Open-shell and transition metal systems often need level shifting or DIIS damping
6. **Imaginary frequencies:** Re-optimize with tighter convergence or different algorithm
7. **Conformer search:** Always check multiple conformers — the obvious geometry may not be the global minimum
