# Electrochemistry

## Oxidation-Reduction (Redox) Reactions

In redox reactions, electrons are transferred between species.

- **Oxidation**: loss of electrons (OIL — Oxidation Is Loss); oxidation number increases
- **Reduction**: gain of electrons (RIG — Reduction Is Gain); oxidation number decreases
- **Oxidizing agent**: accepts electrons; gets reduced
- **Reducing agent**: donates electrons; gets oxidized

### Oxidation Numbers (Oxidation States)
Rules (in order of priority):
1. Pure element: 0
2. Monatomic ion: equal to charge
3. O: −2 (except peroxides: −1; OF₂: +2)
4. H: +1 (except metal hydrides: −1)
5. F: always −1
6. Sum = charge of species (0 for neutral, = charge for ion)

**Examples**:
- Cr in Cr₂O₇²⁻: 2x + 7(−2) = −2 → x = +6 (Cr₂O₇²⁻ = dichromate)
- Mn in KMnO₄: +1 + x + 4(−2) = 0 → x = +7 (permanganate)
- S in SO₄²⁻: x + 4(−2) = −2 → x = +6

## Balancing Redox Equations (Half-Reaction Method)

### Acidic Solution
1. Separate into oxidation and reduction half-reactions
2. Balance atoms (not O, not H)
3. Balance O by adding H₂O
4. Balance H by adding H⁺
5. Balance charge by adding e⁻
6. Multiply to equalize electrons in both half-reactions
7. Add half-reactions; cancel species appearing on both sides

**Example**: MnO₄⁻ + Fe²⁺ → Mn²⁺ + Fe³⁺ (acidic)

Reduction: MnO₄⁻ → Mn²⁺
MnO₄⁻ → Mn²⁺ + 4H₂O (balance O)
MnO₄⁻ + 8H⁺ → Mn²⁺ + 4H₂O (balance H)
MnO₄⁻ + 8H⁺ + 5e⁻ → Mn²⁺ + 4H₂O (balance charge)

Oxidation: Fe²⁺ → Fe³⁺ + e⁻

Multiply oxidation × 5: 5Fe²⁺ → 5Fe³⁺ + 5e⁻

Add: MnO₄⁻ + 8H⁺ + 5Fe²⁺ → Mn²⁺ + 4H₂O + 5Fe³⁺ ✓

### Basic Solution
After balancing as in acid, add equal OH⁻ to both sides to neutralize H⁺ → form H₂O

## Electrochemical Cells

### Galvanic (Voltaic) Cell
Spontaneous redox reaction generates electrical energy.

**Components**:
- **Anode**: oxidation occurs (negative electrode in galvanic cell)
- **Cathode**: reduction occurs (positive electrode in galvanic cell)
- **Salt bridge** or porous disk: maintains electrical neutrality (anions migrate to anode side, cations to cathode side)
- **External circuit**: electrons flow from anode to cathode

**Cell notation (line notation)**:
Zn | Zn²⁺(1M) ‖ Cu²⁺(1M) | Cu
(anode | anode solution ‖ cathode solution | cathode)

**Daniel Cell** (classic example):
- Anode: Zn(s) → Zn²⁺(aq) + 2e⁻  (oxidation)
- Cathode: Cu²⁺(aq) + 2e⁻ → Cu(s)  (reduction)
- Overall: Zn(s) + Cu²⁺(aq) → Zn²⁺(aq) + Cu(s)
- E°cell = +1.10 V

### Standard Reduction Potentials (E°)
Measured relative to standard hydrogen electrode (SHE = 0.00 V):
2H⁺(1M) + 2e⁻ → H₂(g, 1 atm)   E° = 0.00 V

| Half-reaction | E° (V) |
|--------------|--------|
| F₂ + 2e⁻ → 2F⁻ | +2.87 |
| MnO₄⁻ + 8H⁺ + 5e⁻ → Mn²⁺ + 4H₂O | +1.51 |
| Cl₂ + 2e⁻ → 2Cl⁻ | +1.36 |
| Cr₂O₇²⁻ + 14H⁺ + 6e⁻ → 2Cr³⁺ + 7H₂O | +1.33 |
| O₂ + 4H⁺ + 4e⁻ → 2H₂O | +1.23 |
| Cu²⁺ + 2e⁻ → Cu | +0.34 |
| 2H⁺ + 2e⁻ → H₂ | 0.00 |
| Ni²⁺ + 2e⁻ → Ni | −0.26 |
| Fe²⁺ + 2e⁻ → Fe | −0.44 |
| Zn²⁺ + 2e⁻ → Zn | −0.76 |
| Al³⁺ + 3e⁻ → Al | −1.66 |
| Mg²⁺ + 2e⁻ → Mg | −2.37 |
| Na⁺ + e⁻ → Na | −2.71 |
| Li⁺ + e⁻ → Li | −3.04 |

Higher E° → better oxidizing agent; lower E° → better reducing agent

### Calculating E°cell
```
E°cell = E°cathode − E°anode = E°reduction(cathode) − E°reduction(anode)
```

E°cell > 0 → spontaneous (galvanic cell); E°cell < 0 → non-spontaneous (electrolytic cell)

