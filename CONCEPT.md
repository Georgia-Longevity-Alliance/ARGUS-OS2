# CONCEPT — ARGUS-OS2

**Version:** 15.0
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
**Caveat:** In C. elegans, division orientation is determined by cell position in the morphogenetic field (Sulston 1983). Pedigree IS therefore a position marker — not an independent variable. Correlation between pedigree and fate is EXPECTED trivially. The non-trivial question: does pedigree predict fate BETTER than position alone? This is tested by comparing cells at similar positions but with different pedigrees (sister cells at asymmetric divisions).
**Position control strategy:** compare sister cells from asymmetric divisions — identical position, identical mother, identical age, DIFFERENT pedigrees (one daughter gets old centriole, one gets new). This is the only comparison where pedigree is the sole systematic difference. N = all asymmetric divisions in 100-embryo dataset from OS1.
**Inter-embryo control:** cells at identical positions in different embryos (invariant lineage) with different pedigrees (due to stochastic centrosome inheritance — Erpf 2020). This is the complementary control: same position, different pedigree.

In embryogenesis, cell position determines fate. Spatial centriole pedigree — the sequence "up→right→posterior→..." — IS the record of where the cell was. If this information is stored anywhere, fate can be predicted.

### 1.2. C. elegans — Principle Visualization
**Critical limitation:** Kalbfuss & Gönczy (2023) demonstrated that centriole elimination is stereotyped and cell-type-determined — "it is not cell age, but instead cell fate, that determines whether and when centrioles are eliminated." This ESTABLISHES a functional centriole↔fate link, supporting OS2's rationale: if fate determines centriole status, then centriole pedigree should carry predictive information about fate. We test this in the cells that retain centrioles.
**Structural caveat:** C. elegans centrioles are evolutionarily reduced (singlet microtubules) but retain the conserved 14-protein core (Hodges et al. 2010, PMID 20388734). Generalizability to mammals requires RPE1 validation in Phase 2.

C. elegans: complete cell lineage known (Sulston & Horvitz 1977). Centriole pedigree of each cell → its fate. Embryo is transparent. All divisions visible.

**C. elegans is used NOT to prove centriole = memory, but as VISUALIZATION:** show that centriole pedigree correlates with fate in a system where everything is visible.


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
| 4 | Endpoint: cell fate panel — Arl13B (cilium state), acetylated-α-tubulin (cilium axoneme), Ki67 (proliferation), E-cadherin (epithelial integrity). RPE1 is epithelial — neuronal markers not applicable.. A=C? B=D? |

### 2.3. Success Criteria

### 2.4. Phase 1→Phase 2 Checkpoint
After Phase 1 (C. elegans):
- If I(pedigree; fate | position, age) < 0.1 bits → STOP (pedigree adds nothing beyond position+age). Hypothesis unsupported. Publish negative result.
- If 0.1 ≤ I(pedigree; fate | position, age) < 0.3 bits → PROCEED to Phase 2 with N increased to 500 cells.
- If I ≥ 0.4 bits → PROCEED to Phase 2 as planned (N=500).
- Borderline OS1 data (<1.5μm precision, 10-15% phototoxicity): flagged for sensitivity analysis, excluded from primary analysis.


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
| 1 | C. elegans embryo, SAS-4::GFP + SPD-2::mCherry + Histone::BFP (MANDATORY triple marker: SAS-4 for centriole core, SPD-2 for PCM, Histone for nuclei) |
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
**AUC test:** N=500 centrioles screened to yield ~60 with retained centrioles (12% of 500, accounting for 88% elimination — Kalbfuss 2023). SVM classifier. H₀: AUC=0.5.

### Main (RPE1)
**Conditional entropy:** 200 cell pairs. H(fate) vs H(fate|pedigree). ΔI ≥ 0.3 bits → N=500 gives power >80%.

---










## 4a. Age-Pedigree Separation Strategy
Age and pedigree are correlated (older centrioles have longer pedigrees). To separate: (a) match centrioles by division count, compare within same-age groups; (b) include age as covariate in conditional entropy calculation; (c) use partial mutual information I(pedigree; fate | age) as primary metric.
**Cell position tracking:** XYZ coordinates of cell centroid recorded at each timepoint. Included as covariate: I(pedigree; fate | age, position). This addresses the "pedigree = position marker" critique head-on./

## 5a. OS1 Data Quality Criteria
Inclusion: (a) ≥3 tracked divisions, (b) XYZ vector precision <1μm, (c) phototoxicity score <10% division rate drop. Exclusion: abnormal cell behavior, incomplete lineage.

## 5c. Limitation: Correlation ≠ Causality
Even if I(pedigree; fate) > 0.5 bits, this demonstrates PREDICTIVE power, not causality. Pedigree may be a marker of position (which REALLY determines fate). OS3 (centriole transplantation) is required to test causality. This is explicitly a Phase 1 predictive study.

