# Stoichiometry

## The Mole Concept

**1 mole** = 6.022 × 10²³ entities (Avogadro's number, Nₐ)

This is the bridge between atomic/molecular scale and laboratory scale.

### Key Conversions
```
moles = mass (g) / molar mass (g/mol)
moles = number of particles / Nₐ
moles of gas = volume (L) / 22.4 L/mol (at STP: 0°C, 1 atm)
```

**Molar mass** = sum of atomic masses of all atoms in formula (units: g/mol)
- Example: H₂SO₄ = 2(1.008) + 32.07 + 4(16.00) = **98.09 g/mol**

### STP vs. SATP
| Condition | T | P | Molar volume |
|-----------|---|---|--------------|
| STP (IUPAC old) | 0°C (273.15 K) | 1 atm | 22.414 L/mol |
| STP (IUPAC 1982) | 0°C | 100 kPa | 22.711 L/mol |
| SATP | 25°C | 100 kPa | 24.789 L/mol |

## Chemical Formulas

### Empirical vs. Molecular Formula
- **Empirical formula**: simplest whole-number ratio of atoms (e.g., CH₂O for glucose)
- **Molecular formula**: actual number of atoms (e.g., C₆H₁₂O₆ for glucose)
- Molecular formula = n × empirical formula (n = molecular mass / empirical formula mass)

### Finding Empirical Formula from % Composition
1. Assume 100 g sample → % becomes grams
2. Convert grams to moles: mol = g / molar mass
3. Divide all moles by smallest value to get ratios
4. Round to nearest whole number (or multiply to clear fractions)

**Example**: Compound: 40.0% C, 6.7% H, 53.3% O
- C: 40.0/12.01 = 3.33 mol → 3.33/3.33 = 1
- H: 6.7/1.008 = 6.65 mol → 6.65/3.33 = 2
- O: 53.3/16.00 = 3.33 mol → 3.33/3.33 = 1
- Empirical formula: **CH₂O** (formaldehyde, glucose, acetic acid, etc.)

## Balancing Chemical Equations

### Conservation Laws
- **Mass**: atoms of each element equal on both sides
- **Charge**: for ionic equations, total charge equal on both sides

### Methods
1. **Inspection (trial and error)**: adjust coefficients intuitively
2. **Algebraic method**: assign variables as coefficients, solve system of equations
3. **Half-reaction method**: for redox reactions (see Electrochemistry chapter)

### Steps for Balancing by Inspection
1. Write unbalanced skeleton equation
2. Start with most complex molecule
3. Balance metals, then nonmetals, then H, then O
4. Check all atoms balance; ensure lowest whole-number coefficients

**Example**: C₃H₈ + O₂ → CO₂ + H₂O

Balance C: C₃H₈ + O₂ → **3**CO₂ + H₂O  
Balance H: C₃H₈ + O₂ → 3CO₂ + **4**H₂O  
Balance O: C₃H₈ + **5**O₂ → 3CO₂ + 4H₂O ✓

## Stoichiometric Calculations

### Mole Ratio Method
Convert between any two quantities in a reaction using mole ratios from balanced equation.

```
given substance → moles given → moles wanted → wanted quantity
```

**Example**: How many grams of H₂O form from 5.00 g H₂?
- 2H₂ + O₂ → 2H₂O
- 5.00 g H₂ × (1 mol H₂/2.016 g) × (2 mol H₂O/2 mol H₂) × (18.02 g H₂O/1 mol H₂O)
- = **44.7 g H₂O**

## Limiting Reagent

The reactant that is completely consumed first and limits the amount of product formed.

### Finding the Limiting Reagent
**Method 1**: Calculate moles of product each reactant would produce; smallest = limiting reagent
**Method 2**: Divide moles of each reactant by its stoichiometric coefficient; smallest ratio = limiting

**Example**: 3.0 mol N₂ + 6.0 mol H₂ → NH₃  
N₂ + 3H₂ → 2NH₃
- N₂: 3.0/1 = 3.0
- H₂: 6.0/3 = 2.0 ← **smaller → H₂ is limiting**
- NH₃ produced: 6.0 mol H₂ × (2 mol NH₃/3 mol H₂) = 4.0 mol NH₃

**Excess reagent**: N₂ used = 6.0 mol H₂ × (1 mol N₂/3 mol H₂) = 2.0 mol; excess = 3.0 − 2.0 = **1.0 mol N₂**

## Percent Yield

```
% yield = (actual yield / theoretical yield) × 100%
```

- **Theoretical yield**: calculated amount assuming complete reaction with no losses
- **Actual yield**: experimentally measured amount
- % yield ≤ 100% (losses from incomplete reaction, side reactions, mechanical losses)

**Example**: Theoretical yield = 25.0 g; actual yield = 21.3 g
→ % yield = (21.3/25.0) × 100% = **85.2%**

## Solution Stoichiometry

### Concentration Units

| Unit | Formula | Typical Use |
|------|---------|-------------|
| Molarity (M) | mol solute / L solution | Most common lab unit |
| Molality (m) | mol solute / kg solvent | Colligative properties |
| Mole fraction (χ) | mol A / total mol | Vapor pressure, gas mixtures |
| Mass percent (w/w%) | (g solute / g solution) × 100 | Industrial/commercial |
| Parts per million (ppm) | mg solute / L solution (aq) | Trace analysis |

### Dilution
```
M₁V₁ = M₂V₂
```
(moles of solute before = moles after)

**Example**: Prepare 500. mL of 0.100 M HCl from 12.0 M HCl
V₁ = M₂V₂/M₁ = (0.100 × 0.500)/12.0 = **4.17 mL** of concentrated HCl

### Titration Calculations
At equivalence point, moles of acid = moles of base (for 1:1 reactions)

```
MₐVₐ = MbVb   (for monoprotic acid + monobasic base)
```

**Example**: 25.00 mL of HCl titrated with 0.1500 M NaOH; equivalence at 32.47 mL
M(HCl) = (0.1500 × 32.47) / 25.00 = **0.1948 M**

## Colligative Properties

Properties that depend on number of solute particles, not identity.

| Property | Formula | Notes |
|----------|---------|-------|
| Vapor pressure lowering | ΔP = χsolute × P°solvent | Raoult's Law |
| Boiling point elevation | ΔTb = Kb·m·i | Kb: ebullioscopic constant |
| Freezing point depression | ΔTf = Kf·m·i | Kf: cryoscopic constant |
| Osmotic pressure | π = MRT·i | π in atm, M in mol/L |

**i** = van 't Hoff factor (number of particles per formula unit)
- NaCl: i = 2 (Na⁺ + Cl⁻); CaCl₂: i = 3; glucose: i = 1

### Common Kf and Kb Values
| Solvent | Kf (°C/m) | Kb (°C/m) |
|---------|-----------|-----------|
| Water | 1.86 | 0.512 |
| Benzene | 5.12 | 2.53 |
| Cyclohexane | 20.0 | 2.79 |

**Example**: 50.0 g NaCl in 1.000 kg water — ΔTf?  
m = (50.0/58.44) mol / 1.000 kg = 0.855 m; i = 2  
ΔTf = 1.86 × 0.855 × 2 = **3.18°C** → FP = −3.18°C

## Percent Composition

```
% element = (n × molar mass of element / molar mass of compound) × 100%
```

**Example**: % N in NH₄NO₃ (MM = 80.04 g/mol)  
= 2 × 14.01 / 80.04 × 100% = **35.00% N**

## Gas Stoichiometry

At non-STP conditions, use ideal gas law: PV = nRT

**Example**: What volume of CO₂ (at 25°C, 1.00 atm) from 10.0 g CaCO₃?  
CaCO₃ → CaO + CO₂  
n(CO₂) = 10.0/100.09 = 0.0999 mol  
V = nRT/P = (0.0999 × 0.08206 × 298) / 1.00 = **2.45 L**
