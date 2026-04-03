# Gas Laws and Kinetic Molecular Theory

## The Gaseous State

Gases are the simplest state of matter to model mathematically. Gas molecules move freely, occupy the full volume of their container, and exert pressure through collisions with container walls. Understanding gas behavior is essential for chemistry, engineering, atmospheric science, and medicine.

### Properties of Gases

| Property | Symbol | SI Unit |
|----------|--------|---------|
| Pressure | P | Pascal (Pa); 1 atm = 101,325 Pa = 760 mmHg = 760 torr |
| Volume | V | cubic meters (m³); commonly liters (L) |
| Temperature | T | Kelvin (K); K = °C + 273.15 |
| Amount | n | moles (mol) |

**Standard conditions:**
- **STP** (Standard Temperature and Pressure): 0 °C (273.15 K), 1 atm. Molar volume = 22.414 L/mol
- **SATP** (Standard Ambient): 25 °C (298.15 K), 1 bar (0.9869 atm). Molar volume = 24.79 L/mol

---

## The Empirical Gas Laws

### Boyle's Law (1662) — Pressure-Volume Relationship

At constant temperature and amount:

**P₁V₁ = P₂V₂**

- Pressure and volume are inversely proportional
- Doubling pressure halves volume
- Graph of P vs. V produces a hyperbola; P vs. 1/V is linear

**Example:** A gas occupies 4.0 L at 2.0 atm. At 8.0 atm (constant T):
V₂ = (2.0 × 4.0) / 8.0 = 1.0 L

### Charles's Law (1787) — Temperature-Volume Relationship

At constant pressure and amount:

**V₁/T₁ = V₂/T₂**

- Volume is directly proportional to absolute temperature (Kelvin)
- Extrapolation to zero volume defines absolute zero (−273.15 °C)
- Temperature MUST be in Kelvin

**Example:** A balloon at 300 K occupies 6.0 L. At 450 K:
V₂ = 6.0 × (450/300) = 9.0 L

### Gay-Lussac's Law — Pressure-Temperature Relationship

At constant volume and amount:

**P₁/T₁ = P₂/T₂**

- Pressure is directly proportional to absolute temperature
- Explains why sealed containers can rupture when heated

### Avogadro's Law (1811) — Volume-Amount Relationship

At constant temperature and pressure:

**V₁/n₁ = V₂/n₂**

- Equal volumes of gases at the same T and P contain equal numbers of molecules
- The molar volume at STP (22.414 L) is the same for all ideal gases

### Combined Gas Law

Merging Boyle's, Charles's, and Gay-Lussac's laws:

**P₁V₁/T₁ = P₂V₂/T₂**

Useful when pressure, volume, AND temperature all change simultaneously.

---

## The Ideal Gas Law

**PV = nRT**

Where R = 0.08206 L·atm/(mol·K) = 8.314 J/(mol·K)

### Density Form

Since n = m/M (mass/molar mass):

**PM = dRT**    or    **d = PM/(RT)**

Where d = density (g/L), M = molar mass (g/mol)

### Molar Mass Determination

**M = dRT/P = mRT/(PV)**

This allows experimental determination of molar mass by measuring gas density.

### Mole Fraction and Partial Pressure

**Mole fraction:** χᵢ = nᵢ / n_total

**Partial pressure:** Pᵢ = χᵢ × P_total

---

## Dalton's Law of Partial Pressures

**P_total = P₁ + P₂ + P₃ + ...**

The total pressure of a gas mixture equals the sum of partial pressures each gas would exert alone in the same container.

### Collecting Gas Over Water

When gas is collected by water displacement:

**P_gas = P_total − P_water**

Water vapor pressure (P_water) depends on temperature and must be subtracted. At 25 °C, P_water = 23.8 mmHg.

---

## Kinetic Molecular Theory (KMT)

### Five Postulates

1. **Particle size**: Gas molecules are point particles — their volume is negligible compared to container volume
2. **Random motion**: Molecules move in straight lines in random directions
3. **Elastic collisions**: Collisions between molecules (and with walls) are perfectly elastic — no net energy loss
4. **No intermolecular forces**: Molecules do not attract or repel each other between collisions
5. **Temperature-energy relationship**: Average kinetic energy is directly proportional to absolute temperature

### Maxwell-Boltzmann Distribution

Gas molecules do NOT all move at the same speed. The distribution of molecular speeds at temperature T follows:

- **Most probable speed (v_p):** v_p = √(2RT/M)
- **Average speed (v_avg):** v_avg = √(8RT/(πM))
- **Root-mean-square speed (v_rms):** v_rms = √(3RT/M)

**Order:** v_p < v_avg < v_rms

As temperature increases, the distribution broadens and shifts to higher speeds. Heavier molecules move slower at the same temperature.

### Mean Free Path

The average distance a molecule travels between collisions:

**λ = RT / (√2 · π · d² · Nₐ · P)**

Where d = molecular diameter, Nₐ = Avogadro's number. At 1 atm and 25 °C, λ ≈ 70 nm for N₂.

### Collision Frequency

**Z = v_avg / λ**

For N₂ at STP: ~5 × 10⁹ collisions per second per molecule.

### KMT Derivation of Pressure

From KMT, pressure arises from molecular collisions with walls:

**P = (1/3)(N/V)(m·v_rms²) = nMv_rms² / (3V)**

This directly yields PV = nRT when average KE = (3/2)kT.

---

## Graham's Law of Effusion and Diffusion

### Effusion

Escape of gas through a tiny orifice (hole diameter << mean free path):

**Rate₁/Rate₂ = √(M₂/M₁)**

Lighter gases effuse faster. Used in uranium enrichment (²³⁵UF₆ vs. ²³⁸UF₆).