## 5b. Alternative Hypothesis
**H₀_alt:** Centriole pedigree is a MARKER of cell fate (determined by position/morphogens), not a CAUSE. If pedigree predicts fate but experimental perturbation of pedigree does not change fate → centriole is a marker, not a carrier.
**Test:** OS3 (centriole transplantation) — if transplanting a "bad pedigree" centriole into a "good fate" cell changes fate → causality proven. If not → centriole is a correlated marker.

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
| 11 | Januschke et al. (2011) — Drosophila NB: DAUGHTER centriole→stem cell, MOTHER→differentiating (context-dependent, opposite of mGSC) | 21407209 |
| 16 | **Conduit & Raff (2010)** — Cnn dynamics drive centrosome asymmetry in Drosophila NB, Curr Biol | 21145745 |
| 14 | Bei et al. (2002) — SRC-1 + Wnt control cleavage orientation in C. elegans, Dev Cell | 12110172 |
| 15 | **Targeted mother centrosome localization in CD8+ T-cells promotes memory formation (2025)** — direct evidence of centriole→fate in mammals, Cell Rep | 39764850 |
| 13 | Hodges et al. (2010) — evolutionary history of centriole, J Cell Sci | 20388734 |
| 12 | Pintard & Bowerman (2019) — mitotic division C. elegans | 30626640 |
| 23 | **Balestra, von Tobel & Gönczy (2015)** — paternal centrioles persist 10 generations in C. elegans, Cell Res | 25906994 |
| 24 | **Sugioka et al. (2017)** — SAS-7 acts upstream of SPD-2 in centriole assembly, eLife | 28092264 |
| 17 | **Rebollo et al. (2007)** — functionally unequal centrosomes in Drosophila, Dev Cell | 17336911 |
| 18 | **Viol et al. (2020)** — Nek2 kinase displaces distal appendages, J Cell Biol | 32211891 |
| 19 | **Tqemaladze (2022)** — centriole accumulation in stem cell aging, Mol Biol Rep | 36583780 |

---

*Version 15.0 — English. From molecular causality to informational prediction. Jaba Tqemaladze, 2026-07-22.*

### Salary Breakdown

| Item | Amount |
|------|:---:|
| PI (25% FTE, 20 weeks) | $25,000 |
| ML/Data analyst (50% FTE, 20 weeks) | $40,000 |
| C. elegans reagents + microscopy | $20,000 |
| Compute + storage | $5,000 |
| Contingency (10%) | $10,000 |
| Conference travel + OA fees | $5,000 |
| **Total** | **$105,000** |

> OS2 is a computational analysis project using existing OS1 data. No new microscope hardware required.

---

## 6. Enrichment Experiments (Optional, +$85K)

These experiments transform OS2 from pure correlation analysis to mechanistic causality testing.

### E1: Wnt Perturbation — Change Pedigree, Measure Fate ($25K) [MANDATORY — included in core]
**Rationale:** Bei et al. (2002) showed Wnt/SRC-1 controls cleavage orientation in C. elegans. If we perturb Wnt signaling (RNAi or temperature-sensitive mutants), we CHANGE the pedigree WITHOUT changing cell position. If fate follows the NEW pedigree → causality supported.
- **Strains:** Wnt pathway mutants (mom-2, wrm-1) or RNAi
- **N:** 20 embryos per condition × 3 conditions = 60 embryos
- **Duration:** 4 weeks
- **Budget:** $25,000

### E2: Centriole Laser Ablation — Remove One Centriole, Track Fate ($35K)
**Rationale:** Ablate one centrosome at 2-cell stage. The daughter cell inheriting the remaining centrosome has a FORCED pedigree (no choice in orientation). Compare its fate to unablated controls.
- **Setup:** 405nm pulsed laser on spinning disk
- **N:** 30 embryos
- **Duration:** 6 weeks
- **Budget:** $35,000

### E3: Ninein-GFP in RPE1 — Direct Mother Centriole Marker ($25K)
**Rationale:** Barandun et al. (2025, PMID 39764850) showed ninein marks the mother centriole and its knockout randomizes CD8+ T-cell fate. Ninein-GFP in RPE1 enables DIRECT identification of mother vs daughter centriole without AI tracking. Tests whether mother centriole inheritance predicts cilium formation timing.
- **Cell line:** RPE1 Ninein-GFP + Centrin1-mCherry
- **N:** 500 cells
- **Duration:** 6 weeks
- **Budget:** $25,000

### Budget with Enrichment

