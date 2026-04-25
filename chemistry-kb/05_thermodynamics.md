# Thermodynamics

## Fundamental Concepts

- **System**: portion of universe under study
- **Surroundings**: everything outside the system
- **Universe** = system + surroundings

### System Types
| Type | Matter exchange | Energy exchange |
|------|----------------|----------------|
| Open | Yes | Yes |
| Closed | No | Yes |
| Isolated | No | No |

### Energy Forms
- **Internal energy (U or E)**: total kinetic + potential energy of all particles
- **Heat (q)**: energy transferred due to temperature difference
- **Work (w)**: energy transferred due to force × displacement (e.g., PV work)
- **Enthalpy (H)**: H = U + PV (useful at constant pressure)

### Sign Conventions
| Quantity | Positive (+) | Negative (−) |
|----------|-------------|--------------|
| q | Heat flows into system (endothermic) | Heat flows out (exothermic) |
| w | Work done on system | Work done by system |
| ΔU | Internal energy increases | Internal energy decreases |

## Laws of Thermodynamics

### Zeroth Law
If A is in thermal equilibrium with C, and B is in thermal equilibrium with C, then A and B are in thermal equilibrium. (Basis for temperature measurement)

### First Law (Conservation of Energy)
```
ΔU = q + w
```
For a system at constant pressure:
```
q_p = ΔH = ΔU + PΔV
```
For ideal gases: ΔH = ΔU + ΔnRT (where Δn = moles of gaseous products − reactants)

PV work: w = −PextΔV (expansion: w < 0; compression: w > 0)

### Second Law
The entropy of an isolated system always increases for spontaneous processes.
```
ΔS_universe = ΔS_system + ΔS_surroundings ≥ 0
```
(= 0 for reversible processes; > 0 for irreversible/spontaneous)

### Third Law
The entropy of a perfect crystalline solid at absolute zero (0 K) is zero.
→ Absolute entropy values (S°) can be calculated

## Enthalpy (H)

### Enthalpy Change
ΔH = H_products − H_reactants

- **Exothermic** (ΔH < 0): energy released; products lower energy than reactants
- **Endothermic** (ΔH > 0): energy absorbed; products higher energy than reactants

### Standard Enthalpy of Formation (ΔH°f)
Enthalpy change when 1 mole of compound forms from its elements in their standard states.
- Standard state: most stable form at 25°C, 1 bar
- ΔH°f of pure elements in standard state = 0

### Hess's Law
ΔH for overall reaction = sum of ΔH for steps; enthalpy is a state function.

```
ΔH°rxn = Σ ΔH°f(products) − Σ ΔH°f(reactants)
```

**Example**: CH₄(g) + 2O₂(g) → CO₂(g) + 2H₂O(l)
ΔH°rxn = [ΔH°f(CO₂) + 2·ΔH°f(H₂O)] − [ΔH°f(CH₄) + 2·ΔH°f(O₂)]
= [−393.5 + 2(−285.8)] − [−74.8 + 0] = −890.3 kJ/mol

### Bond Enthalpy Method (Approximate)
```
ΔH°rxn ≈ Σ(bonds broken) − Σ(bonds formed)
```
(Breaking bonds requires energy; forming bonds releases energy)

### Common Thermochemical Values
| Reaction type | Typical ΔH |
|--------------|------------|
| Combustion of hydrocarbons | −500 to −5000 kJ/mol |
| Dissolution of NaCl | +3.9 kJ/mol |
| Dissolution of NaOH | −44 kJ/mol |
| Vaporization of water | +44 kJ/mol at 25°C |
| Formation of water from H₂+O₂ | −286 kJ/mol |

## Calorimetry

### Coffee-cup Calorimeter (constant P)
```
q = mcΔT
q_rxn = −q_solution = −m·c·ΔT
ΔH = q_rxn / moles
```

### Bomb Calorimeter (constant V)
```
q_rxn = −C_calorimeter × ΔT
q_rxn = ΔU (not ΔH; correct: ΔH = ΔU + ΔnRT)
```

**Specific heat capacities**:
| Substance | c (J/g·K) |
|-----------|-----------|
| Water (l) | 4.184 |
| Water (s) | 2.09 |
| Water (g) | 2.01 |
| Aluminum | 0.897 |
| Iron | 0.449 |
| Copper | 0.385 |

## Entropy (S)

### What Entropy Measures
Entropy is a measure of the dispersal of energy and matter; related to number of microstates (W):
```
S = kB ln W    (Boltzmann's equation)
```

### Predicting Entropy Changes
ΔS > 0 (increases) when:
- Solids dissolve into solution
- Gases are produced from solids/liquids
- Moles of gas increase (Δn_gas > 0)
- Temperature increases
- Larger, more complex molecules form

ΔS < 0 (decreases) when:
- Gases condense or dissolve
- Moles of gas decrease
- Crystallization occurs

### Standard Entropy (S°)
Absolute entropy at 25°C, 1 bar (unlike ΔH°f, NOT zero for elements)
```
ΔS°rxn = Σ S°(products) − Σ S°(reactants)
```

### Entropy of Surroundings
```
ΔS_surr = −ΔH_sys / T
```

## Gibbs Free Energy (G)

Combines enthalpy and entropy into a single criterion for spontaneity at constant T and P.

```
ΔG = ΔH − TΔS
```

| ΔG | Spontaneity |
|----|------------|
| < 0 | Spontaneous (forward) |
| = 0 | Equilibrium |
| > 0 | Non-spontaneous (reverse is spontaneous) |

### Analysis by Sign of ΔH and ΔS
| ΔH | ΔS | ΔG = ΔH − TΔS | Spontaneous? |
|----|-----|----------------|--------------|
| − | + | Always − | Always spontaneous |
| − | − | − at low T; + at high T | Spontaneous at low T |
| + | + | + at low T; − at high T | Spontaneous at high T |
| + | − | Always + | Never spontaneous |

### Standard Gibbs Free Energy
```
ΔG°rxn = Σ ΔG°f(products) − Σ ΔG°f(reactants)
ΔG°rxn = ΔH°rxn − TΔS°rxn
```

### ΔG and Equilibrium Constant
```
ΔG° = −RT ln K
K = e^(−ΔG°/RT)
```

| ΔG° | K |
|-----|---|
| Negative (large) | K >> 1 (products favored) |
| 0 | K = 1 |
| Positive (large) | K << 1 (reactants favored) |

### ΔG under Non-Standard Conditions
```
ΔG = ΔG° + RT ln Q
```
At equilibrium (Q = K): ΔG = 0 (consistent with ΔG° = −RT ln K)

## Temperature and Equilibrium: van 't Hoff Equation

```
ln(K₂/K₁) = −ΔH°/R × (1/T₂ − 1/T₁)
```

- Exothermic reaction (ΔH° < 0): K decreases as T increases
- Endothermic reaction (ΔH° > 0): K increases as T increases

## Thermodynamic vs. Kinetic Control

- **Thermodynamic product**: most stable (lowest ΔG); favored at high T, long times
- **Kinetic product**: formed fastest (lowest Ea); favored at low T, short times

Example: addition of HBr to 1,3-butadiene
- Kinetic: 1,2-addition product (formed at −78°C)
- Thermodynamic: 1,4-addition product (favored at 40°C)

## Maxwell-Boltzmann Distribution

- Distribution of molecular speeds in a gas at temperature T
- Average speed: v_avg = √(8RT/πM)
- Root mean square speed: v_rms = √(3RT/M)
- Most probable speed: v_mp = √(2RT/M)

Higher T → distribution shifts to higher speeds; increased fraction exceeding activation energy Ea
