# Acids and Bases

## Definitions

### Arrhenius (1884)
- **Acid**: produces H⁺ in aqueous solution (e.g., HCl → H⁺ + Cl⁻)
- **Base**: produces OH⁻ in aqueous solution (e.g., NaOH → Na⁺ + OH⁻)
- Limited to aqueous solutions

### Brønsted-Lowry (1923)
- **Acid**: proton (H⁺) donor
- **Base**: proton (H⁺) acceptor
- Applies to non-aqueous systems; emphasizes conjugate pairs

**Conjugate acid-base pair**: differ by one H⁺
- Example: HCl (acid) / Cl⁻ (conjugate base)
- Example: NH₃ (base) / NH₄⁺ (conjugate acid)
- Stronger acid → weaker conjugate base

**Amphoteric species**: can act as acid or base (e.g., H₂O, HCO₃⁻, HSO₄⁻)

### Lewis (1923)
- **Acid**: electron pair acceptor (Lewis acid)
- **Base**: electron pair donor (Lewis base)
- Broadest definition; includes reactions with no H⁺ transfer
- Examples: BF₃ (Lewis acid, empty orbital), NH₃ (Lewis base, lone pair)
- Metal cations are Lewis acids; ligands are Lewis bases

## The pH Scale

```
pH = −log[H⁺]    [H⁺] = 10^(−pH)
pOH = −log[OH⁻]  [OH⁻] = 10^(−pOH)
pH + pOH = 14.00  (at 25°C)
Kw = [H⁺][OH⁻] = 1.0 × 10⁻¹⁴
```

| pH | [H⁺] | Solution type |
|----|------|---------------|
| 0 | 1 M | Very strongly acidic |
| 3 | 10⁻³ M | Strongly acidic (vinegar) |
| 7 | 10⁻⁷ M | Neutral (pure water) |
| 9 | 10⁻⁹ M | Mildly basic (baking soda) |
| 14 | 10⁻¹⁴ M | Very strongly basic (conc. NaOH) |

## Strong Acids and Bases

**Strong acids** (essentially 100% dissociation):
HCl, HBr, HI, HNO₃, H₂SO₄ (first H), HClO₄, HClO₃

**Strong bases** (essentially 100% dissociation):
Group 1 hydroxides: LiOH, NaOH, KOH, RbOH, CsOH
Group 2 hydroxides (heavy): Ca(OH)₂, Sr(OH)₂, Ba(OH)₂

**pH of strong acid**: pH = −log[H⁺] = −log[HA]
**pH of strong base**: pOH = −log[OH⁻], then pH = 14 − pOH

## Weak Acids

Weak acids partially dissociate:
HA ⇌ H⁺ + A⁻
```
Ka = [H⁺][A⁻] / [HA]
pKa = −log Ka
```

Lower pKa (or higher Ka) → stronger acid

### Common Weak Acids
| Acid | Formula | Ka | pKa |
|------|---------|-----|-----|
| Acetic | CH₃COOH | 1.8 × 10⁻⁵ | 4.74 |
| Formic | HCOOH | 1.8 × 10⁻⁴ | 3.74 |
| Benzoic | C₆H₅COOH | 6.3 × 10⁻⁵ | 4.20 |
| Hydrofluoric | HF | 7.2 × 10⁻⁴ | 3.14 |
| Carbonic (Ka₁) | H₂CO₃ | 4.3 × 10⁻⁷ | 6.37 |
| Ammonium | NH₄⁺ | 5.6 × 10⁻¹⁰ | 9.25 |
| Phenol | C₆H₅OH | 1.3 × 10⁻¹⁰ | 9.89 |
| Water | H₂O | ~10⁻¹⁵·⁷ | 15.7 |

### Calculating pH of Weak Acid
**Example**: 0.100 M acetic acid, Ka = 1.8 × 10⁻⁵

ICE:
|  | CH₃COOH | H⁺ | CH₃COO⁻ |
|--|---------|-----|---------|
| I | 0.100 | 0 | 0 |
| C | −x | +x | +x |
| E | 0.100−x | x | x |

Ka = x²/(0.100−x) ≈ x²/0.100 (assuming x << 0.100)
x = √(1.8×10⁻⁵ × 0.100) = √(1.8×10⁻⁶) = 1.34 × 10⁻³ M
Check: 1.34×10⁻³/0.100 = 1.34% < 5% ✓
pH = −log(1.34×10⁻³) = **2.87**
% dissociation = 1.34%

### Percent Dissociation
```
% dissociation = [H⁺]eq / [HA]₀ × 100%
```
- Increases as concentration decreases (dilution law)

## Weak Bases

B + H₂O ⇌ BH⁺ + OH⁻
```
Kb = [BH⁺][OH⁻] / [B]
```

**Common weak bases**: NH₃ (Kb = 1.8×10⁻⁵), amines (RNH₂, R₂NH, R₃N), pyridine

**Calculating pH of weak base**: same ICE approach, find [OH⁻], then pOH, then pH

## Polyprotic Acids

Acids with more than one ionizable proton; Ka₁ > Ka₂ > Ka₃ (each subsequent ionization harder)

