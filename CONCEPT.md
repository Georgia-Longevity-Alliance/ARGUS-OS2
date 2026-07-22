# CONCEPT — ARGUS-OS2

**Version:** 5.0
**Date:** 2026-07-22
**Idea:** Jaba Tqemaladze — Centriole as material carrier of spatial lineage memory

---

## 0. What is ARGUS-OS2

ARGUS-OS2 tests the hypothesis: **centriole pedigree predicts differentiation fate convergence.**

The mother/daughter centriole is identified by CONTINUOUS AI TRACKING (24/7), not by molecular markers. Data collected by ARGUS-OS1. OS2 analyzes: does centriole pedigree predict cell fate?

**Principle:** If a centriole passed through "up→right→posterior", the cell may become a neuron. If "down→left→anterior" — skin. Centriole pedigree predicts fate. The recording mechanism (structural or otherwise) is beyond this project's scope.

---

## 1. Central Hypothesis

**Spatial centriole pedigree (sequence of division orientations) predicts cell fate. The centriole is a candidate material carrier of this information.**

### 1.1. Principle

In embryogenesis, cell position determines fate. Spatial centriole pedigree — the sequence "up→right→posterior→..." — IS the record of where the cell was. If this information is stored anywhere, fate can be predicted.

### 1.2. C. elegans — Principle Visualization

C. elegans: complete cell lineage known (Sulston & Horvitz 1977). Centriole pedigree of each cell → its fate. Embryo is transparent. All divisions visible.

**C. elegans is used NOT to prove centriole = memory, but as VISUALIZATION:** show that centriole pedigree correlates with fate in a system where everything is visible.

**Gönczy (pers. comm., 21 Jul 2026):** Centrioles retained in terminally differentiated cells of the adult somatic gonad likely remain for a functional reason — supporting the OS2 hypothesis.

### 1.3. Key Predictions

**Prediction 1 (Convergence):** Different centriole pedigrees → same fate. Pedigrees converge.

**Prediction 2 (Pedigree > Age):** Centriole pedigree predicts fate BETTER than centriole age.

```
Centriole A: up → right → posterior → fate: neuron
Centriole B: up → left  → anterior  → fate: neuron

Different pedigrees. Same fate.
Therefore: pedigrees A and B CONVERGED — led to the same result.
```

This means the space of centriole pedigrees is NOT one-to-one with fates. There are **equivalence classes** — groups of different pedigrees converging to one fate.

---

## 2. Primary Experiment: Pedigree Convergence

### 2.1. Logic

Take 4 centrioles of the SAME age (3 divisions):

| Centriole | Pedigree (∥=parallel, ⟂=perpendicular) | Fate prediction |
|-----------|----------------------------------------|-----------------|
| A | ∥ → ∥ → ⟂ | neuron |
| B | ⟂ → ∥ → ∥ | skin |
| C | ∥ → ⟂ → ⟂ | **neuron** (≠ B, same age) |
| D | ⟂ → ⟂ → ∥ | **skin** (≠ A, same age) |

**If age is the only factor:** fate A=B=C=D (all age 3). ❌ Hypothesis disproven.
**If pedigree is a factor:** fate A=C≠B=D. ✅ Hypothesis confirmed.

### 2.2. Experimental Design

| Step | Action |
|:---:|--------|
| 1 | 3D time-lapse RPE1, 3 generations, Centrin1-GFP + SiR-Tubulin |
| 2 | Record pedigree (∥/⟂ for C. elegans, angle θ for RPE1) for 200+ cells |
| 3 | Cluster pedigrees → find convergent groups |
| 4 | Endpoint: cell fate (Arl13B). A=C? B=D? |

### 2.3. Success Criteria

| Result | Verdict |
|--------|---------|
| Fate A=C≠B=D | 🔴 Hypothesis proven. Pedigree predicts fate. |
| Fate A=B=C=D | ❌ Hypothesis disproven. Age is sufficient. |
| Partial convergence (A=C in 70%) | 🟡 Pedigree is a factor, not the only one. |

---

## 3. Two Phases

| Phase | System | Question |
|:---:|--------|----------|
| 1 | C. elegans | Does the PRINCIPLE work? Pedigree→fate in a fully visible system. |
| 2 | RPE1 (ARGUS-OS1 data) | Is the CENTRIOLE the carrier? Is the principle universal? |

### Phase 1: C. elegans

| Step | Method |
|:---:|--------|
| 1 | C. elegans embryo, histone::GFP + γ-tubulin::GFP |
| 2 | 3D time-lapse zygote→~100 cells |
| 3 | Full division tree reconstruction |
| 4 | Per cell: pedigree = sequence of XYZ vectors |
| 5 | Cell fate: known (Sulston 1977) or markers |

**Success criterion:** I(pedigree; fate) > 0.5 bits → principle works. Proceed to Phase 2.

### Phase 2: RPE1

| Step | Method |
|:---:|--------|
| 1 | RPE1-hTERT Centrin1-GFP + SiR-Tubulin, 3D time-lapse |
| 2 | 3-4 generations, 48-72h |
| 3 | Per division: spindle XYZ vector |
| 4 | Centriole pedigree = sequence of division vectors |
| 5 | Endpoint: fate (cilium — Arl13B, Ki67) |

**Success criterion:** Pedigree predicts fate BETTER than age → centriole = lineage memory carrier.

---

## 4. Statistical Design

### Pilot (C. elegans)
**AUC test:** N=100 centrioles (20 from 5 different pedigrees). SVM classifier. H₀: AUC=0.5.

### Main (RPE1)
**Conditional entropy:** 200 cell pairs. H(fate) vs H(fate|pedigree). ΔI ≥ 0.3 bits → N=200 gives power >80%.

---

## 5. Budget

| Phase | System | Duration | Budget |
|-------|--------|:---:|:---:|
| 1: C. elegans | Embryo time-lapse + analysis | 8 weeks | $5,000 |
| 2: RPE1 | OS1 data analysis | 12 weeks | $8,000 |
| **Total** | | **20 weeks** | **$13,000** |

---

## 6. Key References

| # | Reference | PMID |
|---|-----------|------|
| 1 | Sulston & Horvitz (1977) — C. elegans post-embryonic lineage | 838129 |
| 2 | Sulston et al. (1983) — embryonic lineage | 6684600 |
| 3 | Anderson & Stearns (2009) — centriole age → cilium timing | 19682908 |
| 4 | Yamashita et al. (2007) — Drosophila mGSC asymmetric inheritance | 17255513 |
| 5 | Wang et al. (2009) — mouse radial glia asymmetric inheritance | 19829375 |
| 6 | Erpf & Mikeladze-Dvali (2020) — Dendra2::SAS-4 tracking | DOI:10.17912/micropub.biology.000286 |
| 7 | Kalbfuss & Gönczy (2023) — 88% centriole elimination | 37256957 |
| 8 | Magescas et al. (2023) — SAS-1 loss initiates elimination | 37987153 |
| 9 | Coffman et al. (2016) — MT asymmetry C. elegans | 27733624 |
| 10 | Croisier et al. (2025) — EM centrioles in rectal cells | 40475707 |
| 11 | Januschke et al. (2011) — Drosophila NB centrosome | 21407209 |
| 12 | Pintard & Bowerman (2019) — mitotic division C. elegans | 30626640 |

---

*Version 5.0 — English. From molecular causality to informational prediction. Jaba Tqemaladze, 2026-07-22.*
