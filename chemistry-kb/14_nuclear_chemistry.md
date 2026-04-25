# Nuclear Chemistry

## The Nucleus

The atomic nucleus contains protons and neutrons (collectively **nucleons**) held together by the **strong nuclear force** (short range, ~10⁻¹⁵ m, overcomes proton-proton electrostatic repulsion).

### Nuclear Notation
ᴬZX: A = mass number (p + n); Z = atomic number (p); N = A − Z neutrons

### Nuclear Stability
**Belt of stability** (N vs. Z plot): stable nuclei cluster in a band
- Light nuclei: N ≈ Z (1:1 ratio)
- Heavy nuclei: N > Z (need more neutrons to dilute proton repulsion)
- No stable nuclei beyond Z = 83 (bismuth-209 is the heaviest stable)

**Magic numbers**: extra stability when N or Z = 2, 8, 20, 28, 50, 82, 126 (filled nuclear shells)

**Nuclear binding energy**: energy required to completely separate all nucleons
```
Binding energy = Δm × c²
Δm (mass defect) = mass of constituent nucleons − mass of nucleus
```
**Binding energy per nucleon**: peaks at iron-56 (most stable nucleus)
- Nuclei lighter than Fe: energy released by **fusion**
- Nuclei heavier than Fe: energy released by **fission**

## Radioactive Decay

**Radioactivity**: spontaneous emission of radiation from unstable nuclei; obeys first-order kinetics.

```
N(t) = N₀ × e^(−λt)
t₁/₂ = ln2/λ = 0.693/λ
A (activity) = λN  (in Bq: disintegrations per second)
```

### Types of Decay

| Decay type | Emission | Change in A | Change in Z | Penetration |
|-----------|----------|-------------|-------------|-------------|
| Alpha (α) | ⁴He nucleus | −4 | −2 | Low (stopped by paper) |
| Beta-minus (β⁻) | e⁻ + antineutrino | 0 | +1 | Medium (Al sheet) |
| Beta-plus (β⁺) | e⁺ + neutrino | 0 | −1 | Medium |
| Electron capture (EC) | X-ray + neutrino | 0 | −1 | X-rays penetrate |
| Gamma (γ) | High-energy photon | 0 | 0 | High (Pb shielding) |
| Neutron emission | n | −1 | 0 | High (moderated by H) |
| Spontaneous fission | Heavy nucleus splits | Variable | Variable | High |

### Decay Series
Heavy elements undergo a series of decays until reaching stable end product:
- **Uranium-238 series**: ²³⁸U → … → ²⁰⁶Pb (14 steps, t₁/₂ = 4.47 × 10⁹ yr)
- **Thorium-232 series**: ²³²Th → … → ²⁰⁸Pb (t₁/₂ = 1.41 × 10¹⁰ yr)
- **Uranium-235 series**: ²³⁵U → … → ²⁰⁷Pb (t₁/₂ = 7.04 × 10⁸ yr)

### Alpha Decay
Heavy nuclei (A > 200) emit ⁴₂He nucleus:
²³⁸₉₂U → ²³⁴₉₀Th + ⁴₂He
- Alpha particles are high-LET (linear energy transfer); very damaging to living tissue at close range
- Cannot penetrate skin; dangerous if inhaled or ingested

### Beta-Minus Decay
Neutron-rich nuclei: n → p + e⁻ + v̄ₑ
¹⁴₆C → ¹⁴₇N + β⁻ + v̄ₑ
- Occurs below belt of stability (too many neutrons relative to protons)

### Positron (Beta-Plus) Decay
Proton-rich nuclei: p → n + e⁺ + νₑ
²²₁₁Na → ²²₁₀Ne + β⁺ + νₑ
- Occurs above belt of stability
- Positrons annihilate with electrons → two 511 keV γ-rays (basis of PET scanning)

### Electron Capture
Proton-rich alternative to β⁺: nucleus captures inner orbital e⁻
p + e⁻ → n + νₑ
⁵⁵₂₆Fe + e⁻ → ⁵⁵₂₅Mn + νₑ

### Gamma Decay
Follows α or β decay; nucleus in excited state → ground state + γ photon
- ⁹⁹ᵐTc (metastable) → ⁹⁹Tc + γ (140 keV photon; ideal for medical imaging)

## Radiocarbon Dating

