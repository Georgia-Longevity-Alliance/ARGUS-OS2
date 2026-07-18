# CONCEPT — ARGUS-OS2

**Version:** 1.0
**Date:** 2026-07-19
**Based on:** ARGUS-LP_OS v1.0 (shared hardware platform)

---

## 0. What ARGUS-OS2 Is

ARGUS-OS2 is the **causality experiment** running on the ARGUS-LP_OS v1.0 observation platform. Where v1.0 asks "is there a correlation?" — OS2 asks "**is it causal?**" using genetic perturbation (Odf2 knockout) rather than physical intervention (laser ablation).

The logic is clean: if Odf2 KO abolishes centrosome maturation asymmetry AND abolishes daughter cell fate divergence, then the maturation state (Cenexin/Odf2 axis) is causal. HDAC6 inhibitor rescue serves as the critical control — it restores cilia independently of appendages, distinguishing "cilium required" from "Cenexin required."

---

## 1. Central Hypothesis

> **The Cenexin/Odf2 maturation axis is causal for centrosome-mediated daughter cell fate divergence. Odf2 knockout abolishes both maturation asymmetry and fate divergence. HDAC6 inhibitor restores cilia but NOT fate divergence — proving that the appendage/maturation state, not ciliogenesis per se, is the causal factor.**

---

## 2. Experimental Design

### 2.1. Groups

| Group | Genotype | Treatment | Predicted Cilium Asymmetry | Predicted Fate Divergence |
|:-----:|----------|-----------|:--------------------------:|:-------------------------:|
| **WT** | RPE1-hTERT wt | DMSO (vehicle) | 94% | Present |
| **KO** | Odf2⁻/⁻ | DMSO | 0% (no cilia) | Abolished |
| **KO+HDAC6i** | Odf2⁻/⁻ | Tubacin 5 µM | Cilia restored | **KEY READOUT** |
| **HET** | Odf2⁺/⁻ | DMSO | Intermediate | Intermediate |

### 2.2. Key Readout: KO+HDAC6i

| Outcome | Interpretation |
|---------|---------------|
| Cilia restored, asymmetry **PRESENT** | Cilium is the conveyor, NOT Cenexin. Maturation state acts THROUGH cilium. |
| Cilia restored, asymmetry **ABSENT** | Cenexin/Odf2 maturation axis IS causal independent of cilium. |

### 2.3. Molecular Mechanism

```
Cenexin/Odf2 → distal appendages → Plk1 recruitment → γ-tubulin accumulation
    → pericentrin/Cdk5Rap2 → spindle asymmetry (Thomas & Meraldi 2024)
    → daughter cell size difference → differential cilium prob.
```

Odf2 KO removes distal AND subdistal appendages (Ishikawa 2005, PMID 15852003). Different Odf2 domains control different appendage types (Tateishi 2013, PMID 24189274). HDAC6i (tubacin) restores cilia independently of appendages (Wang 2025, PMID 40167251).

---

## 3. Cell Strategy

| Stage | System | Duration | Go/No-Go |
|:-----:|--------|:--------:|----------|
| **KO generation** | RPE1-hTERT, CRISPR Odf2, clonal selection | 6 weeks | >90% KO confirmed by IF + Western |
| **Pilot dose-response** | HDAC6i (tubacin) 1-50 µM, 72h | 2 weeks | Cilia restoration ≥80% at ≤10 µM |
| **Main** | 4 groups × 50 pairs each = 200 pairs | 4 weeks | — |
| **Endpoint** | Cenexin + acetylated tubulin + differentiation markers | — | — |

---

## 4. Statistical Design

### Primary comparison: KO+HDAC6i vs WT

```
H₀: Fate divergence in KO+HDAC6i = WT (Cenexin is causal through cilium)
H₁: Fate divergence in KO+HDAC6i < WT (Cenexin has cilium-independent causal role)
```

**Test:** McNemar for paired binary outcome within each group, followed by between-group comparison of discordant pair proportions (Cochran-Mantel-Haenszel).

**Power:** With 50 pairs per group and effect size of 30 pp difference in discordance proportion, power >80% at α=0.05.

---

## 5. Budget (on top of ARGUS-LP_OS v1.0)

| Line item | $ |
|-----------|--:|
| Odf2 CRISPR knockout (sgRNA design + nucleofection + clonal selection + validation) | 1,500 |
| HDAC6i (tubacin, 10 mg) + DMSO vehicle | 400 |
| Additional Centrin1-GFP RPE1 vials (KO line) | 500 |
| Reagents (puromycin, blasticidin, Western antibodies: Odf2, Cenexin, GAPDH) | 600 |
| **Subtotal** | **3,000** |

> **Total with v1.0 platform: ~$27,053.** Hardware already funded by v1.0 grant.

---

## 6. Results Strategy

| Outcome | Action |
|---------|--------|
| Asymmetry ABSENT in KO+HDAC6i | First causal demonstration of Cenexin/Odf2 axis. High-impact paper. |
| Asymmetry PRESENT in KO+HDAC6i | Cilium is the conveyor. Valuable mechanistic insight. Publish null on Cenexin causality. |
| KO fails (no viable line) | Domain-specific Odf2 mutants (Tateishi 2013) or Cenexin siRNA. |

---

## 7. Key References

1. Ishikawa H et al. *Nat Cell Biol* 7:517–524 (2005). **PMID: 15852003.** — Odf2 KO abolishes appendages.
2. Tateishi K et al. *J Cell Biol* 201(3):417–425 (2013). **PMID: 24189274.** — Odf2 domain specificity.
3. Wang Z et al. *Adv Sci* (2025). **PMID: 40167251.** — HDAC6i restores cilia.
4. Thomas A, Meraldi P. *J Cell Biol* 223(8) (2024). **PMID: 39012627.** — Spindle asymmetry mechanism.

See ARGUS-LP_OS CONCEPT.md for complete reference list (23 PMIDs).

---

*Version 1.0 — 2026-07-19. Initial concept. Causality through Odf2 KO, not laser.*