### Relationship to Thermodynamics
```
ΔG° = −nFE°cell
ΔG° = −RT ln K
∴ E°cell = (RT/nF) ln K = (0.0592/n) log K   (at 25°C)
```
- n = number of electrons transferred
- F = 96,485 C/mol (Faraday's constant)

| E°cell | ΔG° | K |
|--------|-----|---|
| > 0 | < 0 | > 1 |
| = 0 | = 0 | = 1 |
| < 0 | > 0 | < 1 |

## Nernst Equation

Cell potential under non-standard conditions:
```
E = E° − (RT/nF) ln Q = E° − (0.0592/n) log Q    (at 25°C)
```

At equilibrium: E = 0, Q = K → E° = (0.0592/n) log K

**Concentration cells**: identical electrodes but different concentrations; spontaneous until [solute] equalizes.
E = −(0.0592/n) log([dilute]/[concentrated])

## Electrolytic Cells

Non-spontaneous reaction driven by external electrical energy.

- **Anode**: oxidation (connected to + terminal of battery)
- **Cathode**: reduction (connected to − terminal)

### Faraday's Laws of Electrolysis

**First Law**: mass of substance deposited is proportional to charge passed:
```
q = I × t    (charge = current × time, in coulombs)
moles of e⁻ = q / F = I·t / 96485
```

**Second Law**: mass deposited proportional to molar mass / charge (equivalents)

**Example**: How long to deposit 1.00 g Cu from CuSO₄ at 0.500 A?
- Cu²⁺ + 2e⁻ → Cu; MW = 63.55 g/mol
- Moles Cu = 1.00/63.55 = 0.01574 mol
- Moles e⁻ = 2 × 0.01574 = 0.03148 mol
- q = 0.03148 × 96485 = 3036 C
- t = 3036/0.500 = **6072 s ≈ 101 min**

### Industrial Electrolysis

| Process | Electrolyte | Cathode product | Anode product |
|---------|------------|----------------|--------------|
| Chlor-alkali | Brine (NaCl aq) | H₂ + NaOH | Cl₂ |
| Hall-Héroult (Al) | Al₂O₃ in cryolite melt | Al | O₂ (anode consumed) |
| Electroplating | Metal salt | Deposited metal | Metal dissolves |
| Electrorefining | Crude metal | Pure metal | Impurities fall off |
| Water electrolysis | H₂O/H₂SO₄ | H₂ | O₂ |

## Batteries

### Primary Batteries (non-rechargeable)

| Battery | Anode | Cathode | E° | Use |
|---------|-------|---------|-----|-----|
| Alkaline (Zn-MnO₂) | Zn | MnO₂ | ~1.5 V | General purpose |
| Silver oxide | Zn | Ag₂O | 1.55 V | Watches |
| Lithium | Li | MnO₂/CFₓ | 3.0 V | Long shelf life |

### Secondary Batteries (rechargeable)

| Battery | Anode | Cathode | Voltage | Use |
|---------|-------|---------|---------|-----|
| Lead-acid | Pb | PbO₂ | 2 V/cell | Car batteries |
| Ni-Cd | Cd | NiO(OH) | 1.25 V | Power tools |
| Ni-MH | MH (metal hydride) | NiO(OH) | 1.25 V | Hybrid vehicles |
| Li-ion | Graphite (Li intercalation) | LiCoO₂ | 3.6 V | Electronics, EVs |

### Lead-Acid Battery
- 6 cells × 2V = 12V total
- Discharge: Pb + PbO₂ + 2H₂SO₄ → 2PbSO₄ + 2H₂O
- Charge: reverse reaction using external current

### Fuel Cells
Convert chemical energy of fuel directly to electricity.

**Hydrogen fuel cell**:
- Anode: H₂ → 2H⁺ + 2e⁻
- Cathode: O₂ + 4H⁺ + 4e⁻ → 2H₂O
- E°cell = +1.23 V; product is water
- Efficiency ~60% (vs. ~25–40% combustion)

## Corrosion

Corrosion is electrochemical oxidation of metals.

**Rusting of iron**:
- Anode: Fe → Fe²⁺ + 2e⁻
- Cathode: O₂ + 4H⁺ + 4e⁻ → 2H₂O (or O₂ + 2H₂O + 4e⁻ → 4OH⁻)
- Net: 4Fe + 3O₂ + 6H₂O → 4Fe(OH)₃ → 2Fe₂O₃·3H₂O (rust)
- Requires both O₂ and moisture; salt water accelerates (increases conductivity)

### Corrosion Prevention
- **Galvanizing**: coat with zinc (sacrificial anode)
- **Sacrificial anode**: attach more active metal (Mg, Zn); it oxidizes instead
- **Cathodic protection**: apply external negative charge
- **Passivation**: protective oxide layer (Al₂O₃ on Al; Cr₂O₃ on stainless steel)
- **Coatings**: paint, plating (chromium, nickel), anodizing

## Activity Series

Metals ranked by reducing power (ability to displace H₂ from acid or other metals from solution):

Li > K > Ba > Sr > Ca > Na > Mg > Al > Mn > Zn > Cr > Fe > Cd > Co > Ni > Sn > Pb > H > Cu > Ag > Hg > Pt > Au

- Metals above H₂: react with acid to produce H₂
- Metal A will displace metal B from solution if A is above B
