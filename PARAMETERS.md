# PARAMETERS — ARGUS-OS1.5

**Version:** 1.0
**Date:** 2026-07-19

## Experiment Parameters

| Parameter | Value |
|-----------|-------|
| **Platform** | ARGUS-LP_OS v1.0 (shared hardware) |
| **Cell line** | RPE1-hTERT Centrin1-GFP + H2B-GFP (ATCC CRL-4000 + stable transduction) |
| **CRISPR target** | Odf2 (exon 3-5, all isoforms) |
| **KO validation** | Western (Odf2, Cenexin) + IF (Cenexin, acetylated tubulin) |
| **HDAC6i** | Tubacin (Sigma SML0065), 5 µM working concentration (TBD by pilot) |
| **Vehicle** | DMSO ≤0.1% |
| **Sister isolation** | CYTOO 2-cell islands |
| **Imaging** | 10 min interphase / 1 min mitosis |
| **Duration** | 72h continuous |
| **N per group** | 50 pairs × 4 groups = 200 total |
| **Endpoint** | Cenexin + acetylated tubulin + γ-tubulin |

## Go/No-Go Gates

| Gate | Criterion | Fail → Action |
|------|-----------|---------------|
| KO generation | >90% Odf2 KO by Western | Domain-specific mutants (Tateishi 2013) |
| HDAC6i pilot | ≥80% cilia restoration at ≥90% viability | Try other HDAC6i (ACY-1215) or lower dose |
| Main: KO+HDAC6i | 50 pairs with valid endpoint data | Increase N if attrition >20% |

## Budget (+$3,000 on v1.0)

| Line item | $ |
|-----------|--:|
| Odf2 gRNA + Cas9 protein + HDR template | 800 |
| Nucleofection kit (Lonza, 10 reactions) | 400 |
| Puromycin + Blasticidin | 150 |
| Western antibodies (Odf2, Cenexin, GAPDH) | 600 |
| Tubacin 10 mg + DMSO | 400 |
| Additional Centrin1-GFP RPE1 (KO line) | 500 |
| Consumables (plates, tips, selection media) | 150 |
| **TOTAL** | **$3,000** |