| Acid | Ka₁ | Ka₂ | Ka₃ |
|------|-----|-----|-----|
| H₂SO₄ | Large (strong) | 1.2×10⁻² | — |
| H₂CO₃ | 4.3×10⁻⁷ | 4.7×10⁻¹¹ | — |
| H₃PO₄ | 7.5×10⁻³ | 6.2×10⁻⁸ | 4.8×10⁻¹³ |
| H₂S | 1.0×10⁻⁷ | ~10⁻¹⁷ | — |

For most calculations, contribution of Ka₂ to [H⁺] is negligible.

## Acid-Base Properties of Salts (Hydrolysis)

Salt from strong acid + strong base → **neutral solution** (e.g., NaCl → pH 7)
Salt from weak acid + strong base → **basic solution** (A⁻ hydrolyzes: A⁻ + H₂O ⇌ HA + OH⁻)
Salt from strong acid + weak base → **acidic solution** (BH⁺ hydrolyzes: BH⁺ ⇌ B + H⁺)
Salt from weak acid + weak base → depends on Ka vs. Kb

### Hydrolysis of Metal Ions
Metal ions act as Lewis acids; coordinate water molecules donate H⁺:
[Fe(H₂O)₆]³⁺ ⇌ [Fe(H₂O)₅OH]²⁺ + H⁺
→ High charge density cations (Al³⁺, Fe³⁺) produce acidic solutions

## Buffer Solutions

### Definition
A buffer resists pH changes when small amounts of acid or base are added. Contains:
- Weak acid + its conjugate base (acidic buffer)
- Weak base + its conjugate acid (basic buffer)

### Henderson-Hasselbalch Equation
```
pH = pKa + log([A⁻]/[HA])
```

- pH = pKa when [A⁻] = [HA] (equal concentrations)
- Buffer range: pH = pKa ± 1

### Buffer Capacity
- Maximum when [A⁻]/[HA] = 1 (ratio closest to 1)
- Increases with higher concentrations of buffer components
- Choose weak acid with pKa closest to desired pH

### Common Buffers
| Buffer system | pH range | Use |
|--------------|----------|-----|
| Acetic acid/acetate | 3.7–5.8 | Lab, food preservation |
| Phosphate (H₂PO₄⁻/HPO₄²⁻) | 6.2–8.2 | Biological systems, PBS |
| Carbonate/bicarbonate | 6.4–10.3 | Blood, geological systems |
| TRIS | 7.0–9.0 | Biochemistry |
| Ammonia/ammonium | 8.2–10.2 | Lab |

### Buffer Calculation Example
Prepare pH 5.00 buffer using acetic acid (pKa = 4.74):
pH = pKa + log([A⁻]/[HA])
5.00 = 4.74 + log(ratio)
log(ratio) = 0.26 → ratio = 10^0.26 = 1.82
Use [CH₃COO⁻]/[CH₃COOH] = 1.82 (e.g., 0.182 M acetate + 0.100 M acetic acid)

## Acid-Base Titrations

### Strong Acid/Strong Base
- Equivalence point: pH = 7.00
- Sharp endpoint; any indicator near pH 7 works
- Before equivalence: pH set by excess acid
- After equivalence: pH set by excess base

### Weak Acid/Strong Base
- Equivalence point: pH > 7 (conjugate base hydrolyzes)
- At half-equivalence point: pH = pKa (buffer region maximum)
- Gradual pH rise; need indicator with color change at correct pH

### Weak Base/Strong Acid
- Equivalence point: pH < 7
- At half-equivalence: pH = pKa (of conjugate acid) = 14 − pKb

### Indicators
Weak acids where HIn (one color) ⇌ H⁺ + In⁻ (different color)
Useful range: pKa(indicator) ± 1

| Indicator | pH range | Acid color | Base color |
|-----------|----------|-----------|-----------|
| Methyl orange | 3.1–4.4 | Red | Yellow |
| Methyl red | 4.4–6.2 | Red | Yellow |
| Bromothymol blue | 6.0–7.6 | Yellow | Blue |
| Phenolphthalein | 8.2–10.0 | Colorless | Pink |
| Thymolphthalein | 9.4–10.6 | Colorless | Blue |

## Relative Acid Strength

**Oxyacids (same central atom)**: more oxygens → stronger acid (pulls electron density from O–H bond)
HClO < HClO₂ < HClO₃ < HClO₄

**Oxyacids (same structure)**: higher EN central atom → stronger acid
H₂SO₄ > H₂SeO₄ > H₂TeO₄

**Binary acids (H-X)**: larger/less electronegative X → stronger acid (bond strength dominates in non-aqueous)
HI > HBr > HCl > HF (in water: bond strength effect dominates)

**Organic acids**: electron-withdrawing groups increase acidity; electron-donating groups decrease it
- Cl₃CCOOH (Ka = 0.23) > Cl₂CHCOOH > ClCH₂COOH > CH₃COOH (Ka = 1.8×10⁻⁵)

## Superacids and Superbases

**Superacids**: stronger than 100% sulfuric acid
- Magic acid: FSO₃H + SbF₅
- Fluorosulfuric acid: FSO₃H
- Protonates hydrocarbons, noble gas compounds

**Superbases**: stronger than NaOH
- Butyllithium (nBuLi), lithium diisopropylamide (LDA)
- Deprotonates C–H bonds in organic chemistry