| Component | Base | +E1 | +E2 | +E3 | Full |
|-----------|:---:|:---:|:---:|:---:|:---:|
| Personnel | $35K | +$10K | +$15K | +$10K | $70K |
| Reagents/Equipment | $15K | +$12K | +$18K | +$12K | $57K |
| Contingency | $2K | +$3K | +$2K | +$3K | $10K |
| **Total** | **$52K** | **$25K** | **$35K** | **$25K** | **$137K** |

> Full package: $137K — transforms OS2 from correlation to mechanism. E1+E2 recommended minimum ($112K).

### E4: Comparative Analysis — C. elegans vs Drosophila vs RPE1 ($40K)
**Rationale:** Test whether pedigree→fate principle is universal or lineage-specific. Three systems with different centriole biology:
- **C. elegans:** evolutionarily reduced centrioles, 88% elimination, invariant lineage
- **Drosophila NB:** canonical centrioles, asymmetric inheritance (daughter→stem, mother→differentiate)
- **RPE1:** mammalian epithelial, no elimination, cilium as fate readout

**Comparison matrix:**
| Feature | C. elegans | Drosophila NB | RPE1 |
|---------|:---:|:---:|:---:|
| Centriole structure | Singlets (reduced) | Triplets (canonical) | Triplets (canonical) |
| Pedigree→fate known? | ❌ Unknown | ✅ Januschke 2011 | ❌ Unknown |
| Lineage map | ✅ Complete (Sulston) | ❌ Stochastic | ❌ Stochastic |
| Elimination | 88% (Kalbfuss) | None | None |
| Causality test | Wnt perturbation | Laser ablation | Ninein-GFP |
| Budget | $37K (base+E1) | $35K (E2 adapted) | $25K (E3) |

**Comparative analysis plan:**
1. Compute I(pedigree; fate) in all 3 systems using harmonized pipeline
2. Meta-analysis: is the effect size conserved across species?
3. If I > 0.3 in all 3 → universal principle. If only in Drosophila → lineage-specific.

**Duration:** 8 weeks | **Budget:** $40,000 (includes Drosophila facility access + collaborative agreement)

### Full Enrichment Budget Summary

| Component | Base OS2 | +E1 | +E2 | +E3 | +E4 | **Full** |
|-----------|:---:|:---:|:---:|:---:|:---:|:---:|
| Personnel | $35K | +$10K | +$15K | +$10K | +$18K | **$88K** |
| Reagents/Equip | $15K | +$12K | +$18K | +$12K | +$18K | **$75K** |
| Contingency | $2K | +$3K | +$2K | +$3K | +$4K | **$14K** |
| **Total** | **$52K** | **$25K** | **$35K** | **$25K** | **$40K** | **$177K** |

### E5: Heidenhain's Iron Haematoxylin — Endpoint Validation of Zombie Centrioles ($15K)
**Rationale:** Boveri's 1900 method (Scheer 2014, PMID 25047623). Iron haematoxylin stains centriole microtubules directly — NOT dependent on GFP fluorescence. Critical for OS2: verifies that SAS-4-GFP(+) SPD-2-mCherry(-) "zombie" centrioles ARE structurally intact centrioles, not protein aggregates.
| 20 | **Rebollo et al. (2007)** — functionally unequal centrosomes in Drosophila neural stem cells, Dev Cell | 17336911 |
| 21 | **Viol et al. (2020)** — Nek2 kinase displaces distal appendages from mother centriole, J Cell Biol | 32211891 |
| 22 | **Tqemaladze (2022)** — centriole accumulation in stem cell aging, Mol Biol Rep | 36583780 |

**Protocol:**
1. After 100-cell stage imaging → fix embryos
2. Heidenhain's iron haematoxylin staining (2.5% iron-alum mordant, 0.5% haematoxylin, differentiation under microscope)
3. Compare GFP(+) structures vs iron-stained structures in same embryo
4. **Key metric:** fraction of "zombie" centrioles (SAS-4+/SPD-2-) that are iron-positive → true centrioles vs aggregates

**N:** 30 embryos | **Duration:** 3 weeks | **Budget:** $15,000

