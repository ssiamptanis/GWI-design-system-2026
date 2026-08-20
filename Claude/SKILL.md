---
name: gwi-design-system-2026
description: >
  GWI's 2026 rebrand design system — the single source of truth for brand colors, typography,
  logo usage, buttons, icons, and flags. Use this skill whenever answering any question about
  GWI's brand, colors, fonts, or component usage, and whenever creating, reviewing, or editing
  anything GWI-branded — HTML mockups, slides, presentations, dashboards, UI components,
  marketing assets, one-pagers, or any visual output meant to look like GWI. Trigger this even
  if the user doesn't say "brand guidelines" or "design system" — e.g. "make this on-brand",
  "use our colors", "what typeface do we use", "add a GWI button", "what's our primary CTA
  color", or any request to produce something GWI will show to customers or stakeholders.
  Always consult this before generating GWI-branded visual output, not just when explicitly asked.
---

# GWI Design System 2026

This skill lives in `Claude/` at the root of the `GWI-design-system-2026` repo, one level below
the actual brand files — everything referenced below is read directly from its sibling folders,
not copied in. There is no separate copy to keep in sync: if `tokens/color.json` changes, this
skill's knowledge changes with it. All paths below are relative to this file's location
(i.e. `../tokens/color.json` means the `tokens/` folder at the repo root).

## How to use this skill

Don't try to memorize every value below — this file is a map, not the full content. Read the
specific file you need for the task at hand:

| Need to know... | Read |
|---|---|
| Any color value | `../tokens/color.json` |
| Which colors are approved as backgrounds | `../tokens/color-usage.md` |
| Type scale (sizes, weights, line-heights) | `../tokens/typography.json` |
| Which typeface to use, font files, `@font-face` | `../Typography/README.md` |
| Which logo variant to use | `../Components/Logo/README.md` |
| Button colors/states/sizes | `../Components/Buttons/README.md` |
| Icon colors | `../Components/Icons/README.md` |
| Flag file naming | `../Components/Flags/` (self-explanatory: `Dark Mode - <Country>` / `Light Mode - <Country>`) |
| Front/back cover, content page, and divider slide rules | `../Components/Presentations/README.md` |
| Reference HTML template for generating a new deck | `../Templates/Presentation Template.html` |
| Overview of what exists / where | `../FILE-STRUCTURE.md` |

## Core rules (the ones that matter most)

These come up constantly enough to state up front — but always verify against the actual token
file before using a value, since this repo is a living document and gets updated over time.

1. **Colors always come from `../tokens/color.json`, never a guessed or memorized hex.** If a
   value you need is an empty placeholder in that file, say so rather than inventing one.
2. **Typefaces: Ovo for headlines/display only, Instrument Sans for everything else.** Ovo has
   exactly one weight (Regular) — never fake-bold or fake-italicize it. See
   `../Typography/README.md` for the full size-by-size breakdown of which typeface applies where.
3. **Backgrounds are allow-listed, not guessed.** `../tokens/color-usage.md` states: not listed
   there = not approved as a background color.
4. **Buttons: Lime is the primary CTA** (matches `color.accessory.cta_primary`), Hot pink is
   secondary/brand-accent, White is tertiary/for colored or dark surfaces. Full state rules
   (Default/Hover/Active/Inactive) in `../Components/Buttons/README.md`.
5. **Icons: Pink (`color.pink.80`) is the default color** unless there's a specific reason to
   use another approved token — see `../Components/Icons/README.md`.
6. **Logo: Lockup is the default.** Wordmark and The Link are restricted to specific approved
   use cases — use Lockup unless you have a stated reason not to.
7. **Cover slides are minimal, by rule.** Front cover = logo bottom-left, large title positioned
   high on the page, subtitle, nothing else (no eyebrow, no footer, no page number). Back cover =
   `color.neutral.100` background, logo centered horizontally and vertically, nothing else except
   small muted year text. Full detail in `../Components/Presentations/README.md`.
8. **When asked to build a GWI presentation/deck, use `../Templates/Presentation Template.html`
   as the reference template** — it's the living example of correct margins, type sizes, leading,
   card padding, cover/divider/content-page rules, and copy style (no dashes) all applied
   together. Copy its structure and CSS approach rather than reinventing layout values from the
   written rules alone.
9. **Never use dashes (en dash `–` or em dash `—`) in generated slide copy.** Rephrase with a
   period, comma, or "and"/"then" instead.

## When generating new GWI-branded output

If asked to build an HTML mockup, slide, dashboard, or any visual asset that should look like
GWI:

- Pull the actual hex values from `../tokens/color.json` and font stacks from
  `../tokens/typography.json` — don't approximate from memory, since exact values matter for
  brand consistency and this repo is the definitive source.
- Follow the component rules above (button variant choice, icon color, logo variant) rather than
  picking whatever looks good in the moment — these rules exist because someone at GWI made a
  deliberate call about hierarchy and usage, not because they're arbitrary.
- If a rule or value doesn't exist yet (e.g. an empty color placeholder, no defined rule for a
  situation you're facing), say so explicitly and ask, rather than inventing something that looks
  plausible. This repo is still being filled in — treat gaps as gaps, not as license to guess.

## Known open questions (don't treat these as settled)

- `color.accessory.cta_secondary` is currently blue (`#0088FF`) but no exported button uses blue
  — flag this if it comes up rather than assuming it's correct.
- Wordmark and The Link logo variants don't yet have their approved use cases filled in.
- Some `color.json` steps are still empty placeholders (e.g. most of `lime`/`orange` don't have
  a full 10–100 ramp yet, `accessory.warning`/`error`/`info` have no background-approved status).

When any of the above would affect an answer, mention the gap rather than filling it in silently.
