# Analytical Chemistry

## Overview

Analytical chemistry is divided into two main areas:
- **Qualitative analysis**: identifying what is present
- **Quantitative analysis**: determining how much is present

Key principles: **accuracy** (closeness to true value), **precision** (reproducibility), **sensitivity** (ability to detect low concentrations), **selectivity** (distinguish analyte from matrix)

## Error and Statistics

### Types of Error
- **Systematic (determinate) error**: consistent bias in one direction; can be corrected
  - Instrumental, method, personal errors
- **Random (indeterminate) error**: scatter around true value; reduced by more measurements

### Statistical Analysis
**Mean**: x̄ = Σxᵢ/n  
**Standard deviation**: s = √[Σ(xᵢ−x̄)²/(n−1)]  
**Relative standard deviation (RSD)** = (s/x̄) × 100%  
**Confidence interval**: x̄ ± ts/√n  (t from Student's t-table)

### Accuracy Measures
**Absolute error** = measured − true value  
**Relative error** = (measured − true) / true × 100%  
**% recovery** = (amount found / amount spiked) × 100%

### Calibration Strategies
- **External calibration**: standards separate from sample; simple but subject to matrix effects
- **Standard addition**: add known amounts of analyte to sample; compensates for matrix
- **Internal standard**: add fixed amount of related compound; corrects for sample preparation losses

## Gravimetric Analysis

Analyte precipitated as an insoluble compound, filtered, dried, and weighed.

**Gravimetric factor (GF)** = molar mass of analyte / molar mass of precipitate form
```
mass analyte = mass precipitate × GF
```

**Example**: Determine Cl⁻ by precipitating as AgCl
GF = 35.45 / 143.32 = 0.2474
If 0.5124 g AgCl collected: mass Cl⁻ = 0.5124 × 0.2474 = **0.1268 g**

### Requirements for Good Precipitates
- Low solubility (Ksp < 10⁻⁸ ideally)
- Easily filtered (large crystals; crystalline digestion helps)
- Known stoichiometry
- Stable to heat for drying/ignition

### Common Precipitations
| Ion | Precipitate | Form after ignition |
|-----|------------|---------------------|
| Cl⁻ | AgCl | AgCl |
| SO₄²⁻ | BaSO₄ | BaSO₄ |
| Ca²⁺ | CaC₂O₄ | CaO (after ignition) |
| Fe³⁺ | Fe(OH)₃ | Fe₂O₃ |
| Ni²⁺ | Ni-dimethylglyoximate | NiC₈H₁₄N₄O₄ |

## Volumetric Analysis (Titrations)

### Titration Fundamentals
- **Standard solution**: precisely known concentration
- **Primary standard**: high purity, stable, high molar mass; used to standardize solutions
  - Examples: Na₂CO₃, KHP (potassium hydrogen phthalate), K₂Cr₂O₇
- **Equivalence point**: stoichiometrically equivalent amounts have reacted
- **Endpoint**: observed change (indicator/instrumental) signaling near equivalence point

### Acid-Base Titrations
See Acids and Bases chapter for calculations and indicators.

**Standardization of NaOH** with potassium hydrogen phthalate (KHP, MM = 204.22 g/mol):
KHP + NaOH → KNaP + H₂O (1:1 molar ratio)
M(NaOH) = moles KHP / volume NaOH (L)

### Complexometric Titrations (EDTA)
EDTA (ethylenediaminetetraacetic acid) forms stable 1:1 complexes with most metal cations.

- **EDTA titrations**: determine metal ion concentrations (Ca²⁺, Mg²⁺, Zn²⁺, etc.)
- **pM** = −log[M^n+]; titration curve plots pM vs. volume EDTA
- **Metallochromic indicators**: Eriochrome Black T (EBT) for Ca²⁺+Mg²⁺; calmagite, xylenol orange
- Indicator: MIn (colored) + EDTA → MY + In (different color) at endpoint
- **Masking**: add agent to prevent interference from other metals (e.g., CN⁻ masks Cu²⁺, Zn²⁺)
- **Water hardness**: Ca²⁺ + Mg²⁺ total concentration; expressed as mg CaCO₃/L

**Conditional formation constant** K'f = Kf × αY (where αY = fraction of EDTA in Y⁴⁻ form at given pH)

### Redox Titrations
| Titrant | Standard | Analytes |
|---------|----------|----------|
| KMnO₄ | Self-indicating (pink/purple) | Fe²⁺, oxalate, H₂O₂ |
| K₂Cr₂O₇ | Diphenylamine indicator | Fe²⁺ |
| Na₂S₂O₃ | Starch/I₂ indicator | Oxidizing agents (via iodometric method) |
| Ce(IV) | Ferroin indicator | Fe²⁺, As³⁺ |
| I₂ | Starch | Reducing agents directly |

**Iodometric analysis**: analyte oxidizes I⁻ → I₂; I₂ titrated with Na₂S₂O₃
```
I₂ + 2S₂O₃²⁻ → 2I⁻ + S₄O₆²⁻
```

### Precipitation Titrations
**Argentometric methods** (Ag⁺ as titrant for halides):
- **Mohr method**: Ag⁺ + Cl⁻ → AgCl; indicator K₂CrO₄ (red Ag₂CrO₄ forms at endpoint); neutral pH
- **Volhard method**: excess Ag⁺, back-titrate with KSCN; ferric alum indicator; acidic pH
- **Fajans method**: adsorption indicators (fluorescein, dichlorofluorescein)

## Spectroscopic Methods

### Beer-Lambert Law
```
A = εbC = log(P₀/P) = −log(T)
```
- A = absorbance (dimensionless)
- ε = molar absorptivity (L·mol⁻¹·cm⁻¹)
- b = path length (cm)
- C = concentration (mol/L)
- T = transmittance = P/P₀

**Linear range**: A = 0.1–1.0 (best accuracy at A ≈ 0.4–0.7)

### UV-Visible Spectroscopy
- **Chromophore**: part of molecule that absorbs light
- **Transition types**: π→π* (conjugated; ~200 nm), n→π* (carbonyl; ~280 nm), d-d (TM complexes; visible)
- **λmax**: wavelength of maximum absorbance; characteristic of compound
- **Applications**: quantitative analysis, protein concentration (Bradford, BCA), enzyme kinetics

### Atomic Spectroscopy
**Atomic Absorption Spectroscopy (AAS)**:
- Sample atomized (flame or graphite furnace) → atoms absorb light from hollow cathode lamp
- High selectivity; measures one element at a time
- Detection limits: ppm (flame), ppb (graphite furnace)

**Atomic Emission Spectroscopy / ICP-OES**:
- Inductively coupled plasma at ~6000–8000 K; atoms emit characteristic light
- Multi-element capability; wide linear range

**ICP-MS (Inductively Coupled Plasma Mass Spectrometry)**:
- Plasma ionizes sample → ions separated by mass/charge ratio
- Detection limits: ppt–ppq range; isotope ratios; trace metals

### Infrared (IR) Spectroscopy
- Mid-IR (400–4000 cm⁻¹): molecular vibrations (functional groups)
- **FTIR**: Fourier transform; superior sensitivity and resolution
- **ATR-FTIR**: attenuated total reflectance; surface analysis without sample prep
- Quantitative applications via Beer-Lambert law

### Fluorescence Spectroscopy
- More sensitive than UV-Vis (can detect <ppb)
- Only for fluorescent compounds (rigid conjugated systems)
- **Excitation spectrum**: λem fixed, scan λex
- **Emission spectrum**: λex fixed, scan λem
- Stokes shift: λem > λex
- Quenching: reduction in fluorescence by O₂, heavy atoms, energy transfer

### Nuclear Magnetic Resonance (NMR)
- Nuclei in magnetic field: spin states (α/β) differ in energy; absorb RF radiation
- **Chemical shift (δ, ppm)**: position of resonance relative to TMS
- **Integration**: proportional to number of equivalent nuclei
- **Splitting (coupling)**: J-coupling with neighboring nuclei
- **Applications**: structure elucidation (qualitative), quantitative NMR (qNMR)

### Mass Spectrometry (MS)
**Process**: ionization → separation by m/z → detection

**Ionization methods**:
| Method | Applicable to | Fragmentation |
|--------|--------------|--------------|
| Electron ionization (EI) | Small molecules, volatile | Hard (extensive) |
| Chemical ionization (CI) | Small molecules | Soft |
| Electrospray (ESI) | Large biomolecules | Very soft; multiple charges |
| MALDI | Polymers, proteins | Soft |

**m/z peaks**:
- **Molecular ion M⁺**: gives MW
- **M+1, M+2**: isotope peaks (useful for Cl, Br detection)
- **Fragmentation**: characteristic patterns for functional groups
- **Base peak**: most abundant ion

**Hyphenated techniques**: GC-MS, LC-MS, ICP-MS — combine separation with MS detection

## Chromatography

Separation based on differential partitioning between mobile and stationary phases.

### Key Parameters
```
Retention factor: k = (tR − tM) / tM
Resolution: Rs = 2(tR2 − tR1) / (w1 + w2)
Plate count: N = (tR/w)² × 16 = (tR/wh)² × 5.54
Height equivalent: H = L/N
```
- **tR**: retention time; **tM**: dead time (unretained); **w**: peak width at base; **wh**: at half-height

### Gas Chromatography (GC)
- Mobile phase: carrier gas (He, N₂, H₂)
- Stationary phase: liquid or solid coating on column
- Sample must be volatile and thermally stable
- **Column types**: packed vs. capillary (WCOT, PLOT)
- **Detectors**: FID (flame ionization, universal organic), TCD (thermal conductivity, universal), ECD (electron capture, halogens), MS

### High Performance Liquid Chromatography (HPLC)
- Mobile phase: solvent (aqueous or organic)
- Stationary phase: derivatized silica particles (3–5 μm)
- **Reversed-phase HPLC**: nonpolar stationary (C18, C8); polar mobile phase; most common
- **Normal-phase HPLC**: polar stationary (silica); nonpolar mobile phase
- **Ion exchange**: ionic stationary; separate ions
- **Size exclusion**: separate by molecular size
- **Detectors**: UV-Vis, DAD (diode array), fluorescence, refractive index, MS

### Thin Layer Chromatography (TLC)
- Simple, fast, qualitative
- **Rf = distance traveled by spot / distance traveled by solvent**
- Visualization: UV lamp, iodine vapor, ninhydrin, permanganate stains
- Preparative TLC for small-scale purification

### Ion Chromatography (IC)
- Separate anions and cations; suppressor removes background conductivity
- Conductivity detection; ppb detection limits
- Common analytes: F⁻, Cl⁻, NO₃⁻, SO₄²⁻, PO₄³⁻, Na⁺, K⁺, NH₄⁺, Ca²⁺, Mg²⁺

### Capillary Electrophoresis (CE)
- Separation by electrophoretic mobility in narrow capillary
- Very high efficiency (N > 10⁶); minimal sample volume
- Applications: DNA sequencing, chiral separation, amino acids, pharmaceuticals

## Electroanalytical Methods

### Potentiometry
- Measure potential at zero (or negligible) current
- **pH electrode**: glass electrode + reference electrode
- **Ion-selective electrodes (ISE)**: selective membrane; Nernst equation
  - E = constant ± (0.0592/z) log[A] (at 25°C; + for cations, − for anions)
- **Selectivity coefficient**: Kij = interference of ion j relative to primary ion i

### Voltammetry
- Measure current as function of applied potential
- **Cyclic voltammetry (CV)**: scan potential back and forth; shows oxidation/reduction peaks; mechanistic info
- **Differential pulse voltammetry (DPV)**: better sensitivity; ppb detection
- **Stripping voltammetry**: preconcentrate at electrode, then strip off; ppt detection for metals
- **Anodic stripping voltammetry (ASV)**: for heavy metals (Pb, Cd, Hg, Zn) in water

### Coulometry
- Measure total charge to complete electrolysis (100% efficiency)
- **Coulometric titration**: generate titrant in situ electrolytically; Karl Fischer for water content

## Sample Preparation

### Dissolution
- **Acid digestion**: HNO₃, H₂SO₄, HCl, HF, aqua regia (HNO₃/HCl 1:3)
- **Microwave-assisted digestion**: faster, closed vessels, less volatile loss
- **Fusion**: KOH, Na₂CO₃, or Na₂O₂ fusion for refractory materials

### Extraction
- **Liquid-liquid extraction**: partition analyte between two immiscible solvents; D = Corg/Caq
- **Solid-phase extraction (SPE)**: pass through sorbent cartridge; selective retention/elution
- **QuEChERS**: Quick, Easy, Cheap, Effective, Rugged, Safe — pesticide residues in food
- **Supercritical fluid extraction (SFE)**: CO₂ at T > 31.1°C, P > 73.8 atm; extracts nonpolar analytes

### Cleanup and Preconcentration
- **Solid-phase extraction**: cleanup of complex matrices
- **Evaporation**: concentrate analytes from dilute solutions
- **Derivatization**: improve volatility (GC), UV absorption, or fluorescence
