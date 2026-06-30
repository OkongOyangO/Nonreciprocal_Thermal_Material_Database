# First-Principles Dielectric & Nonreciprocity Database for Magnetic Topological Materials

**Live viewer:** https://okongoyango.github.io/Nonreciprocal_Thermal_Material_Database/

Companion data repository for:

> Yiyang Jiang, Yufei Zhao, Linxiao Zhu, and Binghai Yan, "Designing Strong and Broadband Nonreciprocal Thermal Radiation in Magnetic Topological Materials," [arXiv:2606.14861](https://arxiv.org/abs/2606.14861) (2026).

## Overview

This repository hosts the full first-principles dielectric tensor and nonreciprocal thermal radiation database computed for the paper. All material parameters were obtained from a DFT–Kubo–Maxwell framework: density functional theory (DFT) calculations with spin-orbit coupling and magnetic order → maximally localized Wannier functions → Kubo–Greenwood optical conductivity → gyrotropic permittivity tensor → angle-resolved nonreciprocity via a 4×4 Berreman matrix solver.

The database covers 10 candidate magnetic topological materials across a chemical potential sweep μ ∈ [−0.5, 0.5] eV and emission angle θ ∈ [5°, 85°].

## Materials

| Material | Magnetic type | Notes |
|---|---|---|
| Co₃Sn₂S₂ | Kagome Weyl ferromagnet | Giant and broadband nonreciprocity; headline material |
| Eu₃In₂As₄ (FMa) | Hybrid topological semimetal | Highest Δ_max ~ 35% in screened set |
| Eu₃In₂As₄ (AFMa) | Hybrid topological semimetal (AFM) | |
| Eu₃In₂As₄ (FMc) | Hybrid topological semimetal (c-axis FM) | Multiple ENZ crossings → intrinsically broadband |
| Mn₃Ge | Noncollinear antiferromagnet | Large AHE but high loss → weak nonreciprocity |
| Mn₃Sn | Noncollinear antiferromagnet | Large AHE but high loss → weak nonreciprocity |
| Co₂MnAl | Heusler topological ferromagnet | Real-dominated off-diagonal gyrotropy |
| Co₂MnGa | Heusler topological ferromagnet | Real-dominated off-diagonal gyrotropy |
| MnTe | Altermagnet | Low carrier density; no ENZ at high hole doping |
| InAs (B = 1 T) | Conventional semiconductor reference | External-field benchmark |

## ENZ-audit categories

Each (material, μ) point is classified by whether Re ε_xx(ω) has a clean epsilon-near-zero (ENZ) crossing in the radiation window, since the scaling laws require a well-defined plasma frequency ω₀:

| Tag | Meaning |
|---|---|
| **MATCH** | Single clean ENZ crossing — valid for scaling-law fit |
| **MULTI** | ≥ 2 ENZ crossings — multi-resonance regime, intrinsically broader bandwidth |
| **NO_ENZ** | Re ε_xx stays negative / no crossing in simulated window |
| **INSUL** | Insulating or outside the scaling analysis set |

## Key material parameters tabulated

For each (material, μ) point with a well-defined ω₀, the database reports:

- **ω₀** — ENZ (plasma) frequency where Re ε_xx(ω₀) = 0
- **β** — dielectric dispersion ∂_ω Re ε_xx evaluated at ω₀ (eV⁻¹)
- **Im ε_xx** — optical loss at ω₀
- **Re ε_xz, Im ε_xz** — off-diagonal anomalous Hall component at ω₀
- **Δ_max** — peak nonreciprocal contrast max|e(ω,θ) − α(ω,θ)|
- **Δω** — operational bandwidth (half-maximum support of Δ around ω₀)

## Design rules from the paper

The paper derives two universal material scaling laws from the factorized gyrotropic Fresnel reflectivity:

**Nonreciprocity strength:**
$$\Delta_\text{max} \propto \frac{g}{(\varepsilon_d'')^p}, \quad p \in [1,\, 3/2]$$

where g = Im ε_xz is the anomalous Hall gyrotropy and ε_d'' = Im ε_xx is the optical loss. The exponent interpolates between the low-loss semiconductor limit (p → 1) and the high-loss metal limit (p → 3/2).

**Operational bandwidth:**
$$\Delta\omega \propto \frac{\varepsilon_d''}{\beta}$$

which equals the plasmon linewidth. Large optical loss and small dielectric dispersion both favor broadband response.

These two laws expose a fundamental trade-off — optical loss degrades strength but enlarges bandwidth — and identify materials with moderate carrier density and large anomalous Hall effect (e.g. Co₃Sn₂S₂) as optimal candidates for simultaneously strong and broadband nonreciprocal thermal radiation.

## Interactive viewer

Open `index.html` in any modern browser — no server, no build step, no dependencies. All data is embedded in the single HTML file.

- **Heatmap** — rows: materials; columns: chemical potential μ; cell color: ENZ-audit category. Click any cell to load the spectra for that (material, μ) point.
- **Dielectric spectra panel** — Re ε_xx, Im ε_xx, Re/Im ε_xz vs photon energy ω.
- **Nonreciprocity panel** — Δ(ω, θ) = e(ω, θ) − α(ω, θ) for the selected emission angles.
- **Category filter** — show/hide MATCH / MULTI / NO_ENZ / INSUL points.
- **Angle selector** — overlay all θ curves (default) or isolate a single emission angle θ in the Δ(ω, θ) panel.
- **Curve readout** — hover any Δ(ω, θ) curve to read off the exact (ω, Δ) coordinates (and θ) at that point via a snap-to-curve tooltip and crosshair marker.

## Computational parameters

All calculations use a phenomenological broadening η = 0.01 eV representing the inverse quasiparticle lifetime. The InAs benchmark uses the single-band non-parabolic effective-mass Drude model under B = 1 T, following the parameters of the gradient-doped InGaAs experiments. DFT calculations include spin-orbit coupling and the relevant magnetic ordering for each material phase.

## Citation

If you use this database, please cite:

> Yiyang Jiang, Yufei Zhao, Linxiao Zhu, and Binghai Yan, "Designing Strong and Broadband Nonreciprocal Thermal Radiation in Magnetic Topological Materials," [arXiv:2606.14861](https://arxiv.org/abs/2606.14861) (2026).
