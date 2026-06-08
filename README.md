# NTP ENZ-Audit Interactive Viewer

**Live demo:** https://okongoyango.github.io/NTP-ENZ-Audit-Viewer/

Interactive database viewer for *Nonreciprocal Thermal Photonics in Magnetic Topological Materials*.

## What's inside

A single-file HTML application (`index.html`) embedding the full first-principles dielectric and nonreciprocity database for 10 candidate materials across a sweep of chemical potential μ and emission angle θ:

| Material | Type |
|---|---|
| Co₃Sn₂S₂ | Magnetic Weyl semimetal |
| Mn₃Ge, Mn₃Sn | Kagome antiferromagnet |
| Co₂MnAl, Co₂MnGa | Heusler half-metal |
| MnTe | Altermagnetic semiconductor |
| Eu₃In₂As₄ (FM/AFM) | Topological EuIn₂As₂ family |
| InAs (B = 1 T) | Conventional reference |

## ENZ-audit categories

| Tag | Meaning |
|---|---|
| **MATCH** | Single ENZ crossing — valid for scaling-law fit |
| **MULTI** | ≥ 2 ENZ crossings — multi-branch regime |
| **NO_ENZ** | No crossing / spurious ω₀ in spectral window |
| **INSUL** | Insulating / excluded from scaling set |

## Usage

Open `index.html` in any modern browser — no server, no dependencies.

- Click a heatmap cell to load dielectric spectra (Re/Im εxx, Im εxz) and nonreciprocity (ΔR vs ω) for that (material, μ) combination.
- Use the angle selector to overlay multiple θ curves.
- Use the category filter to hide/show audit classes.

## Citation

> J. Yang *et al.*, "Nonreciprocal Thermal Photonics in Magnetic Topological Materials from a First-Principles Toolbox" (in preparation, 2026).
