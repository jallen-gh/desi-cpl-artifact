# desi-cpl-artifact

Companion analysis for: **"A Relational Unification Framework 
via Type III₁ Algebras"**

Preprint: **"The DESI Phantom Crossing as a Parameterization 
Artifact: A Logarithmic Baseline and Falsifiable Predictions 
for DR4/DR5"**  
DOI: [10.5281/zenodo.19477320](https://doi.org/10.5281/zenodo.19477320)

## Overview

Recent constraints from DESI DR2 suggest an apparent "phantom 
crossing" in the dark energy equation of state when analyzed 
using the standard Chevallier-Polarski-Linder (CPL) 
parameterization. This repository demonstrates that this 
crossing is a fitting artifact arising when a rigid linear 
parameterization is applied to integral distance data generated 
by a strictly monotonic, logarithmically evolving phantom 
baseline.

The baseline $w(\tau) = -1 - (\eta_{opt}/2)(1 + e^{-\tau})$ 
emerges from the Oros Fundus framework with:
- $\eta_{opt} = 2/(\sqrt{\pi}(\ln N_F)^2) \approx 0.05416$ 
  (parameter-free, derived from topological invariants, $N_F = 96$)
- $w(z=0) = -1 - \eta_{opt} \approx -1.054$ (instantaneous value at $z=0$)
- $w_{eff} \approx -1.027$ (time-averaged over cosmic history, as reported in the companion paper)

## What the simulation shows

The script `mock_fit.py` runs CPL least-squares minimization 
across three progressive scenarios:

1. **Pure Noiseless Baseline:** The underlying geometry 
   naturally recovers a flat projection
2. **Realistic Local Variance:** Standard 1.5% noise triggers 
   a moderate phantom crossing
3. **Systemic Dataset Tension:** Simulates the 3–4.5% distance 
   anomalies in DESI LRG bins, recovering exactly 
   $w_0 \approx -0.75$, $w_a \approx -1.17$ — matching the 
   DESI DR2 "crisis" parameters

## Falsifiable Prediction

Non-parametric reconstruction of $w(z)$ from DESI DR4/DR5 
and Euclid will recover a monotonically phantom baseline 
without crossing. A genuine crossing that persists under 
non-parametric reconstruction with baryonic systematics 
controlled falsifies the artifact mechanism.

## Version history

| Version | Framework | eta_opt | Target |
|---------|-----------|---------|--------|
| v1.0 | Oros Fundus ~v15 | ~0.0850 | DR3 |
| v2.0 | Oros Fundus v1.5.35 | 0.05416 | DR4/DR5 + Euclid |

## Requirements

- `numpy`
- `scipy`

## Usage

```bash
python mock_fit.py
```

## Citation

If you use this code, please cite:  
Allen, J. (2026). *The DESI Phantom Crossing as a 
Parameterization Artifact*. Zenodo. 
https://doi.org/10.5281/zenodo.19477320