**Principle**: ¹⁴C produced in upper atmosphere by cosmic ray neutrons + ¹⁴N; enters biosphere via CO₂; living organisms maintain constant ¹⁴C/¹²C ratio; upon death, ¹⁴C decays without replenishment.

t₁/₂(¹⁴C) = 5,730 years

```
age = t₁/₂ / ln2 × ln(A₀/A) = 8267 yr × ln(A₀/A)
```

**Range**: ~500 to ~50,000 years  
**Calibration**: required due to variations in atmospheric ¹⁴C (IntCal20 curve)

### Other Radiometric Dating
| Parent → Daughter | Half-life | Application |
|-------------------|-----------|-------------|
| ⁴⁰K → ⁴⁰Ar | 1.25 × 10⁹ yr | Rocks, minerals (K-Ar) |
| ²³⁸U → ²⁰⁶Pb | 4.47 × 10⁹ yr | Ancient rocks, Earth age |
| ⁸⁷Rb → ⁸⁷Sr | 4.88 × 10¹⁰ yr | Oldest rocks, meteorites |
| ²³²Th → ²⁰⁸Pb | 1.40 × 10¹⁰ yr | Old rocks |

## Nuclear Reactions

### Notation
General: A(a,b)B or: X + a → Y + b

**Particle symbols**: p (proton), n (neutron), d (deuteron ²H), α (⁴He), γ (gamma)

### Transmutation
First artificial: Rutherford (1919): ¹⁴N + α → ¹⁷O + p
First using accelerator: ⁷Li + p → 2α (Cockcroft-Walton, 1932)

**Transuranium elements**: produced by bombardment of heavy nuclei with neutrons or heavy ions
- Np (Z=93), Pu (Z=94) → first made in cyclotron
- Elements 104–118 (Rf through Og): made at GSI, JINR, RIKEN

### Nuclear Fission
Heavy nucleus splits into two medium-mass fission products + neutrons + energy

²³⁵₉₂U + n → ²³⁶₉₂U* → ¹⁴¹₅₆Ba + ⁹²₃₆Kr + 3n + ~200 MeV

**Chain reaction**: neutrons from fission trigger more fissions
- **Critical mass**: minimum mass for self-sustaining chain reaction
- **Subcritical**: k < 1 (chain dies out)
- **Critical**: k = 1 (steady power)
- **Supercritical**: k > 1 (exponential growth → bomb or meltdown)

**Moderators**: slow neutrons to thermal energies (more efficient fission of ²³⁵U)
- H₂O, D₂O (heavy water), graphite

**Control rods**: absorb neutrons to regulate chain reaction (Cd, B, Hf)

### Fission Fragments
Bimodal mass distribution (~95 and ~135 mass units); most fission products are radioactive beta-minus emitters (neutron-rich)
- ⁹⁰Sr (t₁/₂ = 28.8 yr): bone seeker; serious fallout hazard
- ¹³⁷Cs (t₁/₂ = 30.1 yr): major Chernobyl/Fukushima contaminant
- ¹³¹I (t₁/₂ = 8 days): thyroid cancer risk; treated with KI prophylaxis

### Nuclear Fusion
Light nuclei combine to form heavier nucleus + energy

Key reactions (tokamak/ICF):
- D + T → ⁴He + n + 17.6 MeV  (most favorable for power)
- D + D → ³He + n + 3.27 MeV
- p + ¹¹B → 3⁴He + 8.7 MeV (aneutronic; lower radiation)

**Stars**: fusion powers all stars; Sun burns H → He (proton-proton chain)
**Nucleosynthesis**: elements up to Fe formed in stars; heavier elements in supernovae/neutron star mergers

## Radiation Units

| Quantity | Unit (SI) | Old unit | Definition |
|----------|-----------|---------|-----------|
| Activity | Becquerel (Bq) | Curie (Ci) | 1 Bq = 1 decay/s; 1 Ci = 3.7×10¹⁰ Bq |
| Absorbed dose | Gray (Gy) | Rad | 1 Gy = 1 J/kg; 1 rad = 0.01 Gy |
| Dose equivalent | Sievert (Sv) | Rem | Gy × radiation weighting factor |
| Exposure | Coulomb/kg | Röntgen (R) | Ionization in air |

