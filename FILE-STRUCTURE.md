# File structure

Current state of the repo. Repetitive asset sets (buttons, flags, icons, logo variants) are collapsed with a naming-pattern note rather than listed file-by-file — see each folder's own `README.md` for the full breakdown.

```
GWI-design-system-2026/
│
├── README.md                          — repo entry point / index
│
├── tokens/
│   ├── README.md                      — how the token files are structured
│   ├── color.json                     — color palette (DTCG format)
│   ├── color-usage.md                 — background color guardrails
│   └── typography.json                — type scale (DTCG format)
│
├── Typography/
│   ├── README.md                      — typeface rules, @font-face snippets
│   ├── Ovo/
│   │   ├── Ovo-Regular.ttf
│   │   └── Ovo-Regular.woff2
│   └── Instrument Sans/
│       ├── InstrumentSans-VariableFont_wdth,wght.ttf
│       ├── InstrumentSans-VariableFont_wdth,wght.woff2
│       ├── InstrumentSans-Italic-VariableFont_wdth,wght.ttf
│       └── InstrumentSans-Italic-VariableFont_wdth,wght.woff2
│
└── Components/
    │
    ├── Logo/
    │   ├── README.md                  — Lockup = default; Wordmark / The Link = restricted use
    │   ├── Lockup/
    │   │   ├── SVG/  (8 files — Color=Light Mode, Dark Mode, Mono Lime Dark, Mono Orange Dark, Mono Pink, Mono Pink Light, Mono Light Mode, Mono Dark Mode)
    │   │   └── PNG/  (same 8 variants)
    │   ├── Wordmark/
    │   │   ├── SVG/  (6 files — same color pattern minus the two "Mono Mode" variants)
    │   │   └── PNG/  (6 files)
    │   └── The link/
    │       ├── SVG/  (6 files — Lime Dark, Orange Dark, Pink, Pink Light, Neutral 10, Neutral 100)
    │       └── PNG/  (6 files)
    │
    ├── Flags/
    │   ├── SVG/  (118 files — 59 countries × Dark Mode / Light Mode)
    │   └── PNG/  (118 files — same pattern)
    │       naming: "Dark Mode - <Country>.svg" / "Light Mode - <Country>.svg"
    │
    ├── Buttons/
    │   ├── README.md                  — color/state/size rules, cta_primary mapping
    │   └── SVG/  (108 files — 3 colors [Lime, Hot pink, White] × 3 sizes [Big, Medium, Small] × 3 icon positions [left, right, off] × 4 states [Default, Hover, Active, Inactive])
    │       naming: "Colour=<color>, Size=<size>, icon=<position>, State=<state>.svg"
    │
    └── Icons/
        ├── README.md                  — color-to-token mapping, Pink = default
        ├── SVG/  (64 files — 8 icons [Flow, Group, Quadrant, Spread, Stack, Storage, User, World] × 8 colors)
        └── PNG/  (64 files — same pattern)
            naming: "<Icon> - <Colour>.svg/png"
```

## Counts

| Area | Files |
|---|---|
| Logo | 40 (SVG + PNG combined) |
| Flags | 236 (SVG + PNG combined) |
| Buttons | 108 (SVG only — PNG not yet exported) |
| Icons | 128 (SVG + PNG combined) |
| Typography | 6 font files |
| Tokens | 3 JSON/markdown files |
| READMEs | 6 (root, tokens, Typography, Logo, Buttons, Icons) |
