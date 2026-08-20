# GWI Design System 2026

Single source of truth for the GWI rebrand — colors, typography, and UI components. Built to be read by more than just humans: this repo is meant to feed a Claude Skill, a Claude design skill, Cursor, and other LLM/design tools directly, so values and rules only need to be defined once, here, rather than copy-pasted into every consuming system.

## How this repo works

- **`tokens/`** — machine-readable values (color, typography), in [DTCG](https://design-tokens.github.io/community-group/format/) format (`$type` / `$value` / `$description`). This is what a build pipeline, Figma sync (Tokens Studio), or a Skill should read for the actual hex codes, font sizes, etc.
- **`Components/`** and **`Typography/`** — the visual assets (SVG/PNG exports, font files) plus a `README.md` per folder documenting the *rules*: which variant to use, when, and why. Assets without rules are just files; the READMEs are what make this a system.
- Values live in JSON. Rules live in markdown. Neither replaces the other — a Skill needs both to answer "what color is this" and "when should I use it."

## Status: early / actively growing

This was just stood up — treat everything here as a working draft that gets filled in and corrected over time, not a finished spec. Several things are explicitly flagged as placeholders or open questions in their respective READMEs (e.g. approved use cases for the Wordmark/The Link logo variants, a possible mismatch on `cta_secondary` in `tokens/color.json`). Check each folder's README for its own "flag" notes before treating something as final.

## What's here

| Folder | Contents |
|---|---|
| `tokens/color.json` | Color palette — pink, lime, orange, neutral ramps, plus accessory/CTA colors. Some steps are still empty placeholders. |
| `tokens/color-usage.md` | Guardrails for which colors are approved as backgrounds. Rule: not listed = not approved. |
| `tokens/typography.json` | Type scale (Display, Heading, Body, Action) with desktop + mobile sizes, weight, line-height, and font family per step. |
| `Typography/` | Font files for Ovo and Instrument Sans (ttf + self-hosted woff2) plus usage rules — which typeface for what, and that Ovo is Regular-only (no faux bold/italic). |
| `Components/Logo/` | Lockup (default), Wordmark and The Link (restricted use) — light/dark/mono variants. |
| `Components/Flags/` | Country flags, light/dark mode, SVG + PNG. |
| `Components/Buttons/` | Lime/Hot pink/White button variants × 3 sizes × icon position × 4 states, with color/state rules and which button maps to `cta_primary`. |
| `Components/Icons/` | 8 icons × 8 approved colors, all tied back to `tokens/color.json` — Pink is the default. |

## Working on this repo going forward

Structure is meant to hold steady now that other systems will point at specific paths (`tokens/color.json`, `Components/Buttons/README.md`, etc.) — renaming or reshaping folders later is a breaking change for anything already connected, not just a local tidy-up. Prefer adding to what's here over restructuring it.

When adding something new, follow the existing pattern: primitive values as tokens (JSON, DTCG format, empty placeholders are fine until real values exist), usage rules as a README in the same folder, and flag open questions explicitly rather than guessing at an answer.
