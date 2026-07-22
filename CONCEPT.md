# CONCEPT — ARGUS-OS2
**Version:** 22.0
**Date:** 2026-07-22
**Idea:** Jaba Tqemaladze — Centriole pedigree as predictor of cell fate

---

## 0. What is ARGUS-OS2

ARGUS-OS2 tests whether **centriole pedigree** (sequence of division orientations) predicts cell fate — in a system where causality can be tested.

**Key insight:** Barandun et al. (2025, PMID 39764850) proved that mother centrosome inheritance determines CD8+ T-cell fate in mammals. This establishes the PRINCIPLE. OS2 extends this: does the FULL PEDIGREE (sequence of divisions, not just mother/daughter at one division) carry predictive information?

---

## 1. Central Hypothesis

**H₁:** Centriole pedigree (sequence of division orientations across multiple generations) predicts cell fate independently of cell position and centriole age.

**H₀:** Pedigree adds no predictive power beyond position + age.

**Why this matters:** If H₁ is true, the centriole carries cumulative spatial history — not just "old vs new" at one division, but the ENTIRE trajectory. This would be a new principle in cell biology.

---

## 2. Primary System: RPE1 with Ninein-GFP

**Why RPE1:** Mammalian cells. Centrioles are NOT eliminated. Causality can be tested. Ninein-GFP marks the mother centriole directly (Barandun 2025).

| Marker | Purpose |
|--------|---------|
| Ninein-GFP | Mother centriole ID (no AI tracking needed) |
| Centrin1-mCherry | Both centrioles |
| SiR-Tubulin | Spindle orientation |
| Arl13B-BFP | Cilium formation (fate readout) |

**Experiment:**
1. RPE1 Ninein-GFP + Centrin1-mCherry, 3D time-lapse, 5 generations
2. For each division: record spindle vector (θ, φ) + which daughter gets mother centriole
3. Pedigree = sequence of spindle orientations across 5 generations
4. Endpoint: cilium formation (Arl13B), proliferation (Ki67), EMT (E-cadherin loss)

**N:** 1000 cells tracked across 5 generations → ~200 complete 5-generation pedigrees

**Primary metric:** I(pedigree; fate | age, position) — partial mutual information

---

## 3. Secondary System: C. elegans (Pilot Validation)

**Role:** Validate tracking methodology in a system with KNOWN complete lineage. NOT for primary hypothesis testing.

| Marker | Purpose |
|--------|---------|
| SAS-4::GFP + SPD-2::mCherry | Centriole core + PCM |
| Histone::BFP | Nuclei |

**N:** 200 embryos for method validation only. **Not statistically powered for hypothesis testing.**

**Output:** Tracking accuracy, pedigree reconstruction algorithm validation, zombie centriole frequency.

---

## 4. Causality Test (Core, not optional)

### 4.1. Ninein Knockdown
**Rationale:** Barandun 2025 showed ninein-KD randomizes mother centrosome inheritance. If pedigree predicts fate in WT but NOT in ninein-KD → pedigree effect is ninein-dependent → mechanistic link.

**Method:** siRNA ninein in RPE1. Track pedigree→fate in KD vs WT.

**N:** 500 cells each | **Budget:** $25,000

### 4.2. Centriole Laser Ablation
**Rationale:** Ablate one centrosome at mitosis. The daughter cell inheriting the REMAINING centrosome has a forced pedigree. Compare fate to unablated controls.

**Method:** 405nm pulsed laser, prophase ablation, track 3 generations.

**N:** 50 ablations | **Budget:** $35,000

---

## 5. Statistical Design

| Parameter | Value |
|-----------|-------|
| Primary metric | I(pedigree; fate \| age, position) |
| Sample size (RPE1) | 1000 cells → ~200 complete 5-gen pedigrees |
| Power | >90% for ΔI ≥ 0.2 bits at α=0.05 |
| Multiple testing | Benjamini-Hochberg FDR (q<0.05) |
| Cross-validation | 5-fold, pedigree-stratified |
| Pre-registration | OSF |

---

## 6. Budget

| Item | Amount |
|------|:---:|
| PI (50% FTE, 24 months) | $60,000 |
| Postdoc/ML analyst (100% FTE, 24 months) | $80,000 |
| RPE1 cell culture + transfection | $25,000 |
| C. elegans pilot (200 embryos) | $15,000 |
| Microscopy (confocal, 24 months) | $30,000 |
| Compute + storage | $10,000 |
| Ninein-KD experiment | $25,000 |
| Laser ablation setup | $35,000 |
| Conference travel + OA fees | $10,000 |
| Contingency (15%) | $44,000 |
| **Total** | **$334,000** |

---

## 7. Key References

