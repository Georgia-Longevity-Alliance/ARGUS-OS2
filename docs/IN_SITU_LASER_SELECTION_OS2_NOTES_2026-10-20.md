# OS2 (V7) — Engineering Notes: Automated in-situ laser selection → OS2 rationale

**Date:** 2026-10-20
**Master analysis:** `../docs/NIKON_AUTOMATED_LASER_SORTING_ANALYSIS_2026-10-20.md` (index-level)
**Primary source:** Kaneshiro et al. 2022 (Quant Plant Biol 3:e30, DOI 10.1017/qpb.2022.24, open access) + Nikon app-note 2311E (vendor).
**All PMIDs/DOIs verified 2026-10-20.**

## Why this matters for OS2

OS2 (V7) is the lineage-prediction stage (60×/1.2 WI + sCMOS + **microfluidic** + Jetson AGX, N=100 embryos). Its job: **pedigree → fate** prediction. The Kaneshiro 2022 method is directly relevant to OS2's sample-delivery and selection philosophy:

1. **Positional preservation vs microfluidics.** The paper's core claim — *"the positional information before irradiation is completely maintained after laser irradiation, and our method facilitates continuous analysis, such as live imaging, for tracing individual cells"* — is an independent, peer-reviewed confirmation that **in-situ selection preserves the lineage/position information** that microfluidic sorting destroys. OS2 uses microfluidics for **loading/delivery** (fine), but this paper strengthens the argument that **selection/elimination should be done in-situ, not by sorting out**, if lineage continuity matters. → citable justification in OS2's DESIGN/CONCEPT and in the N=100 main-experiment protocol.

2. **Substrate of choice for the ablation loop.** The automated ablation loop designed for OS3 (`../OS3/docs/AUTOMATED_ABLATION_LOOP.md`) can run on the OS2 platform too: OS2's sCMOS + Jetson AGX (stronger edge-AI than OS3's Mac) + 60×/1.2 WI make it the natural host for Cellpose-driven closed-loop ablation at higher precision than the 20×/0.75 Nikon system.

3. **QC / lineage-integrity argument.** Continuous per-cell ablation-QC (Table-2-style stats, paper) plus ARGUS's Flight Recorder gives OS2 a lineage-integrity audit trail — a grant-writing advantage over commercial closed platforms.

## What to take for OS2
- Add the positional-preservation citation (Kaneshiro 2022) to OS2 CONCEPT/DESIGN rationale (in-situ selection vs sorting).
- Note that the automated ablation loop (OS3) is OS2-compatible (sCMOS + AGX) → OS2 can serve as the precision host for causality experiments if OS3 is delayed.
- Do NOT add hardware changes to OS2 for this (no laser needed for OS2's observation stage) — this is a rationale/design note, not a BOM change.

## Verified sources
- Kaneshiro et al. 2022 — DOI 10.1017/qpb.2022.24 (primary, CC BY 4.0)
- Gokce et al. 2014 — PMID 25470130 (automated fs-laser ablation in C. elegans)
- Kamei et al. 2009 — PMID 19079252 (IR-LEGO foundation)
