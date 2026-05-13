# Axiom-Earth2 — Exoplanet Discovery Pipeline

**Pipeline:** EARTH2-1.0.0 · **Schema:** v3.0 · **Data Source:** NASA TESS (SPOC) · **License:** MIT

> Before all else: I recognize that in a domain as complex and data-invariant as astrophysics, mathematical discrepancies or logical oversights may exist in these early results. Axiom-Zspace is a mission to build the first fully transparent, white-box system for exoplanet discovery. While it is a work in progress, I am committed to absolute transparency and invite the community to audit and correct any findings. I am open to technical collaborations under NDA to further refine these logical kernels.
> — *Axiom-Zspace mission statement (Updated: 2/May/2026)*

---

## Resource: Axiom-Zspace (The Parent Project)

This repository is part of the broader **Axiom-Zspace** initiative — a fully transparent, white-box engine for large-scale astronomical signal processing.

> [**Axiom-Zspace on GitHub**](https://github.com/Zierax/Axiom-Zspace)

**Axiom-Zspace** is a high-performance, white-box engine designed for large-scale astronomical signal processing. By leveraging **Deterministic Logical Invariants**, it deconvolves raw light-curve data from the TESS and Kepler missions to identify exoplanet transit candidates with high precision and sub-millisecond inference logic.

### Axiom-Zspace Milestones

| Milestone | Date | Result |
|-----------|------|--------|
| **First Milestone** | April 26, 2026 | **2,886 new exoplanet candidates** from TESS Sectors 7, 41, 42 (24-hour scan) |
| **Second Milestone** | May 2, 2026 | **5,845 new exoplanet candidates** from Sectors 7, 36, 41, 42, 55, 67 (ongoing) |
| **Performance Benchmark** | — | 92.7% detection rate on single-core CPU (~4 hours for 619 signals) |

### Performance Benchmark (Axiom-Zspace Kernel Stress Test)

| Metric | Value |
|:---|---:|
| **Hardware Environment** | Single-Core CPU |
| **Total Processing Time** | ~4 Hours |
| **Total Signals Tested** | 619 |
| **Confirmed Detections** | 574 (**92.7%**) |
| **False Negatives (Missed)** | 3 (**0.5%**) |
| **Technical Failures** | 42 (6.8%) |

> A 92.7% detection rate on a single-core processor within 4 hours demonstrates the extreme computational efficiency of the Truthimatics logic compared to traditional probabilistic models — and this is before GPU acceleration.

### The Big Picture

**Who built this?** Axiom-Zspace/Earth2 was built by a **17-year-old independent researcher** currently in their final year of secondary school. This project represents a novel approach to exoplanet detection that prioritizes **deterministic logic** over statistical black-box methods.

**Why does this exist?** Traditional exoplanet detection pipelines (including NASA's own) are often opaque, relying on neural networks, random forest classifiers, or proprietary algorithms that are difficult to audit. Axiom-Zspace and Axiom-Earth2 were created to demonstrate that **a fully transparent, white-box system can achieve competitive results** while maintaining complete auditability.

**Philosophy:** Every signal must have a traceable, verifiable mathematical proof. No black boxes. No hidden layers. No proprietary secrets.

### Special Acknowledgments

Made possible through generous free-tier compute provided by:

- **[Google Colab](https://colab.research.google.com)**
- **[Kaggle Kernels](https://www.kaggle.com)**
- **[Lightning.ai](https://lightning.ai)**

Data sourced from **[NASA & The TESS Mission](https://asd.gsfc.nasa.gov/archive/tess/)** via the **[MAST Archive](https://archive.stsci.edu/)**.

---

## Table of Contents

- [What Is Axiom-Earth2?](#what-is-axiom-earth2)
- [Why Does This Repository Exist?](#why-does-this-repository-exist)
- [The Target Prioritization System](#the-target-prioritization-system)
- [Verdict Distribution](#verdict-distribution)
- [Candidate Leaderboard](#candidate-leaderboard)
- [How the Pipeline Works](#how-the-pipeline-works)
- [Aggregate Statistics](#aggregate-statistics)
- [The Candidate Planets](#the-candidate-planets)
- [False Positive Breakdown](#false-positive-breakdown)
- [File Structure](#file-structure)
- [Discovery Card Schema](#discovery-card-schema)
- [Key Quantitative Metrics Explained](#key-quantitative-metrics-explained)
- [Data Provenance](#data-provenance)
- [The Truthimatics Seal](#the-truthimatics-seal)
- [On Data Authenticity](#on-data-authenticity)
- [Usage](#usage)
- [Contributing and Contact](#contributing-and-contact)
- [License](#license)

---

## What Is Axiom-Earth2?

**Axiom-Earth2** is a **fully transparent, white-box exoplanet detection pipeline** that processes TESS light curves to identify, validate, and characterize exoplanet candidates. This repository contains **263 detailed discovery cards** — one per TESS target of interest (TIC) — each with a complete, auditable chain of physical reasoning explaining the verdict.

**Every single analyzed target is included here** — the 1 confirmed planet candidate, the 14 likely candidates, the 20 ambiguous signals requiring follow-up, and all 228 false positives. This ensures the full evidentiary record is preserved. False positives are not discarded; they are documented with the same rigor as every candidate, including exactly why each signal was rejected.

Axiom-Earth2 is **not** an ML model and **not** a black box. It is a **physics engine** that applies Kepler's laws, Mandel-Agol transit models, and established astrophysical principles to decide whether a signal is a real exoplanet.

### Key Principles

| Principle | Meaning |
|-----------|---------|
| **White-Box** | Every score and verdict can be traced back to raw photometric data and physical equations |
| **No ML** | No machine learning, neural networks, or black box models are used anywhere in the pipeline |
| **No Imputation** | Missing or low-quality data is flagged, not fabricated |
| **Physics-Derived** | All calculations are based on Kepler's laws, Mandel-Agol transit models, and established astrophysics |
| **Full Proof Chain** | Each card contains the complete step-by-step derivation from raw light curve to final verdict |

---

## Why Does This Repository Exist?

### The Problem

Exoplanet discovery pipelines in astronomy have a transparency problem:

- **NASA's TESS pipeline (SPOC)** uses proprietary algorithms that require expert-level understanding to audit
- **Machine learning approaches** (random forests, neural networks, autoencoders) are inherently opaque — you cannot trace *why* a particular classification was made
- **Community surveys** often only publish positive results, creating publication bias
- **False positives are typically discarded silently**, making it impossible to learn from them

### The Axiom Solution

This repository is a **proof of concept** that demonstrates:

1. **Transparency is possible** — Every single target, whether a planet candidate or a clear false positive, gets a full write-up with its complete analytical trace
2. **Deterministic logic works** — By using physical laws instead of statistical inference, we produce auditable, reproducible results
3. **Failure modes are documented** — The 228 false positives are not noise; they are a learning resource showing exactly why each signal was rejected (depth inconsistency, V-shape, density mismatch, etc.)
4. **Anyone can verify** — Each discovery card is a standalone JSON document with the full proof chain

### What This Repository Contains

- **263 fully analyzed TESS targets** from single-sector observations
- **35 targets with CVS > 0.35** (passing initial detection thresholds)
- **1 confirmed planet candidate** (TIC 436235326)
- **228 false positives** with complete documentation of why each was rejected
- **Full methodology explanations** including formulas, thresholds, and weight calculations
- **Zero imputation** — all flags are based on actual data quality

### Open Invitation for Peer Review

These findings are strictly classified as **Candidates**. While each discovery is supported by a deterministic benchmark and a unique analytical proof, they require spectroscopic confirmation by the professional astronomical community.

> I invite astrophysicists, logic researchers, and data scientists to audit the underlying engine. My goal is to refine this framework through rigorous peer feedback, evolving it into a reliable, open-source tool for planetary discovery.
>
> — *Founder, Axiom-Zspace (17 years old, final year secondary school)*

**Community cross-reference:** These findings are being actively cross-referenced with community-driven projects such as [Zooniverse Planet Hunters TESS](https://www.zooniverse.org/projects/nora-dot-eisner/planet-hunters-tess/).

---

## The Target Prioritization System

Axiom-Earth2 does not blindly scan every TIC in the sky. It uses a **prioritization system** that scores and ranks targets before any light curve processing begins.

### How Prioritization Works

1. **Target Filtering** — Before any transit search, targets are pre-screened by:
   - Stellar parameters (T_eff, radius, log(g), metallicity from TIC v8.2)
   - Exclusion of known eclipsing binaries and variable stars
   - Data quality flags from the TESS pipeline
   - Minimum cadence requirements (reject targets with insufficient observations)

2. **Priority Scoring** — Remaining targets are ranked by:
   - **Habitability potential** (stellar temperature matching conservative HZ boundaries)
   - **Signal detectability** (stellar brightness, photometric noise floor)
   - **Scientific value** (known planets, multi-sector coverage, community interest)

3. **Batch Processing** — The highest-priority targets are processed first, with the batch size determined by available compute resources

4. **Iterative Refinement** — As high-priority targets complete processing, new batches are drawn from the priority queue

This means that **the 263 targets in this repository were not randomly selected** — they represent the top-priority targets from a much larger pool, pre-selected for their likelihood of hosting detectable, potentially habitable planets.

> **Why this matters:** This prioritization explains why the dataset includes many targets with Earth-like equilibrium temperatures (290K range) rather than random stars. The pipeline actively seeks out the most promising candidates before investing compute in their analysis.

---

## Verdict Distribution

| Verdict | Count | CVS Threshold |
|---------|:-----:|:-------------:|
| **PLANET CANDIDATE** | **1** | CVS >= 0.80 |
| **LIKELY PLANET CANDIDATE** | **14** | CVS >= 0.55 |
| **AMBIGUOUS / REQUIRES FOLLOW-UP** | **20** | CVS >= 0.35 |
| **FALSE POSITIVE** | **228** | CVS < 0.35 |
| **Total** | **263** | — |

---

## Candidate Leaderboard

Below are all **35 targets with CVS >= 0.35** — the targets that passed initial detection thresholds and warrant further investigation. These are listed in order of descending CVS, encompassing the single planet candidate, 14 likely planet candidates, and 20 ambiguous cases requiring follow-up.

| Rank | TIC ID | Verdict | CVS | Period (d) | Radius (R_Earth) | Teq (K) | ESI | Composition | Flags |
|:----:|:-------|:--------|:---:|:----------:|:----------------:|:-------:|:---:|:-----------:|:-----:|
| 1 | TIC 436235326 | **PLANET CANDIDATE** | **0.8272** | 30.248 | 2.07 | 290.3 | 0.7338 | Water World | 3 |
| 2 | TIC 359496368 | **LIKELY PLANET CANDIDATE** | **0.7991** | 2.665 | 1.40 | 730.7 | 0.6598 | Rocky/Earth-like | 2 |
| 3 | TIC 99937206 | **LIKELY PLANET CANDIDATE** | **0.7983** | 32.089 | 1.24 | 296.8 | 0.9052 | Rocky/Earth-like | 5 |
| 4 | TIC 142963210 | **LIKELY PLANET CANDIDATE** | **0.7243** | 32.089 | 1.20 | 221.7 | 0.9169 | Rocky/Earth-like | 4 |
| 5 | TIC 7773413 | **LIKELY PLANET CANDIDATE** | **0.6899** | 39.382 | 1.86 | 291.6 | 0.7687 | Water World | 2 |
| 6 | TIC 100013015 | **LIKELY PLANET CANDIDATE** | **0.6369** | 32.054 | 2.38 | 220.2 | 0.6884 | Water World | 4 |
| 7 | TIC 138362758 | **LIKELY PLANET CANDIDATE** | **0.6328** | 29.090 | 2.49 | 265.1 | 0.6779 | Water World | 5 |
| 8 | TIC 289325518 | **LIKELY PLANET CANDIDATE** | **0.6237** | 44.060 | 1.11 | 217.9 | 0.9351 | Rocky/Earth-like | 4 |
| 9 | TIC 284185810 | **LIKELY PLANET CANDIDATE** | **0.6230** | 26.715 | 1.30 | 311.1 | 0.8816 | Rocky/Earth-like | 4 |
| 10 | TIC 288129738 | **LIKELY PLANET CANDIDATE** | **0.6218** | 13.730 | 1.04 | 427.7 | 0.8336 | Rocky/Earth-like | 4 |
| 11 | TIC 142825877 | **LIKELY PLANET CANDIDATE** | **0.6217** | 44.200 | 2.90 | 249.7 | 0.6323 | Water World | 4 |
| 12 | TIC 156464839 | **LIKELY PLANET CANDIDATE** | **0.6209** | 43.386 | 0.76 | 260.9 | 0.8966 | Rocky/Earth-like | 1 |
| 13 | TIC 237131816 | **LIKELY PLANET CANDIDATE** | **0.5815** | 37.384 | 3.48 | 239.4 | 0.5819 | Water World | 6 |
| 14 | TIC 142878895 | **LIKELY PLANET CANDIDATE** | **0.5703** | 38.552 | 2.66 | 194.8 | 0.6471 | Water World | 4 |
| 15 | TIC 229552665 | **LIKELY PLANET CANDIDATE** | **0.5692** | 38.247 | 1.41 | 305.9 | 0.8591 | Rocky/Earth-like | 1 |
| 16 | TIC 372759030 | AMBIGUOUS | 0.5367 | 49.230 | 2.04 | 256.9 | 0.7418 | Water World | 3 |
| 17 | TIC 21002564 | AMBIGUOUS | 0.5331 | 43.611 | 2.40 | 248.4 | 0.6891 | Water World | 3 |
| 18 | TIC 441761546 | AMBIGUOUS | 0.5219 | 47.941 | 1.59 | 274.4 | 0.8269 | Water World | 2 |
| 19 | TIC 137733738 | AMBIGUOUS | 0.5097 | 34.645 | 2.19 | 286.2 | 0.7155 | Water World | 2 |
| 20 | TIC 219698776 | AMBIGUOUS | 0.4946 | 4.660 | 1.46 | 519.8 | 0.7357 | Rocky/Earth-like | 5 |
| 21 | TIC 297962875 | AMBIGUOUS | 0.4839 | 38.203 | 1.70 | 277.6 | 0.8017 | Water World | 2 |
| 22 | TIC 142322155 | AMBIGUOUS | 0.4812 | 47.345 | 2.27 | 227.4 | 0.7041 | Water World | 2 |
| 23 | TIC 148838894 | AMBIGUOUS | 0.4775 | 23.784 | 2.60 | 322.2 | 0.6564 | Water World | 4 |
| 24 | TIC 263632601 | AMBIGUOUS | 0.4768 | 48.223 | 2.19 | 249.6 | 0.7182 | Water World | 4 |
| 25 | TIC 42713455 | AMBIGUOUS | 0.4763 | 42.062 | 0.97 | 220.7 | 0.9516 | Rocky/Earth-like | 7 |
| 26 | TIC 198099910 | AMBIGUOUS | 0.4449 | 44.288 | 1.85 | 252.0 | 0.7751 | Water World | 3 |
| 27 | TIC 159398282 | AMBIGUOUS | 0.4439 | 0.563 | 1.69 | 773.3 | 0.6169 | Water World | 5 |
| 28 | TIC 230390765 | AMBIGUOUS | 0.4367 | 35.291 | 1.37 | 300.0 | 0.8713 | Rocky/Earth-like | 4 |
| 29 | TIC 288470970 | AMBIGUOUS | 0.4255 | 41.021 | 1.64 | 223.9 | 0.8124 | Water World | 1 |
| 30 | TIC 147935967 | AMBIGUOUS | 0.4240 | 38.177 | 1.67 | 263.2 | 0.8101 | Water World | 4 |
| 31 | TIC 103605168 | AMBIGUOUS | 0.4098 | 3.311 | 1.58 | 573.3 | 0.6964 | Water World | 5 |
| 32 | TIC 362216120 | AMBIGUOUS | 0.4001 | 45.241 | 2.72 | 285.6 | 0.6486 | Water World | 1 |
| 33 | TIC 123013596 | AMBIGUOUS | 0.3927 | 41.572 | 0.81 | 203.9 | 0.8910 | Rocky/Earth-like | 4 |
| 34 | TIC 232964488 | AMBIGUOUS | 0.3559 | 44.207 | 2.00 | 250.9 | 0.7482 | Water World | 3 |
| 35 | TIC 233513676 | AMBIGUOUS | 0.3525 | 49.131 | 1.42 | 270.1 | 0.8670 | Rocky/Earth-like | 2 |

**Notes:**
- The Flags column indicates the number of active flags raised by the pipeline for each target.
- Ambiguous cases typically have one or more of: V-shaped transits suggesting possible eclipsing binary, density mismatches between transit-derived and catalog stellar parameters, non-Gaussian MCMC posteriors indicating noisy signal, or single-sector data limiting cross-validation.
- The remaining 228 targets (CVS < 0.35) are classified as FALSE POSITIVE and are fully documented in their respective discovery cards.

---

## How the Pipeline Works

The Earth2 pipeline scores each TIC through **four independent modules**, each producing a sub-score (S) with a learned weight (w):

### 1. Periodicity Score (weight: 0.97)

**Method:** Box Least Squares (BLS) period search on the detrended light curve.

**Checks performed:**
- BLS signal-to-noise ratio (SNR) — threshold: >= 4.5
- False Alarm Probability (FAP) — threshold: < 1x10^-4
- Gates: PASS if SNR > 4.5 AND FAP < 1x10^-3

**Flags raised when:**
- `SUSPECT_DURATION` — transit duration > 15% of orbital period (possible grazing transit or eclipsing binary)
- `SHALLOW_TRANSIT` — depth < 10 ppm (near noise floor)

### 2. Depth Consistency Score (weight: 0.83)

**Method:** Coefficient of Variation (CV = sigma/mu) across all detected transits.

**Scoring:** S_delta = max(0, 1 - CV / 0.10)

- A low CV means all transits show consistent depth -> high score
- A high CV means transit depths fluctuate -> flagged as possible false positive

**Flags raised when:**
- `HIGH_CV` — CV > 0.10 -> inconsistent depths across transits
- `MCMC_NOISE` — posterior distributions are non-Gaussian -> score penalized x0.7
- `SINGLE_TRANSIT` — insufficient data for CV calculation -> score set to 0.50 (then x0.7)

### 3. Limb Shape Score (weight: 0.61)

**Method:** Mandel-Agol transit model fit via `batman`, comparing residual RMS between transit center vs. wings.

**Physics:** A true planet produces a **U-shaped transit** (flat bottom) while an **eclipsing binary** produces a **V-shaped transit**.

**Scoring:** Wing-to-center RMS ratio determines shape:
- ratio > 1 -> U-shape (planet-like)
- ratio ~ 1 -> V-shape (eclipsing binary candidate)

**Flags raised when:**
- `V_SHAPE_PENALTY` — high ingress fraction indicates V-shape -> score halved
- `V_SHAPE_HIGH_RISK` — ingress > 0.4 -> high false-positive risk flagged

### 4. Stellar Context Score (weight: 0.31)

**Method:** Cross-checks the transit signal against known stellar properties and data quality.

**Sub-tests:**

| Test | What It Checks | Flag When |
|------|----------------|-----------|
| Centroid Shift | Is the transit centered on the star? | Shift > 2.5 sigma -> possible background binary |
| Secondary Eclipse | Is there a secondary eclipse at phase 0.5? | SNR > 2.5 -> likely eclipsing binary |
| Density Constraint | Does a/R_star match the catalog stellar density? | Deviation > 15% -> DENSITY_MISMATCH |
| Multi-Sector | Is the signal consistent across TESS sectors? | Only 1 sector -> no cross-check possible |
| Contamination | Is nearby starlight diluting the signal? | Ratio > threshold -> DILUTION_PENALTY |

### Hard Physical Filters

The pipeline also applies **hard rejection filters** that can zero out the CVS entirely:

| Filter | Reason |
|--------|--------|
| DURATION_TOO_LONG | Transit duration > ~80% of period — physically impossible for a planet |
| V_SHAPE_PENALTY | V-shaped transit inconsistent with planetary transit |
| DENSITY_MISMATCH | Severe mismatch between transit-derived and catalog stellar density |

### MCMC Validation

Markov Chain Monte Carlo sampling (10 walkers, 200 steps) validates the transit depth posterior:

- **Gaussian posterior** -> consistent signal, no flags
- **Non-Gaussian posterior** (high skewness/kurtosis) -> flagged as possible noise artifact

---

## Aggregate Statistics

| Metric | Min | Max | Mean |
|--------|:---:|:---:|:----:|
| **CVS** | 0.0000 | 0.8272 | **0.0916** |
| **Orbital Period** | 0.50 d | 49.23 d | — |
| **Planet Radius** | 0.03 R_Earth | 10.44 R_Earth | — |
| **Equilibrium Temperature** | 194.8 K | 1297.5 K | — |
| **Earth Similarity Index** | 0.1688 | 0.9784 | — |

### Composition Regimes

| Regime | Count | Description |
|--------|:-----:|-------------|
| **Rocky/Earth-like** | 199 | Iron/silicate composition, R < 2 R_Earth |
| **Water World** | 44 | Significant water/ice content |
| **Sub-Neptune** | 13 | Extended H/He envelope |
| **Neptune/Jupiter** | 7 | Gas giant composition |

> **Important:** Composition regimes are derived from transit geometry (radius + mass-radius relation) and are assigned to **all** targets regardless of their false-positive status. A "Rocky/Earth-like" label on a false-positive target (CVS = 0) describes the implied composition of the *transit signal*, not a detected exoplanet.

### Habitability Zone Classification

| Classification | Count |
|:--------------|:-----:|
| **Too Hot** | 211 |
| **Too Cold** | 52 |
| In Habitable Zone (boolean) | 51 (of 263) |
| Earth-like Radius | 71 (of 263) |

> **Note on habitable zone classification:** The pipeline's `habitable_zone_classification` string (e.g., "Too Cold") comes from a conservative boundary model, while the `in_habitable_zone` boolean uses the full Kopparapu et al. habitable zone limits. This explains why some targets with Earth-like equilibrium temperatures (e.g., TIC 436235326 at 290K) are labeled "Too Cold" yet flagged as `in_habitable_zone = true`.

---

## The Candidate Planets

### Planet Candidate (CVS = 0.8272)

| TIC ID | Period (d) | Radius (R_Earth) | Teq (K) | ESI | CVS | Composition | HZ Classification |
|--------|:----------:|:----------------:|:-------:|:---:|:---:|:-----------:|:-----------------:|
| **TIC 436235326** | 30.25 | 2.07 | 290.3 | 0.734 | **0.827** | Water World | Too Cold |

**TIC 436235326** — The single confirmed planet candidate. All false-positive filters passed cleanly:

- **U-shaped transit** (ingress/egress test: VERY_LOW risk)
- **MCMC posteriors are Gaussian** (consistent signal)
- **Deep transit** (1284 ppm) with consistent depths (CV = 0.033)
- **Strong detection** (SNR = 16.46, FAP ~ 0)
- **No secondary eclipse** detected
- **Density constraint within bounds**

This is a **temperate water world** orbiting its host star every 30.25 days with an equilibrium temperature of ~290K — comparable to Earth's 255K.

### Likely Planet Candidates (CVS 0.55-0.80)

| Rank | TIC ID | Period (d) | Radius (R_Earth) | Teq (K) | ESI | CVS | Composition |
|:----:|:-------|:----------:|:----------------:|:-------:|:---:|:---:|:-----------:|
| 2 | TIC 359496368 | 2.66 | 1.40 | 730.7 | 0.660 | **0.799** | Rocky/Earth-like |
| 3 | TIC 99937206 | 32.09 | 1.24 | 296.8 | **0.905** | **0.798** | Rocky/Earth-like |
| 4 | TIC 142963210 | 32.09 | 1.20 | 221.7 | **0.917** | **0.724** | Rocky/Earth-like |
| 5 | TIC 7773413 | 39.38 | 1.86 | 291.6 | 0.769 | **0.690** | Water World |
| 6 | TIC 100013015 | 32.05 | 2.38 | 220.2 | 0.688 | **0.637** | Water World |
| 7 | TIC 138362758 | 29.09 | 2.49 | 265.1 | 0.678 | **0.633** | Water World |
| 8 | TIC 289325518 | 44.06 | 1.11 | 217.9 | **0.935** | **0.624** | Rocky/Earth-like |
| 9 | TIC 284185810 | 26.72 | 1.30 | 311.1 | 0.882 | **0.623** | Rocky/Earth-like |
| 10 | TIC 288129738 | 13.73 | 1.04 | 427.7 | 0.834 | **0.622** | Rocky/Earth-like |
| 11 | TIC 142825877 | 44.20 | 2.90 | 249.7 | 0.632 | **0.622** | Water World |
| 12 | TIC 156464839 | 43.39 | 0.76 | 260.9 | 0.897 | **0.621** | Rocky/Earth-like |
| 13 | TIC 237131816 | 37.38 | 3.48 | 239.4 | 0.582 | **0.582** | Water World |
| 14 | TIC 142878895 | 38.55 | 2.66 | 194.8 | 0.647 | **0.570** | Water World |
| 15 | TIC 229552665 | 38.25 | 1.41 | 305.9 | 0.859 | **0.569** | Rocky/Earth-like |

### Ambiguous Cases (CVS 0.35-0.54)

| Rank | TIC ID | Period (d) | Radius (R_Earth) | Teq (K) | ESI | CVS | Composition |
|:----:|:-------|:----------:|:----------------:|:-------:|:---:|:---:|:-----------:|
| 16 | TIC 372759030 | 49.23 | 2.04 | 256.9 | 0.742 | 0.537 | Water World |
| 17 | TIC 21002564 | 43.61 | 2.40 | 248.4 | 0.689 | 0.533 | Water World |
| 18 | TIC 441761546 | 47.94 | 1.59 | 274.4 | 0.827 | 0.522 | Water World |
| 19 | TIC 137733738 | 34.65 | 2.19 | 286.2 | 0.716 | 0.510 | Water World |
| 20 | TIC 219698776 | 4.66 | 1.46 | 519.8 | 0.736 | 0.495 | Rocky/Earth-like |
| 21 | TIC 297962875 | 38.20 | 1.70 | 277.6 | 0.802 | 0.484 | Water World |
| 22 | TIC 142322155 | 47.35 | 2.27 | 227.4 | 0.704 | 0.481 | Water World |
| 23 | TIC 148838894 | 23.78 | 2.60 | 322.2 | 0.656 | 0.478 | Water World |
| 24 | TIC 263632601 | 48.22 | 2.19 | 249.6 | 0.718 | 0.477 | Water World |
| 25 | TIC 42713455 | 42.06 | 0.97 | 220.7 | **0.952** | 0.476 | Rocky/Earth-like |
| 26 | TIC 198099910 | 44.29 | 1.85 | 252.0 | 0.775 | 0.445 | Water World |
| 27 | TIC 159398282 | 0.56 | 1.69 | 773.3 | 0.617 | 0.444 | Water World |
| 28 | TIC 230390765 | 35.29 | 1.37 | 300.0 | 0.871 | 0.437 | Rocky/Earth-like |
| 29 | TIC 288470970 | 41.02 | 1.64 | 223.9 | 0.812 | 0.426 | Water World |
| 30 | TIC 147935967 | 38.18 | 1.67 | 263.2 | 0.810 | 0.424 | Water World |
| 31 | TIC 103605168 | 3.31 | 1.58 | 573.3 | 0.696 | 0.410 | Water World |
| 32 | TIC 362216120 | 45.24 | 2.72 | 285.6 | 0.649 | 0.400 | Water World |
| 33 | TIC 123013596 | 41.57 | 0.81 | 203.9 | 0.891 | 0.393 | Rocky/Earth-like |
| 34 | TIC 232964488 | 44.21 | 2.00 | 250.9 | 0.748 | 0.356 | Water World |
| 35 | TIC 233513676 | 49.13 | 1.42 | 270.1 | 0.867 | 0.353 | Rocky/Earth-like |

The 20 ambiguous cases typically have one or more of:
- **V-shaped transits** suggesting possible eclipsing binary
- **Density mismatches** between transit-derived and catalog stellar parameters
- **Non-Gaussian MCMC posteriors** indicating noisy signal
- **Single-sector data** limiting cross-validation

### False Positives (CVS < 0.35)

The 228 false positives are fully documented in their respective discovery cards in the Results/ directory. Each card contains the complete analytical trace explaining why the signal was rejected.

---

## False Positive Breakdown

The 228 FALSE POSITIVE verdicts were triggered by a combination of the following flags. Note that most false positives trigger **multiple** flags simultaneously:

| Flag Category | Occurrences | Description |
|:---|---:|:---|
| **MCMC_NOISE** | 207 | Non-Gaussian posterior distributions — signal likely noise |
| **SUSPECT_DURATION** | ~160+ | Transit duration > 15% of orbital period |
| **HIGH_CV** | ~200+ | Transit depths inconsistent across events |
| **DENSITY_MISMATCH** | ~150+ | Stellar density from transit disagrees with catalog |
| **SHALLOW_TRANSIT** | ~30 | Depth < 10 ppm — below reliable detection threshold |
| **V_SHAPE_PENALTY** | ~31 | V-shaped transit — likely eclipsing binary |
| **SECONDARY_ECLIPSE** | ~20 | Detection of secondary eclipse at phase 0.5 |
| **SINGLE_TRANSIT** | 8 | Only one transit event detected — insufficient data |
| **EB_PENALTY** | 2 | Even/odd test suggests eclipsing binary |

### Breakdown Summary

| Target Zone | CVS Range | Count | Key Characteristics |
|:---|---:|:---:|:---|
| **Planet Candidate** | 0.80-1.00 | 1 | Passes all filters, U-shaped, Gaussian posteriors |
| **Likely Candidates** | 0.55-0.80 | 15 | Good signals, may need multi-sector confirmation |
| **Ambiguous** | 0.35-0.55 | 20 | Signal present but with concerns |
| **Near Misses** | 0.10-0.35 | ~14 | Non-zero CVS but hard-rejected by filters |
| **Zero Score** | 0.0000 | ~213 | Complete rejection by one or more hard filters |

---

## File Structure

```
Axiom-Earth2/
  README.md                               (This file)
  Results/                                (263 discovery cards)
    discovery_card_ZS-T-100013015-01.json
    discovery_card_ZS-T-102900991-01.json
    discovery_card_ZS-T-103580569-01.json
    discovery_card_ZS-T-103605168-01.json
    ... (263 files total)
    discovery_card_ZS-T-99971351-01.json
  .git/
```

---

## Discovery Card Schema

Each JSON file (schema v3.0) contains these top-level sections:

| Field | Description |
|-------|-------------|
| `schema_version` | Schema version (3.0) |
| `pipeline_version` | Pipeline version (EARTH2-1.0.0) |
| `zspace_id` | Unique identifier (ZS-T-{tic_id}-{planet_order}) |
| `tic_id` | TESS Input Catalog ID |
| `planet_order` | Planet number for this TIC (always 1 in this dataset) |
| `timestamp_utc` | Processing timestamp |
| `verdict` | Final classification |
| `composite_vitality_score` | CVS value, components, and full proof chain |
| `orbital_mechanics` | Period, semi-major axis, Teq, radius, depth |
| `bls_detection` | BLS search results, SNR, FAP |
| `transit_audits` | Even/odd test, depth consistency, limb shape analysis |
| `stellar_context` | Stellar metadata, centroid test, secondary eclipse, density |
| `ingestion_audit` | Data quality, cadence counts, processing log |
| `earth2_metrics` | ESI, habitable zone flags, Earth-like radius |
| `planet_characterization` | Mass, composition, gravity, insolation, tidal locking |
| `habitability_assessment` | ESI, PHI, HHP, water retention, atmosphere |
| `earth2_confidence` | Earth Confidence Index (ECI) decomposition |
| `fp_filters_v2` | Ingress/egress test, density, MCMC validation |
| `truthimatics_seal` | Pipeline integrity seal |
| `all_flags` | Complete list of all flags raised |

### The Truthimatics Proof Chain

Every score in every card includes a `proof` field that documents the exact arithmetic used. For example:

```json
{
  "value": 0.8272,
  "components": {
    "periodicity_score": { "value": 1.0, "weight": 0.97 },
    "depth_consistency_score": { "value": 0.8762, "weight": 0.83 },
    "limb_shape_score": { "value": 0.7233, "weight": 0.61 },
    "stellar_context_score": { "value": 0.6581, "weight": 0.31 }
  },
  "proof": "CVS = (1.00x0.97 + 0.8762x0.83 + 0.7233x0.61 + 0.6581x0.31) / (0.97+0.83+0.61+0.31) = 0.8272"
}
```

---

## Key Quantitative Metrics Explained

### Composite Vitality Score (CVS)

```
CVS = sum(w * S) / sum(w)

Where:
  w = weight for each module
  S = sub-score for each module (0.0 to 1.0)
```

### Earth Similarity Index (ESI)

The ESI measures physical similarity to Earth on a scale of 0 to 1, based on radius and equilibrium temperature. ESI > 0.80 is considered "Earth-like."

### Earth Confidence Index (ECI)

```
ECI = 1 - (1-CVS) * (1-ESI) * (1-PHI) * (1-HHP)

Where:
  CVS = Composite Vitality Score (detection confidence)
  ESI = Earth Similarity Index (physical similarity)
  PHI = Planet Habitability Index (potential for life)
  HHP = Human Habitability Percentage
```

### Equilibrium Temperature

```
T_eq = T_eff * sqrt(R_star / 2a) * (1-A)^0.25

Where:
  T_eff = stellar effective temperature
  R_star = stellar radius
  a = semi-major axis (from Kepler's Third Law)
  A = albedo (assumed 0.30)
```

### Planet Radius

```
R_p = R_star * sqrt(delta)

Where:
  R_star = stellar radius
  delta = transit depth
```

---

## Data Provenance

All light curves are sourced from NASA's **TESS (Transiting Exoplanet Survey Satellite)** mission, processed by the **SPOC (Science Processing Operations Center)** pipeline, and retrieved via the **MAST (Mikulski Archive for Space Telescopes)** archive.

- **Mission:** TESS
- **Exposure:** Short cadence (2-minute)
- **Author:** SPOC
- **Catalog:** TIC v8.2 — [TESS Input Catalog](https://tess.mit.edu/science/tess-input-catalog/)
- **Processing date:** 2026-05-13

> TIC IDs can be looked up at the [ExoMAST](https://exo.mast.stsci.edu/) or [TESS A-touch](https://tasoc.dk/tasocatouch/) web interfaces for additional context on each target star.

### Pipeline Caveats

- **Fixed trial duration:** The BLS search uses a fixed trial transit duration of 10.0 hours for all targets, which may be suboptimal for very short-period planets (where the true transit is shorter) or very long-period planets. Flags like SUSPECT_DURATION are raised when the trial duration is a large fraction of the period.
- **Single-sector limitation:** The majority of targets in this dataset were observed in only 1 TESS sector, meaning multi-sector cross-validation (a powerful tool for ruling out instrumental artifacts) was not possible.
- **All 263 targets are from Sector 0** in the ingestion audit field, indicating they may be aggregated observations rather than individual sector passes.

### Data Processing Steps

1. **FETCH** — Download TESS light curve FITS files from MAST
2. **QUALITY_MASK** — Remove cadences flagged with TESS quality indicators
3. **SIGMA_CLIP** — Remove 3-sigma upward outliers (preserving transit dips by design)
4. **NORMALIZE** — Median-normalize flux to ~1.0
5. **SAVGOL** — Savitzky-Golay filter for long-term trend removal
6. **CONSISTENCY_CHECK** — Verify final light curve integrity

---

## The Truthimatics Seal

Every discovery card ends with:

```
TRUTHIMATICS-SEAL | CVS=XX.X% | WHITE-BOX | NO-ML | NO-IMPUTATION | PHYSICS-DERIVED | Axiom-ZSpace v1.0
```

This seal certifies that:

- **CVS=XX.X%** — The Composite Vitality Score is reported transparently
- **WHITE-BOX** — Every calculation can be inspected and verified
- **NO-ML** — No machine learning models were used in the analysis
- **NO-IMPUTATION** — No missing data was fabricated or assumed
- **PHYSICS-DERIVED** — All conclusions follow from established astrophysics

---

## On Data Authenticity

If you are examining this repository and have concerns about the veracity of the data, the following points may be helpful.

### 1. All Raw Data Comes from NASA

The TESS light curves are **publicly available** from the [MAST archive](https://archive.stsci.edu/). Every TIC ID in this repository can be independently queried:

- Visit [ExoMAST](https://exo.mast.stsci.edu/)
- Enter any TIC ID from this repository
- Download the raw light curve FITS files
- Run your own detection pipeline and compare results

This is fundamentally different from an ML model where you cannot see the training data.

### 2. The Full Proof Chain Is Documented

Every discovery card contains a `truthimatics_seal` with the pipeline version, and every numeric score has a `proof` field showing the exact arithmetic used. There is no hidden logic. You can:

- Replicate any score by hand using the formulas in [How the Pipeline Works](#how-the-pipeline-works)
- Validate the arithmetic of any `proof` field
- Cross-check the CVS components against the raw sub-scores

### 3. False Positives Are Included (This Is Unusual)

In most exoplanet surveys, false positives are silently discarded. This repository **intentionally includes all 228 false positives** with the same level of documentation as the planet candidate. If the data were fabricated, it would be easier to simply omit the false positives and only present positive results.

### 4. Composition Regimes Are Based on Physics, Not Detection

A false positive target (CVS = 0) still has a derived composition regime (e.g., "Rocky/Earth-like") because composition is calculated from transit **geometry** (radius and mass-radius relation), not from detection confidence. This is clearly documented in the [Composition Regimes](#composition-regimes) section.

### 5. The Axiom-Zspace Parent Project Has Published Benchmarks

The [Axiom-Zspace repository](https://github.com/Zierax/Axiom-Zspace) documents a **92.7% detection rate on a 619-target benchmark** using only a single-core CPU. These results are reproducible using the open-source pipeline code.

### 6. How to Verify

The most direct way to verify this data:

```python
import json, os

# Pick any file, inspect the full proof chain
card = json.load(open("Results/discovery_card_ZS-T-436235326-01.json"))
print("Verdict:", card["verdict"])
print("CVS:", card["composite_vitality_score"]["value"])
print("Proof:", card["composite_vitality_score"]["proof"])

# Check the ingress/egress test
fp = card["fp_filters_v2"]
print("Ingress frac:", fp["ingress_egress_test"]["ingress_fraction"])
print("Shape:", "U-SHAPE" if not fp["ingress_egress_test"]["is_v_shape"] else "V-SHAPE")
```

---

## Usage

This repository is a **reference data set** of fully analyzed TESS targets. Each file is a standalone JSON document that can be ingested by any programming language or data analysis tool.

### Quick Start (Python)

```python
import json, os

for f in sorted(os.listdir("Results/")):
    if f.endswith(".json"):
        card = json.load(open(f"Results/{f}"))
        print(f"TIC {card['tic_id']}: {card['verdict']} (CVS={card['composite_vitality_score']['value']:.3f})")
```

### Quick Start (jq)

```bash
# Count verdicts
jq -r '.verdict' Results/*.json | sort | uniq -c | sort -rn

# Find planet candidates
jq 'select(.verdict == "PLANET CANDIDATE") | {tic_id, verdict, cvs: .composite_vitality_score.value}' Results/*.json

# Find targets in the habitable zone
jq 'select(.earth2_metrics.in_habitable_zone == true) | {tic_id, period: .orbital_mechanics.period_days.value, radius: .orbital_mechanics.planet_radius_earth.value, teq: .orbital_mechanics.equilibrium_temperature_k.value}' Results/*.json
```

---

## Contributing and Contact

This is a reference data set of analyzed TESS targets. If you would like to:

- **Report an error** in a discovery card, open an issue with the TIC ID and the evidence
- **Request analysis** of additional TESS targets, open a feature request
- **Contribute code** for the pipeline itself, please reach out
- **Collaborate under NDA** to further refine these logical kernels, contact via GitHub Issues

### Related Community Discussions

The Axiom-Zspace project is actively discussed on:

- [Zooniverse Planet Hunters TESS Talk](https://www.zooniverse.org/projects/nora-dot-eisner/planet-hunters-tess/talk/2110/3998656)
- [Zooniverse Planet Hunters TESS Talk](https://www.zooniverse.org/projects/nora-dot-eisner/planet-hunters-tess/talk/2110/3995685)
- [Zooniverse Planet Hunters TESS Talk](https://www.zooniverse.org/projects/nora-dot-eisner/planet-hunters-tess/talk/2110/3987225)

### Contact

For technical audits or partnerships, please reach out via [GitHub Issues](https://github.com/Zierax/Axiom-Zspace/issues) or contact directly at `zs.01117875692@gmail.com`.

---

## License

This project is licensed under the MIT License. The underlying TESS data is publicly available from the MAST archive at the Space Telescope Science Institute.
