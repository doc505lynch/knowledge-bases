# Chemical Equilibrium

## The Concept of Equilibrium

Chemical equilibrium is a dynamic state where forward and reverse reaction rates are equal, and macroscopic properties (concentrations, pressure, color) remain constant.

- Equilibrium is reached from either direction
- Both forward and reverse reactions continue at the molecular level
- Equilibrium does not mean equal concentrations of reactants and products — it means no NET change

## The Equilibrium Constant (K)

For: aA + bB ⇌ cC + dD

### Kc (concentration-based)
```
Kc = [C]^c[D]^d / [A]^a[B]^b
```

### Kp (pressure-based, for gas-phase reactions)
```
Kp = (PC)^c(PD)^d / (PA)^a(PB)^b
```

### Relationship Between Kc and Kp
```
Kp = Kc(RT)^Δn
```
where Δn = moles of gaseous products − moles of gaseous reactants, R = 0.08206 L·atm/mol·K

### Rules for Writing K
1. **Pure solids and pure liquids are excluded** (activity = 1)
2. **Gases**: use partial pressures (Kp) or molar concentrations (Kc)
3. **Aqueous**: use molar concentrations
4. **Water as solvent**: excluded from K expression
5. K is dimensionless (strictly, uses activities)

## Properties of K

### Meaning of K Magnitude
| K value | Interpretation |
|---------|---------------|
| K >> 1 (>10³) | Products strongly favored at equilibrium |
| K ≈ 1 (10⁻³ to 10³) | Both reactants and products present significantly |
| K << 1 (<10⁻³) | Reactants strongly favored at equilibrium |

### Manipulating Equilibrium Expressions
1. **Reverse reaction**: K' = 1/K
2. **Multiply by factor n**: K' = Kⁿ
3. **Add two reactions**: K_total = K₁ × K₂

## The Reaction Quotient (Q)

Q has same form as K but uses non-equilibrium concentrations.

```
Q = [C]^c[D]^d / [A]^a[B]^b  (at any point in time)
```

| Comparison | Direction of reaction |
|-----------|----------------------|
| Q < K | Forward reaction proceeds (more products form) |
| Q = K | System is at equilibrium |
| Q > K | Reverse reaction proceeds (more reactants form) |

## Le Chatelier's Principle

"If a system at equilibrium is disturbed, it will shift to partially counteract the disturbance and reach a new equilibrium."

### Effect of Concentration Change
| Change | Shift |
|--------|-------|
| Add reactant | Forward (→) |
| Remove reactant | Reverse (←) |
| Add product | Reverse (←) |
| Remove product | Forward (→) |

### Effect of Pressure/Volume (Gas Phase)
| Change | Shift |
|--------|-------|
| Increase pressure (decrease V) | Toward side with fewer moles of gas |
| Decrease pressure (increase V) | Toward side with more moles of gas |
| Add inert gas (constant V) | No shift (partial pressures unchanged) |
| Δn_gas = 0 | No shift for pressure changes |

### Effect of Temperature
| Change | Exothermic rxn (ΔH < 0) | Endothermic rxn (ΔH > 0) |
|--------|------------------------|------------------------|
| Increase T | Shifts reverse (←), K decreases | Shifts forward (→), K increases |
| Decrease T | Shifts forward (→), K increases | Shifts reverse (←), K decreases |

