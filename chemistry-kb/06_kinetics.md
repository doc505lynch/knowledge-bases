# Chemical Kinetics

## Reaction Rates

The **reaction rate** measures how quickly reactants are consumed or products are formed.

For: aA + bB → cC + dD
```
rate = −(1/a)Δ[A]/Δt = −(1/b)Δ[B]/Δt = (1/c)Δ[C]/Δt = (1/d)Δ[D]/Δt
```

- Rates are always positive (concentration of reactant decreasing → negative sign)
- **Average rate**: over a time interval Δt
- **Instantaneous rate**: slope of tangent to [A] vs. t curve at a specific time
- **Initial rate**: instantaneous rate at t = 0 (before significant product buildup)

## Rate Laws

```
rate = k[A]^m[B]^n
```

- **k**: rate constant (temperature dependent, not concentration dependent)
- **m, n**: reaction orders with respect to A and B (usually determined experimentally, not from stoichiometry)
- **Overall order**: m + n

### Determining Rate Law (Method of Initial Rates)
Compare experiments where one concentration is varied while others are held constant.

| Exp | [A] (M) | [B] (M) | Initial Rate (M/s) |
|-----|---------|---------|-------------------|
| 1 | 0.10 | 0.10 | 2.0 × 10⁻³ |
| 2 | 0.20 | 0.10 | 8.0 × 10⁻³ |
| 3 | 0.10 | 0.20 | 2.0 × 10⁻³ |

Exp 2 vs 1: rate doubles twice when [A] doubles → m = 2 (second order in A)
Exp 3 vs 1: rate unchanged when [B] doubles → n = 0 (zero order in B)
→ rate = k[A]²; k = 2.0×10⁻³/(0.10)² = **0.20 M⁻¹s⁻¹**

### Orders and Their Meanings
| Order | Meaning |
|-------|---------|
| 0 | Rate independent of concentration |
| 1 | Rate proportional to concentration |
| 2 | Rate proportional to concentration squared |
| Fractional | Complex mechanism (e.g., 1.5) |
| Negative | Inhibitor or product inhibition |

## Integrated Rate Laws

Relate concentration to time; allow calculation of [A] at any time t.

### Zero Order
```
[A]t = [A]₀ − kt
```
- t₁/₂ = [A]₀/2k (half-life depends on initial concentration)
- Linear plot: [A] vs. t
- Units of k: M·s⁻¹

### First Order
```
ln[A]t = ln[A]₀ − kt   or   [A]t = [A]₀·e^(−kt)
```
- t₁/₂ = ln2/k = 0.693/k (constant; independent of concentration)
- Linear plot: ln[A] vs. t (slope = −k)
- Units of k: s⁻¹
- Radioactive decay is first order

### Second Order
```
1/[A]t = 1/[A]₀ + kt
```
- t₁/₂ = 1/(k[A]₀) (depends on initial concentration)
- Linear plot: 1/[A] vs. t (slope = k)
- Units of k: M⁻¹·s⁻¹

### Summary Table
| Order | Integrated Law | Linear Plot | Half-life |
|-------|---------------|-------------|-----------|
| 0 | [A] = [A]₀ − kt | [A] vs t | [A]₀/2k |
| 1 | ln[A] = ln[A]₀ − kt | ln[A] vs t | 0.693/k |
| 2 | 1/[A] = 1/[A]₀ + kt | 1/[A] vs t | 1/(k[A]₀) |

## Factors Affecting Reaction Rate

1. **Concentration**: higher [reactants] → more collisions → faster rate (for orders > 0)
2. **Temperature**: higher T → more energetic collisions → faster rate (k increases)
3. **Physical state/surface area**: finer particles → more surface → faster reaction
4. **Catalysts**: lower activation energy → faster rate (not consumed)
5. **Nature of reactants**: ionic reactions fast; bond-breaking reactions slow

## Collision Theory

For a reaction to occur, molecules must:
1. **Collide** (sufficient concentration and temperature)
2. Have **sufficient energy** ≥ activation energy (Ea)
3. Have **proper orientation** (steric factor)

```
rate = Z · f · p
```
- Z = collision frequency
- f = fraction with E ≥ Ea = e^(−Ea/RT)
- p = steric/orientation factor

## Transition State Theory (Activated Complex Theory)

Reactants → [Transition State / Activated Complex]‡ → Products

