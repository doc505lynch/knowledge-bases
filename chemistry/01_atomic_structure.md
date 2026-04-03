# Atomic Structure

## Historical Models of the Atom

| Model | Scientist | Year | Key Idea |
|-------|-----------|------|----------|
| Billiard ball | Dalton | 1803 | Atoms are indivisible solid spheres |
| Plum pudding | Thomson | 1904 | Electrons embedded in positive sphere |
| Nuclear | Rutherford | 1911 | Small dense positive nucleus; electrons orbit |
| Planetary/Quantized | Bohr | 1913 | Electrons in fixed circular orbits (energy levels) |
| Quantum mechanical | Schrödinger | 1926 | Electrons described by wave functions (orbitals) |

## Subatomic Particles

| Particle | Symbol | Charge | Mass (amu) | Location |
|----------|--------|--------|------------|----------|
| Proton | p⁺ | +1 | 1.0073 | Nucleus |
| Neutron | n⁰ | 0 | 1.0087 | Nucleus |
| Electron | e⁻ | −1 | 0.000549 | Orbitals (electron cloud) |

- **Atomic number (Z)**: number of protons — defines the element
- **Mass number (A)**: protons + neutrons
- **Isotopes**: same Z, different A (different number of neutrons)
- **Ions**: atoms with gained (anion, −) or lost (cation, +) electrons

## Isotope Notation

ᴬZX or X-A notation (e.g., ¹²C, C-12; ²³⁵U, U-235)

**Atomic mass** = weighted average of isotope masses:
```
atomic mass = Σ (fractional abundance × isotope mass)
```

Example — chlorine: 75.77% ³⁵Cl (34.969 amu) + 24.23% ³⁷Cl (36.966 amu)  
= 0.7577(34.969) + 0.2423(36.966) = **35.45 amu**

## Quantum Mechanical Model

### Wave-Particle Duality
- de Broglie: λ = h/mv (wavelength of a particle)
- Heisenberg uncertainty principle: Δx · Δp ≥ ℏ/2 (cannot simultaneously know exact position and momentum)

### Schrödinger Equation
Ĥψ = Eψ

- ψ (wave function): mathematical description of electron state
- ψ² (probability density): probability of finding electron at given location
- **Orbital**: region of space with 90%+ probability of electron occupancy

## Quantum Numbers

Four quantum numbers uniquely describe each electron:

| QN | Symbol | Values | Describes |
|----|--------|--------|-----------|
| Principal | n | 1, 2, 3, … | Energy level / shell size |
| Angular momentum | ℓ | 0 to (n−1) | Orbital shape (subshell) |
| Magnetic | mℓ | −ℓ to +ℓ | Orbital orientation |
| Spin | ms | +½ or −½ | Electron spin direction |

### Subshell Labels
- ℓ = 0 → **s** (spherical), 1 orbital per subshell
- ℓ = 1 → **p** (dumbbell), 3 orbitals
- ℓ = 2 → **d** (cloverleaf), 5 orbitals
- ℓ = 3 → **f**, 7 orbitals

Maximum electrons per subshell: s=2, p=6, d=10, f=14

## Electron Configuration Rules

1. **Aufbau principle**: fill lowest energy orbitals first
2. **Pauli exclusion principle**: no two electrons can have the same four quantum numbers; max 2 electrons per orbital (opposite spins)
3. **Hund's rule**: within a subshell, one electron per orbital before pairing; all unpaired electrons have parallel spins

### Filling Order (Madelung's rule)
1s → 2s → 2p → 3s → 3p → 4s → 3d → 4p → 5s → 4d → 5p → 6s → 4f → 5d → 6p → 7s → 5f → 6d → 7p

### Examples
- H (Z=1): 1s¹
- C (Z=6): 1s² 2s² 2p²  → [He] 2s² 2p²
- Fe (Z=26): [Ar] 3d⁶ 4s²
- Cu (Z=29): [Ar] 3d¹⁰ 4s¹ (exception — stability of full d subshell)
- Cr (Z=24): [Ar] 3d⁵ 4s¹ (exception — stability of half-full d subshell)

### Abbreviated (Noble Gas) Notation
Write the preceding noble gas in brackets, then remaining electrons:
- Na: [Ne] 3s¹
- Cl: [Ne] 3s² 3p⁵

## Orbital Shapes

| Orbital | Shape | Nodes |
|---------|-------|-------|
| 1s | sphere | 0 radial, 0 angular |
| 2s | larger sphere with radial node | 1 radial, 0 angular |
| 2p | dumbbell along x, y, or z axis | 0 radial, 1 angular |
| 3d | cloverleaf (4 lobes) or dz² | 0 radial, 2 angular |
| 4f | complex multi-lobe | 0 radial, 3 angular |

- **Radial nodes**: n − ℓ − 1
- **Angular nodes**: ℓ
- **Total nodes**: n − 1

## Atomic Spectra

### Bohr Model (Hydrogen)
Energy of level n: Eₙ = −13.6 eV / n²  = −2.18 × 10⁻¹⁸ J / n²

Energy of photon emitted/absorbed:
ΔE = Eᶠ − Eᵢ = hν = hc/λ

**Rydberg equation**:
1/λ = R∞(1/n₁² − 1/n₂²)  where R∞ = 1.097 × 10⁷ m⁻¹

### Spectral Series (Hydrogen)
| Series | n₁ | Region |
|--------|-----|--------|
| Lyman | 1 | UV |
| Balmer | 2 | Visible |
| Paschen | 3 | IR |
| Brackett | 4 | IR |

## Effective Nuclear Charge and Shielding

**Zeff = Z − S** (effective nuclear charge = nuclear charge minus shielding constant)

- Core electrons shield outer electrons from full nuclear charge
- **Slater's rules** give approximate shielding constants
- Higher Zeff → electrons held more tightly → smaller atomic radius, higher ionization energy

## Magnetic Properties

- **Diamagnetic**: all electrons paired; weakly repelled by magnetic field
- **Paramagnetic**: one or more unpaired electrons; attracted to magnetic field (e.g., O₂, Fe³⁺)
- **Ferromagnetic**: permanent magnetism in bulk (Fe, Co, Ni)
