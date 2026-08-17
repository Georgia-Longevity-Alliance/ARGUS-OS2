# ARGUS-OS2

ARGUS-OS2 tests the centriole pedigree convergence hypothesis using data from ARGUS-OS1.

**Question:** Does centriole pedigree (sequence of division orientations) predict cell fate convergence?

**Two phases:**
1. C. elegans — Principle visualization (complete lineage)
2. RPE1 — Centriole as carrier test

**Primary experiment:** Different pedigrees → same fate = convergence proven.

**Budget:** $13,000 (20 weeks)

## V9 Upgrade — Robot Hands + Shared Local LLM Brain (V9-Standard)

OS2 (V7) carries the V9-Standard autonomy configuration. Two cable-driven robot arms operate through the glove ports **instead of human hands**, providing 24/7 servicing across the multi-week RPE1 runs (5 generations): sample exchange, medium replenishment, objective cleaning for the 60x/1.2 WI, and microfluidic cassette handling.

The brain is an **external LLM on local hardware** — the Jetson AGX accelerates vision; the planning LLM runs on the same host that controls the arms and micro-robots (no cloud). Consumables and spare parts are sterilized outside and enter through the V7-TRANSFER box (UV-C + HEPA purge); the inner door is opened by the operator in gloves.

| V9 element | OS2 instantiation |
|-----------|-------------------|
| Hands | 2x cable-driven arms, 5-6 DOF, NEMA 17 + TMC2209, exchangeable end-effectors |
| Brain | Jetson AGX 64GB (vision) + shared local host (LLM planner); Tool Bridge + Safety Layer + Flight Recorder (AIS) |
| Transfer box | V7-TRANSFER: 2 doors, interlock, UV-C 254 nm, HEPA purge |
| Sterilization | Autoclave + UV-C + EtOH (shared lab set) |
| Budget | ~$11-13K (arms + transfer box) |

- Design: [ARGUS-OS1/docs/V9_PROTOTYPE.md](https://github.com/Georgia-Longevity-Alliance/ARGUS-OS1/blob/main/docs/V9_PROTOTYPE.md)
- Sterilization & transfer-box SOPs: [ARGUS-OS1/docs/STERILIZATION_TRANSFER.md](https://github.com/Georgia-Longevity-Alliance/ARGUS-OS1/blob/main/docs/STERILIZATION_TRANSFER.md)