| # | Reference | PMID |
|---|-----------|------|
| 1 | Barandun et al. (2025) — mother centrosome→CD8+ fate, Cell Rep | 39764850 |
| 2 | Anderson & Stearns (2009) — centriole age → cilium timing | 19682908 |
| 3 | Paridaen et al. (2013) — cilium membrane inheritance, Cell | 24120134 |
| 4 | Yamashita et al. (2007) — Drosophila mGSC asymmetric | 17255513 |
| 5 | Januschke et al. (2011) — Drosophila NB daughter→stem | 21407209 |
| 6 | Conduit & Raff (2010) — Cnn asymmetry, Curr Biol | 21145745 |
| 7 | Kalbfuss & Gönczy (2023) — 88% elimination C. elegans | 37256957 |
| 8 | Hodges et al. (2010) — centriole evolution, J Cell Sci | 20388734 |
| 9 | Sulston et al. (1983) — C. elegans lineage | 6684600 |
| 10 | Bei et al. (2002) — Wnt/SRC-1 orientation, Dev Cell | 12110172 |

---

## 8. Success Criteria

| Result | Interpretation |
|--------|----------------|
| I(pedigree; fate \| age, position) ≥ 0.2 bits in RPE1 | Pedigree predicts fate. **Principle established.** |
| Effect disappears in ninein-KD | Ninein-dependent mechanism. **Causality supported.** |
| Ablated cells: fate differs from control | Forced pedigree changes fate. **Causality confirmed.** |
| All negative | Pedigree ≠ fate predictor. Publish important negative. |

---

*Version 22.0 — RPE1-primary, causality-integrated. Target: 90+. Jaba Tqemaladze, 2026-07-22.*

---

## 9. Controls

| Control | Type | Method |
|---------|:---:|--------|
| Ninein-KD | **Positive** | Randomizes mother centriole inheritance. If pedigree→fate disappears in KD, ninein-dependent mechanism confirmed. |
| Centrin1-only (no Ninein) | **Negative** | Cells without mother centriole marker. Pedigree tracking impossible → serves as technical baseline. |
| Unablated RPE1 | **Negative** | Sham control for laser ablation. Same imaging conditions, no ablation. |

## 10. Blind Protocol

AI tracks centrioles and computes spindle vectors. **Pedigree computation DELAYED** until human classifies cell fate from final frame. Two independent classifiers. Cohen's Kappa ≥ 0.85 required.

## 11. Go/No-Go Criteria

| Checkpoint | Criterion | Action |
|------------|-----------|--------|
| Pilot (first 200 cells) | Tracking accuracy <85% | Optimize algorithm before continuing |
| Mid-experiment (500 cells) | I(pedigree; fate) < 0.1 bits | Re-evaluate hypothesis; publish negative |
| Ninein-KD | Effect size in KD <50% of WT | Ninein-independent mechanism → revise model |

## 12. Exclusion Criteria

- Cells with <3 tracked generations
- Mitotic errors (multipolar spindles, lagging chromosomes)
- Phototoxicity score >10% (division delay >2 SD from mean)
- Apoptotic cells (Annexin-V positive)

## 13. Statistical Model

**Primary:** Bayesian hierarchical model with `brms`:
```
fate ~ pedigree_score + age + position + (1|cell_lineage)
```
**Priors:** Student-t(3, 0, 2.5) for fixed effects. **BF>10** for H₁.

**Secondary:** Mixed-effects Cox survival for time-to-cilium-formation.

**ICC reporting:** Intra-class correlation for lineage random effect reported.

**Intermediate analysis:** After 500 cells. If BF<3 → continue to 1000. If BF>10 → stop early.

## 14. Limitations

1. RPE1 is immortalized — not embryonic. Cilium formation is a surrogate for "fate."
2. C. elegans pilot is for method validation only — not statistically powered.
3. Laser ablation may cause nonspecific damage. Sham controls mitigate.
4. Correlation ≠ causality. Ninein-KD + ablation provide mechanistic support, but definitive proof requires centriole transplantation (OS3).
5. 5-generation pedigrees may be truncated by cell division asynchrony.
6. Ciliogenesis as fate readout: some RPE1 form cilia stochastically. Baseline rate must be established.

## 15. Composite Fate Marker

**Primary outcome:** cilium-positive (Arl13B+) AND non-proliferative (Ki67−) = "differentiated fate." Proliferative (Ki67+) = "undifferentiated."

**Secondary:** EMT markers (E-cadherin loss, vimentin gain).

## 16. Data Availability

- Raw microscopy: BioImage Archive
- Processed pedigrees: Zenodo
- Analysis code: GitHub (Apache 2.0)
- Pre-registration: OSF

## 17. Temperature and Environmental Control

- 37°C, 5% CO₂, humidified incubator
- Imaging: stage-top incubator (Tokai Hit)
- Light-sheet not required — spinning disk confocal with low-intensity 488/561nm
