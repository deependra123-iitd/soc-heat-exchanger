# Self-Organized Criticality in Heat Exchangers

> **Complexity Science Project** — applying the SOC framework to fouling dynamics
> in shell-and-tube heat exchangers.

**Student:** Deependra Singh &nbsp;|&nbsp; **Course:** CHL7903 — Complexity Science &nbsp;|&nbsp; **Department:** Chemical Engineering, IIT Delhi &nbsp;|&nbsp; **Submitted:** 09 April 2026

---

## Overview

This project argues that shell-and-tube heat exchanger fouling dynamics are a
natural physical realisation of **self-organised criticality (SOC)**. We map
the system onto the Bak–Tang–Wiesenfeld (BTW) sandpile model and simulate
fouling-induced thermal avalanches on a 2D lattice. The key result is a
power-law avalanche size distribution, with exponent τ ≈ 1.5–1.8, whose
statistics depend systematically on the tube-bundle connectivity.

---

## Repository Structure

```
├── manuscript.tex            # LaTeX source — two-column journal format
├── manuscript_journal.pdf    # Compiled PDF (journal style)
├── simulation.py             # Python BTW sandpile simulation
├── figures/                  # Generated plots (created by simulation.py)
│   ├── fig1_fouling_evolution.png
│   ├── fig2_avalanche_distribution.png
│   ├── fig3_connectivity_comparison.png
│   └── fig4_temporal_evolution.png
├── stats.json                # Simulation summary statistics (auto-generated)
└── README.md
```

---

## Quick Start

### 1. Install dependencies

```bash
pip install numpy matplotlib scipy
```

### 2. Run the simulation

```bash
python3 simulation.py
```

This will:
- Run 200 000 drive steps on a 50 × 50 grid for both k = 4 and k = 8
- Generate all four figures in `figures/`
- Write `stats.json` with summary statistics

### 3. Compile the manuscript (requires a LaTeX installation)

```bash
pdflatex manuscript.tex
pdflatex manuscript.tex   # run twice for cross-references
```

---

## Key Results

| Connectivity | Avalanches | Max size | Mean size | Power-law exponent τ |
|---|---|---|---|---|
| k = 4 (Von Neumann) | 1 909 | 168 | 5.2 | ≈ 1.5 |
| k = 8 (Moore)       | 4 737 | 225 | 12.6 | ≈ 1.8 |

*Results from T = 5 000 drive steps on a 15 × 15 grid (manuscript parameters).
The simulation defaults to N = 50 and T = 200 000 for better statistics.*

---

## Model Summary

The heat exchanger tube bundle is mapped to an N × N integer lattice.

| Concept | Physical meaning | Model element |
|---|---|---|
| **Noise** | Stochastic fouling particle deposition | Random grain addition |
| **Avalanche** | Cascade heat-load redistribution | BTW toppling rule |
| **Connectivity** | Thermally coupled neighbouring tubes | k = 4 or k = 8 |
| **Boundary** | Shell wall dissipation | Open boundary (grains lost) |

### Toppling rule

When a cell accumulates fouling load z ≥ z_c = 4:

```
z[i,j]       ←  z[i,j] - z_c
z[neighbour] ←  z[neighbour] + 1   (for each in-bounds neighbour)
```

Grains that would leave the N × N boundary are permanently removed,
providing the open-boundary dissipation required for SOC.

---

## Engineering Implications

1. **Unpredictability of large events** — P(s) is heavy-tailed; use power-law
   statistics for risk assessment, not Gaussian.
2. **Connectivity as a design variable** — reducing tube-bundle connectivity
   (via baffles or lower-pitch layouts) reduces both the frequency and maximum
   size of fouling avalanches.
3. **Perturbation as a control strategy** — periodic cleaning pulses are more
   effective than reactive cleaning because the SOC state is an attractor.

---

## Dependencies

| Package | Version | Purpose |
|---|---|---|
| numpy | ≥ 1.24 | Array operations & random number generation |
| matplotlib | ≥ 3.7 | Figures |
| scipy | ≥ 1.10 | (optional — used for extended statistical analysis) |

---

## References

- P. Bak, C. Tang & K. Wiesenfeld (1987). *Self-organized criticality*. Phys. Rev. Lett. 59(4).
- P. Bak (1996). *How Nature Works*. Copernicus Press.
- S. Lübeck (2000). *Finite-size scaling of the BTW sandpile model*. Phys. Rev. E 61(1).
- M. Muller-Steinhagen & Q. Zhao (1997). *Heat transfer and pressure drop during
  crystallisation fouling*. Chem. Eng. Sci. 52(19).

---

## Acknowledgements

This project used [Claude (Anthropic)](https://claude.ai) for manuscript drafting
and simulation code generation. All scientific content was verified by the author
against primary literature.