Note: Temperature actually changes K (van 't Hoff equation); other factors don't change K.

### Catalysts and Equilibrium
Catalysts lower Ea for both directions equally → reach equilibrium faster but do NOT change K or equilibrium position.

## Equilibrium Calculations (ICE Tables)

ICE = Initial, Change, Equilibrium

**Example**: H₂(g) + I₂(g) ⇌ 2HI(g), Kc = 50.5 at 448°C
Initial: [H₂]₀ = [I₂]₀ = 0.100 M, [HI]₀ = 0

|  | H₂ | I₂ | 2HI |
|--|----|----|-----|
| I | 0.100 | 0.100 | 0 |
| C | −x | −x | +2x |
| E | 0.100−x | 0.100−x | 2x |

Kc = (2x)² / (0.100−x)² = 50.5
√50.5 = 2x/(0.100−x) = 7.106
2x = 0.7106 − 7.106x → 9.106x = 0.7106 → x = 0.0780 M

Equilibrium: [H₂] = [I₂] = 0.022 M; [HI] = 0.156 M

### Simplifying Assumptions
If K is small (K < 10⁻³) and initial concentration is moderate, assume x << [A]₀:
Check: x/[A]₀ < 5% for assumption to be valid

## Specific Equilibrium Types

### Kw — Water Autoionization
```
H₂O ⇌ H⁺ + OH⁻      Kw = [H⁺][OH⁻] = 1.0 × 10⁻¹⁴ at 25°C
```
Pure water: [H⁺] = [OH⁻] = 1.0 × 10⁻⁷ M → pH = 7.00

### Ka — Acid Dissociation Constant
HA ⇌ H⁺ + A⁻
```
Ka = [H⁺][A⁻] / [HA]
pKa = −log(Ka)
```

### Kb — Base Dissociation Constant
B + H₂O ⇌ BH⁺ + OH⁻
```
Kb = [BH⁺][OH⁻] / [B]
```

### Conjugate Acid-Base Pair Relationship
```
Ka × Kb = Kw = 1.0 × 10⁻¹⁴
pKa + pKb = 14
```

### Ksp — Solubility Product
For: MₓAy(s) ⇌ xM^(y+)(aq) + yA^(x−)(aq)
```
Ksp = [M^(y+)]^x[A^(x−)]^y
```

**Molar solubility (s)**: moles of compound that dissolve per liter
- For CaF₂: Ksp = [Ca²⁺][F⁻]² = (s)(2s)² = 4s³
- If Ksp = 3.9 × 10⁻¹¹: s = (3.9×10⁻¹¹/4)^(1/3) = 2.1 × 10⁻⁴ M

**Common ion effect**: Solubility decreases when a common ion is added (Q > Ksp)
**Complex ion formation**: Solubility increases with excess ligand (shifts equilibrium)

### Common Ksp Values (25°C)
| Compound | Ksp |
|----------|-----|
| AgCl | 1.8 × 10⁻¹⁰ |
| BaSO₄ | 1.1 × 10⁻¹⁰ |
| CaF₂ | 3.9 × 10⁻¹¹ |
| PbS | 8 × 10⁻²⁸ |
| Ca(OH)₂ | 6.5 × 10⁻⁶ |
| Mg(OH)₂ | 5.6 × 10⁻¹² |
| Fe(OH)₃ | 2.8 × 10⁻³⁹ |

### Kf — Formation Constant (Complex Ions)
For: M^n+ + xL ⇌ [MLx]^n+
```
Kf = [[MLx]^n+] / ([M^n+][L]^x)
```
Large Kf means very stable complex (e.g., [Fe(CN)₆]⁴⁻: Kf ≈ 10³⁵)

## Equilibria in Industrial Processes

### Haber-Bosch Process
N₂(g) + 3H₂(g) ⇌ 2NH₃(g)   ΔH° = −92 kJ/mol

- Exothermic → low T favors products (thermodynamics)
- Low T → slow rate (kinetics)
- Compromise: **400–500°C**, **150–300 atm**, **Fe catalyst**
- High pressure → fewer gas moles on product side → favors products

### Contact Process (H₂SO₄ production)
2SO₂(g) + O₂(g) ⇌ 2SO₃(g)   ΔH° = −197 kJ/mol
- Conditions: ~450°C, 1–2 atm, V₂O₅ catalyst

### Equilibrium and pH Buffer Systems
H₂CO₃ ⇌ H⁺ + HCO₃⁻ (Ka₁ = 4.3 × 10⁻⁷)
HCO₃⁻ ⇌ H⁺ + CO₃²⁻ (Ka₂ = 4.7 × 10⁻¹¹)
Critical for blood pH regulation (pH 7.35–7.45)