**Radiation weighting factors**: 
- α: 20; protons: 2; γ, β, X-ray: 1; neutrons: 5–20 (energy dependent)

**Background radiation**: ~3 mSv/year (radon ~2.3, cosmic ~0.3, medical ~3 mSv US avg)
**Dose limits**: occupational 50 mSv/yr; public 1 mSv/yr (above background)
**Lethal dose**: LD₅₀ ≈ 4 Gy whole-body acute (without treatment)

## Nuclear Power

### Nuclear Reactor Types
| Type | Moderator | Coolant | Fuel | Notes |
|------|-----------|---------|------|-------|
| PWR (pressurized water) | H₂O | H₂O (liquid) | enriched UO₂ | Most common (~70% worldwide) |
| BWR (boiling water) | H₂O | H₂O (boiling) | enriched UO₂ | Simpler; 20% worldwide |
| CANDU | D₂O | D₂O | natural UO₂ | No enrichment needed |
| RBMK | Graphite | H₂O | enriched U | Chernobyl reactor type |
| Fast reactor | None | Na or Pb | MOX (U+Pu) | Breed more fuel |
| Molten salt reactor | Graphite/none | Molten salt | dissolved U | Inherently safe design |

### Fuel Cycle
Mining → conversion → enrichment (²³⁵U: 0.72% natural → 3–5% power; >90% weapons) → fabrication → reactor → reprocessing or storage → disposal

**Enrichment methods**: gaseous diffusion (old), gas centrifuge (current), laser (SILEX, future)

## Medical and Industrial Applications

### Nuclear Medicine
**Diagnostic**: radiotracer injected → imaged with gamma camera, SPECT, or PET

| Radioisotope | t₁/₂ | Decay | Application |
|-------------|------|-------|-------------|
| ⁹⁹ᵐTc | 6 hr | γ (140 keV) | Most widely used; bone, heart, brain, thyroid scans |
| ¹⁸F-FDG | 110 min | β⁺ | PET scan; oncology, neurology, cardiology |
| ¹²³I | 13.2 hr | γ | Thyroid imaging |
| ²⁰¹Tl | 73 hr | γ | Cardiac perfusion |
| ⁶⁷Ga | 78 hr | γ | Infection, tumor imaging |

**Therapeutic**: radiotracer destroys target tissue

| Radioisotope | t₁/₂ | Decay | Application |
|-------------|------|-------|-------------|
| ¹³¹I | 8.1 d | β⁻ + γ | Thyroid cancer, hyperthyroidism |
| ⁹⁰Y | 2.7 d | β⁻ | Microspheres for liver cancer |
| ²²³Ra | 11.4 d | α | Bone metastases (Xofigo) |
| ¹⁷⁷Lu | 6.7 d | β⁻ | DOTATATE (neuroendocrine tumors) |

**Radiation therapy**: external beam (X-ray, γ, proton, carbon-12 ion); IMRT, SBRT

### Industrial Applications
- **Radiography**: ¹⁹²Ir or ⁶⁰Co X-ray welds, castings
- **Gauges**: measure thickness, density
- **Sterilization**: ⁶⁰Co γ-irradiation of medical equipment, food
- **Smoke detectors**: ²⁴¹Am (α-emitter) ionizes air
- **Food irradiation**: extends shelf life; approved in 60+ countries
- **Neutron activation analysis (NAA)**: ultra-trace elemental analysis

## Radiation Protection

### Three Principles
1. **Time**: minimize exposure time
2. **Distance**: maximize distance (inverse square law: I ∝ 1/r²)
3. **Shielding**: appropriate material for radiation type
   - α: paper/skin
   - β: plastics/aluminum (avoid high-Z materials: bremsstrahlung)
   - γ/X-ray: lead, concrete, water
   - Neutrons: hydrogen-rich materials (polyethylene, water, paraffin)

### Biological Effects
- **Stochastic effects**: probabilistic; cancer risk; no threshold assumed
- **Deterministic effects**: certain dose → certain effect; threshold exists
  - Erythema (skin redness): ~3 Gy local
  - Acute radiation syndrome: >1 Gy whole body
  - Cataracts: >0.5–2 Gy to lens

**Radiosensitivity**: rapidly dividing cells most sensitive (bone marrow, GI epithelium, gonads)
**LNT model** (linear no-threshold): cancer risk proportional to dose; basis for radiation protection standards