- **Activation energy (Ea)**: energy barrier between reactants and transition state
- **Transition state**: highest energy point along reaction coordinate; cannot be isolated
- **Intermediate**: local minimum between steps; can potentially be isolated

### Reaction Coordinate Diagram
```
Energy
  |        ‡
  |       /|\
  |      / | \
  |     /  |  \
  |    /   Ea  \
  | reactants   products
  |
  +------------------------→ Reaction coordinate
```

## Arrhenius Equation

Temperature dependence of the rate constant:
```
k = A·e^(−Ea/RT)
ln k = ln A − Ea/RT
```
- **A** = frequency factor (pre-exponential factor; includes collision frequency and orientation)
- **Ea** = activation energy (J/mol)
- **R** = 8.314 J/mol·K
- **T** = temperature in Kelvin

### Two-Temperature Form
```
ln(k₂/k₁) = (Ea/R)(1/T₁ − 1/T₂)
```

**Rule of thumb**: rate doubles for every 10°C rise (rough approximation; actual depends on Ea)

**Finding Ea**: plot ln k vs. 1/T (Arrhenius plot); slope = −Ea/R

## Reaction Mechanisms

A reaction mechanism is a step-by-step sequence of elementary reactions that add up to the overall reaction.

### Elementary Reactions
Simple, single-step reactions where order equals stoichiometry.

| Molecularity | # reactant species | Example |
|-------------|-------------------|---------|
| Unimolecular | 1 | A → products; rate = k[A] |
| Bimolecular | 2 | A + B → products; rate = k[A][B] |
| Termolecular | 3 | Rare; 3 species collide simultaneously |

### Rate-Determining Step
The slowest step controls the overall rate. The rate law for the mechanism must match the experimentally determined rate law.

### Example Mechanism
Overall: 2NO₂ + F₂ → 2NO₂F (experimental rate = k[NO₂][F₂])

Mechanism:
- Step 1 (slow): NO₂ + F₂ → NO₂F + F·   rate = k₁[NO₂][F₂] ← rate determining
- Step 2 (fast): NO₂ + F· → NO₂F         rate = k₂[NO₂][F·]

Rate law from slow step: rate = k₁[NO₂][F₂] ✓ (matches experimental)

### Intermediates and Steady-State Approximation
**Intermediate**: produced in one step, consumed in another (does not appear in overall equation)
**Steady-state approximation**: d[intermediate]/dt ≈ 0; rate of formation = rate of consumption

### Pre-equilibrium Approximation
If fast equilibrium step precedes the slow step:
K_eq = k_f/k_r for fast step; substitute into rate expression

## Catalysis

### Homogeneous Catalysis
Catalyst in same phase as reactants (e.g., H⁺ in acid-catalyzed reactions)

**Example**: Iodine-catalyzed decomposition of H₂O₂ in acidic solution

### Heterogeneous Catalysis
Catalyst in different phase (usually solid catalyst, gas/liquid reactants)

Steps: **adsorption → activation → reaction → desorption**

**Industrial examples**:
- Haber process: Fe catalyst for N₂ + 3H₂ → 2NH₃
- Contact process: V₂O₅ for SO₂ + ½O₂ → SO₃
- Catalytic converter: Pt/Pd/Rh for NOₓ, CO, hydrocarbon removal

### Enzyme Catalysis (Michaelis-Menten Kinetics)
Enzymes are biological catalysts (proteins).

**Mechanism**: E + S ⇌ ES → E + P
```
rate = Vmax[S] / (Km + [S])
```
- **Vmax**: maximum rate (when enzyme saturated with substrate)
- **Km** (Michaelis constant): [S] at half-maximum rate; reflects enzyme-substrate affinity
- **Lineweaver-Burk plot**: 1/rate vs. 1/[S] → straight line to determine Km and Vmax

### Effect of Catalyst on Energy Profile
- Provides alternative pathway with lower activation energy
- Does NOT change ΔG, ΔH, or equilibrium constant
- Speeds up both forward and reverse reactions equally

## Radioactive Decay (First-Order Kinetics)

```
N(t) = N₀·e^(−λt)
t₁/₂ = 0.693/λ
```
λ = decay constant

**Radiometric dating**: ¹⁴C half-life = 5,730 years (organic materials up to ~50,000 yr)
**Medical imaging**: ⁹⁹ᵐTc t₁/₂ = 6 hr; ¹⁸F-FDG t₁/₂ = 110 min (PET scan)
