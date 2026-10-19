# OS2 (V7) — Engineering Notes: Axio Observer benchmark → OS2 hardware

**Date:** 2026-10-19
**Master analysis:** `ARGUS-OS1/docs/AXIO_OBSERVER_ENGINEERING_ANALYSIS_2026-10-19.md`
**All PMIDs verified 2026-10-19.**

OS2 (V7) is the commercial-grade ARGUS stage (60×/1.2 WI + sCMOS + microfluidic + Jetson AGX, N=100 embryos). This is the stage where the Zeiss Axio Observer 7 lessons apply most directly: here **hardware focus-hold, environment, and sensitive detection** are required for multi-hour/multi-day runs.

## 1. What we take from Axio Observer 7 for OS2

| # | OS2 solution | Source | Justification |
|:-:|--------------|--------|---------------|
| 1 | **Hardware autofocus / focus-hold** | Definite Focus 3 / Nikon PFS / Olympus TruFocus ZDC / Leica AFC | The main failure mode of multi-day acquisition is thermal/mechanical Z-drift. For N=100 embryos at 2-min intervals, automatic focus without intervention is mandatory. Open implementation: fiducial autofocus (PMID 42274973), LED autofocus (PMID 42525498). |
| 2 | **Incubation module** (CO₂/temperature/humidity) | Axio Observer live (Glass Lid CO₂/O₂ heated, Temperature Controller, Heated Plate K) | C. elegans embryos develop for 3 h at 25 °C; cell lines (hPSC-CM, RPE1) require 37 °C/5% CO₂. Without environment — irreproducibility and physiological artefacts. Budget estimate: stage-top module ~$3–6K or an incubator chamber. |
| 3 | **Multi-channel LED engine** (≥5 channels) | Colibri 7 (7 channels) / Lumencor Aura | Low phototoxicity + fast switching between the 7 markers (SAS-4::GFP, SAS-1::mCherry, Centrin1::BFP, Dendra2, PAR-2::GFP, PAR-3::mCherry, CED-3::mCherry, Histone::CFP). |
| 4 | **Piezo Z + sCMOS** | Scanning Stage PIEZO + pco.edge 4.2 | Centriole Z-stacks (depth 1–2 µm, step 100–300 nm) require nm-precise Z and a high-sensitivity sCMOS (QE>90%, 16-bit). |
| 5 | **Auto-immersion** | Autoimmersion module | 60×/1.2 WI on long runs — immersion stability without hands (until V9). |
| 6 | **Optical sectioning (SIM/HiLo class)** | Apotome 3 | For 3D centriole contrast in scattering samples; cheaper than confocal. |
| 7 | **Micro-Manager + Mastodon** | ZEN / Mastodon (PMID 42841415) | Unified lineage pipeline: acquisition → segmentation → tracking → pedigree. |

## 2. Benchmark weak points that OS2 avoids

| Axio Observer weak point | How OS2 avoids it |
|--------------------------|-------------------|
| Price $100–200K+ | OS2 ~$307K full (HW ~$70K) — but with local edge-AI, no service contracts |
| Closed ZEN/autofocus | Open drivers, Micro-Manager, repairability |
| Phototoxicity (even brightfield — PMID 42393487) | Body Law: phototoxicity ceiling; LED minimisation; sensitive cameras |
| No autonomous sample change | V9-Standard (2 hands) |

## 3. Budget notes (impact on ~$307K full / ~$70K HW)

- Incubation module: **+$3–6K** (was not in the original estimate — add).
- Hardware autofocus (open implementation): **+$0.2–1K** (fiducial markers + LED; or via piezo hold).
- Multi-channel LED engine: **+$2–5K** (partly covered by the 405/488/561/640 lasers — to check: for live-cell, LED with low phototoxicity is preferred, not only laser).
- Piezo Z: **+$3–8K**.

> Bottom line: adding incubation + autofocus + LED raises the reliability of the N=100 experiment, which otherwise risks "losing focus/physiology" on long runs. Economically justified: the cost of a failed run (100 embryos, months) ≫ module cost.

## 4. Open questions
- [ ] Reconcile the current OS2 hardware list (PARAMETERS.md) with the §1 table.
- [ ] Choose between fiducial autofocus and LED autofocus by accuracy at 60× WI (pilot on OS1 P0).
- [ ] Incubation: stage-top vs placement in an incubator (IncuCyte variant, PMID 41795377 — in-incubator microscope).
- [ ] Check whether Micro-Manager supports OS2 immersion/filter changes — verify drivers.

---

*Added 2026-10-19. Master analysis in ARGUS-OS1/docs/. All PMIDs verified (Europe PMC/NCBI).*
