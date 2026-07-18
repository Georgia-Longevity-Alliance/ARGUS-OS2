# MAP — ARGUS-OS2

```
ARGUS-OS2/
├── README.md               # Homepage
├── CONCEPT.md              # Concept — Odf2 KO causality
├── PARAMETERS.md           # Experiment parameters, budget
├── TODO.md                 # Tasks
├── STATE.md                # Current status
├── MEMORY.md               # Decision history
├── _pi.md                  # Rules for pi
│
├── docs/                   # Documentation
│   └── (protocols, dose-response data)
│
├── letters/                # Reagent requests, collaboration
│
├── grants/                 # Causality grant application
│
└── refs/                   # Odf2, HDAC6, CRISPR literature
```

## Relationship

```
ARGUS-LP_OS (v1.0)          ARGUS-OS2 (v2.0)            ARGUS-OS3 (v3.0)
    │                            │                           │
    ├─ Hardware: OF v6.1.5       ├─ Hardware: SAME           ├─ Hardware: v1.0 + laser
    ├─ Glove-box + HEPA          ├─ Glove-box: SAME          ├─ Glove-box + UV-C
    ├─ Night vision: 1× NV       ├─ Night vision: SAME       ├─ Night vision: 2× NV
    ├─ No laser                  ├─ No laser                 ├─ Femtosecond laser
    ├─ No micromanipulator       ├─ No micromanipulator      ├─ Micromanipulator
    ├─ RPE1 observation          ├─ RPE1 Odf2 KO             ├─ NPC ablation
    └─ $24,053                   └─ +$3,000                  └─ $40,600
```

## Shared vs Owned

| Resource | ARGUS-LP_OS | ARGUS-OS2 | ARGUS-OS3 |
|----------|:-----------:|:---------:|:---------:|
| OpenFlexure | ✅ Owns | 🔗 Shares | 🔗 Shares |
| Glove-box | ✅ Owns | 🔗 Shares | 🔗 Shares + UV-C |
| Camera HQ | ✅ Owns | 🔗 Shares | ✅ Own sCMOS |
| Jetson Orin | ✅ Owns | 🔗 Shares | ✅ Own Mac M4 |
| Night vision | ✅ Owns (1×) | 🔗 Shares | ✅ Own (2×) |
| Micromanipulator | ❌ | ❌ | ✅ Owns |
| Laser | ❌ | ❌ | ✅ Owns |

## Links
- **ARGUS-LP_OS:** `~/Desktop/Marketing/ARGUS-LP_OS/`
- **ARGUS-OS3:** `~/Desktop/Marketing/ARGUS-OS3/`
- **OpenFlexure upstream:** `https://github.com/openflexure/openflexure-microscope`