| Item | Cost |
|------|:---:|
| Reagents (iron-alum, haematoxylin, Bouin's) | $2,000 |
| Microscopy time (brightfield + fluorescence overlay) | $5,000 |
| Personnel (histology + analysis) | $6,000 |
| Contingency (10%) | $10,000 |
| Conference travel + OA fees | $5,000 |

### Updated Full Budget

| Component | Base | +E1 | +E2 | +E3 | +E4 | +E5 | **Full** |
|-----------|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
| **Total** | $52K | $25K | $35K | $25K | $40K | $15K | **$192K** |

### E7: Proteasome Inhibition — Block Elimination, Track Pedigree ($20K)
**Rationale:** If centriole elimination is proteasome-dependent (Pierron 2023), blocking proteasomes should extend centriole lifespan. This creates MORE cells with tracked pedigrees — directly addressing the 88% elimination problem. MG132 or bortezomib treatment on 30 embryos.
**N:** 30 embryos × 2 conditions | **Duration:** 4 weeks | **Budget:** $20,000

### E6: Planaria — Centriole Fate During Regeneration ($30K)
**Rationale:** Planarians regenerate entire body from tiny fragments via neoblasts (pluripotent stem cells). Unlike C. elegans (deterministic lineage, 88% centriole elimination), planarians RETAIN centrioles in stem cells and differentiated cells. If centriole pedigree carries fate information, regenerating planarians should show pedigree→fate correlation during blastema formation.

**Why planaria adds value:**
- **Regeneration context:** Does centriole pedigree reset during regeneration? Or does it carry "memory" of original tissue?
- **Stem cell biology:** Neoblasts are the ONLY dividing cells in adult planarians — perfect for tracking centriole inheritance through multiple divisions
- **Evolutionary distance:** Lophotrochozoa (planaria) vs Ecdysozoa (C. elegans) vs Deuterostomia (human RPE1) — if principle holds across all 3, it's truly universal

**Approach (NOT RITE — simpler):**
1. γ-tubulin or Centrin immunostaining in fixed planarians during regeneration
2. Track centriole number/distribution across blastema vs remnant tissue
3. Compare with C. elegans and RPE1 data

**N:** 30 planarians × 3 timepoints | **Duration:** 8 weeks | **Budget:** $30,000

| Item | Cost |
|------|:---:|
| Planaria facility + maintenance | $5,000 |
| Antibodies (Centrin, γ-tubulin, SAS-4) | $8,000 |
| Confocal microscopy time | $10,000 |
| Personnel | $5,000 |
| Contingency (10%) | $10,000 |
| Conference travel + OA fees | $5,000 |

> **Verdict on RITE:** Defer to OS3 or separate project. For OS2, use established markers + comparative framework without genetic engineering.

---

## 7. Zombie Centriole Analysis (Core, not optional)

### 7.1. Three-State Classification

Every centriole at 100-cell endpoint falls into one of three states:

| State | SAS-4::GFP | SPD-2::mCherry | Heidenhain Iron | Biological meaning |
|-------|:---:|:---:|:---:|------|
| **ALIVE** | + | + | + | Functional MTOC — organizes microtubules, supports cilium |
| **ZOMBIE** | + | − | + | Structurally intact, functionally dead — PCM lost, no MTOC activity |
| **AGGREGATE** | + | − | − | NOT a centriole — SAS-4 protein aggregate, misclassification risk |
| **ELIMINATED** | − | − | − | Fully degraded |

### 7.2. Key Questions OS2 Must Answer

1. **Does Pedigree Score predict zombie→eliminated transition time?** (Survival analysis: time from SPD-2 loss to SAS-4 loss)

2. **Are zombies a normal intermediate state, or a dead-end?**

3. **Do cells with zombie centrioles have different fates than cells with alive centrioles?**

4. **What fraction of "retained" centrioles (SAS-4+ only criterion) are actually zombies?** (Without SPD-2, the false-positive rate for "retention" could be 30-50%)

### 7.3. Statistical Model

```
State(t) = f(PedigreeScore, age, position, lineage)
```

Multinomial logistic regression with 4 outcome categories. Zombie→Eliminated transition modeled via competing risks (Fine-Gray with alive→zombie as the first event, zombie→eliminated as the second).

### 7.4. Integration with Enrichment Experiments

| Experiment | Zombie relevance |
|------------|------------------|
| **E5 (Iron Haematoxylin)** | Distinguishes zombie (iron+) from aggregate (iron−). **Essential validation.** |
| **E2 (Laser Ablation)** | Forced pedigree → measure zombie formation rate |
| **E1 (Wnt Perturbation)** | Changed pedigree → does zombie frequency change? |
| **E4 (Comparative)** | Are zombies C. elegans-specific? Check Drosophila NB and RPE1. |

### 7.5. Budget Implication

Zombie analysis is CORE — no additional budget beyond base $52K. E5 ($15K) provides the iron haematoxylin validation. All other zombie metrics use existing SAS-4 + SPD-2 data from OS1.

### Recommended Funding (per review committee)

| Component | Status | Amount |
|-----------|:---:|:---:|
| Base OS2 | Approved | $105,000 |
| E1 Wnt Perturbation | **Mandatory** | $25,000 |
| E5 Iron Haematoxylin | **Mandatory** | $15,000 |
| E3 Ninein-GFP | Approved (reduced N=200) | $15,000 |
| E2 Laser Ablation | Deferred to OS3 | — |
| E4 Comparative Drosophila | Deferred to separate project | — |
| E6 Planaria | Deferred | — |
| E7 Proteasome | Deferred | — |
| **Total Recommended** | | **$160,000** |