### Diffusion

Spreading of gas molecules through another gas. Graham's law approximately applies but is complicated by molecular collisions.

**Example:** H₂ (M = 2) effuses √(32/2) = 4 times faster than O₂ (M = 32).

---

## Real Gases

### Deviations from Ideal Behavior

Real gases deviate from PV = nRT because:
1. **Molecules have finite volume** — significant at high pressure
2. **Intermolecular forces exist** — significant at low temperature

**When do gases behave most ideally?**
- High temperature (KE >> IMF strength)
- Low pressure (molecules far apart, volume negligible)

### Compressibility Factor (Z)

**Z = PV/(nRT)**

| Z value | Meaning |
|---------|---------|
| Z = 1 | Ideal behavior |
| Z < 1 | Attractive forces dominate (gas more compressible than ideal) |
| Z > 1 | Repulsive forces / volume effects dominate (gas less compressible) |

All gases approach Z = 1 at low pressure. At moderate pressures, most gases show Z < 1. At very high pressures, Z > 1 for all gases.

### Van der Waals Equation

**(P + a·n²/V²)(V − nb) = nRT**

| Correction | Term | Physical meaning |
|------------|------|------------------|
| Pressure correction | + a·n²/V² | Accounts for intermolecular attractions reducing wall collisions |
| Volume correction | − nb | Accounts for finite molecular volume (excluded volume) |

**Van der Waals constants (selected):**

| Gas | a (L²·atm/mol²) | b (L/mol) |
|-----|------------------|-----------|
| He | 0.034 | 0.0237 |
| H₂ | 0.244 | 0.0266 |
| N₂ | 1.39 | 0.0391 |
| CO₂ | 3.59 | 0.0427 |
| H₂O | 5.46 | 0.0305 |
| NH₃ | 4.17 | 0.0371 |

**Trends:**
- Large **a** → strong IMFs (polar molecules, H-bonding)
- Large **b** → larger molecular size

### Other Real Gas Equations

| Equation | Form | Notes |
|----------|------|-------|
| Redlich-Kwong | P = RT/(V−b) − a/[T^½·V(V+b)] | Better than vdW at high pressures |
| Peng-Robinson | More complex | Industry standard for hydrocarbons |
| Virial | PV = nRT(1 + B/V + C/V² + ...) | Theoretical basis; B, C from statistical mechanics |

---

## Critical Constants and Liquefaction

### Critical Point

Above the **critical temperature (Tc)**, no amount of pressure can liquefy a gas. At T_c:

| Gas | T_c (K) | P_c (atm) | V_c (L/mol) |
|-----|---------|-----------|-------------|
| He | 5.2 | 2.26 | 0.0578 |
| H₂ | 33.2 | 12.8 | 0.0650 |
| N₂ | 126.2 | 33.5 | 0.0901 |
| O₂ | 154.6 | 49.7 | 0.0744 |
| CO₂ | 304.2 | 72.8 | 0.0940 |
| H₂O | 647.3 | 217.7 | 0.0560 |

**Supercritical fluids** (T > Tc, P > Pc) have properties between gas and liquid. Supercritical CO₂ is used as an industrial solvent (decaffeination, dry cleaning, extraction).

### Relationship to Van der Waals Constants

**Tc = 8a/(27Rb)**,  **Pc = a/(27b²)**,  **Vc = 3b**

---

## Gas Stoichiometry

### At STP

At STP (0 °C, 1 atm), 1 mole of ideal gas = 22.414 L.

**Example:** How many liters of O₂ at STP are needed to burn 16.0 g of CH₄?

CH₄ + 2O₂ → CO₂ + 2H₂O

16.0 g CH₄ × (1 mol/16.04 g) × (2 mol O₂/1 mol CH₄) × (22.414 L/mol) = 44.6 L O₂

### At Non-Standard Conditions

Use PV = nRT to convert between moles and volume at any T and P.

---

## Atmospheric Chemistry and Applications

### Composition of Dry Air

| Gas | Mole fraction | Partial pressure at 1 atm |
|-----|---------------|---------------------------|
| N₂ | 0.7808 | 0.7808 atm |
| O₂ | 0.2095 | 0.2095 atm |
| Ar | 0.0093 | 0.0093 atm |
| CO₂ | 0.0004 | 0.0004 atm |

### Barometric Formula

Pressure decreases with altitude:

**P = P₀ · exp(−Mgh/RT)**

Where g = 9.81 m/s², h = altitude. Pressure drops roughly 12% per 1000 m.

### Gas Solubility — Henry's Law

**C = k_H · P_gas**

Gas solubility is proportional to its partial pressure above the solution. Explains:
- Carbonation (CO₂ under pressure)
- The bends (N₂ dissolved in blood at depth)
- Oxygen transport in blood (supplemental O₂ therapy)

---

## Key Equations Summary

| Law/Equation | Formula | Conditions |
|--------------|---------|------------|
| Boyle's | P₁V₁ = P₂V₂ | Constant T, n |
| Charles's | V₁/T₁ = V₂/T₂ | Constant P, n |
| Gay-Lussac's | P₁/T₁ = P₂/T₂ | Constant V, n |
| Avogadro's | V₁/n₁ = V₂/n₂ | Constant T, P |
| Combined | P₁V₁/T₁ = P₂V₂/T₂ | Constant n |
| Ideal Gas | PV = nRT | All variables |
| Dalton's | P_total = ΣPᵢ | Gas mixtures |
| Graham's | Rate₁/Rate₂ = √(M₂/M₁) | Effusion |
| Van der Waals | (P + an²/V²)(V − nb) = nRT | Real gases |
| Henry's | C = k_H · P | Gas solubility |
| RMS speed | v_rms = √(3RT/M) | Molecular speed |
