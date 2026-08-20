# Typography

Source: GWI Brand Guidelines, "Typography" section. Two typefaces, both Google Fonts, both OFL (Open Font License) — free to redistribute, files already live in this folder.

## Type family

**Ovo** — humanist Venetian serif, designed by Nicole Fally (Sorkin Type Co.), inspired by 1930s hand-lettered caps. Medium-contrast, soft serifs, whimsical numerals. Used for **headlines and display only** — it is not a body or UI typeface.

**Rule: Ovo has exactly one weight — Regular.** There is no Medium, SemiBold, Bold, or Italic cut of this typeface. Never fake-bold or fake-italicize Ovo (CSS `font-weight: bold` or `font-style: italic` applied to a font with no such cut produces a synthetic/faux style that looks distorted and off-brand). If a design calls for a heavier or italic headline treatment, that's a sign the text should move to Instrument Sans instead, not that Ovo should be artificially altered.

**Instrument Sans** — modern variable sans-serif (weight + width axes in one file, plus a separate italic). Balances precision with subtle playfulness; 12 stylistic sets available for alternate glyphs (advanced/optional — not a default rule, a designer would need to deliberately enable a stylistic set). Used for everything else: supporting headings, all body copy, all buttons/CTAs.

Files:
- `Typography/Ovo/Ovo-Regular.ttf` + `.woff2`
- `Typography/Instrument Sans/InstrumentSans-VariableFont_wdth,wght.ttf` + `.woff2`
- `Typography/Instrument Sans/InstrumentSans-Italic-VariableFont_wdth,wght.ttf` + `.woff2`

(woff2 files generated locally from the ttf's for web use — same font, just compressed; no separate download needed.)

## The rule: which typeface, when

**Ovo is for headers/display only, and only at 48px and above.** Anything smaller — Heading-03 down, and *all* Body and Action/CTA text regardless of size — is set in Instrument Sans. This holds even where a Body size is larger than 48px (e.g. Body XL at 54px): size alone doesn't put something in Ovo — only Display/Heading-01/Heading-02 do.

| Scale group | Typeface |
|---|---|
| Display xl (64px), Display lg (48px) | **Ovo**, Regular |
| Display md (35px), Display sm (24px) | Instrument Sans |
| Heading 01 (64px), Heading 02 (48px) | **Ovo**, Regular |
| Heading 03–05 (36px and below) | Instrument Sans |
| Body (all sizes) | Instrument Sans |
| Action/CTA (all sizes) | Instrument Sans |

## Type scale

See `tokens/typography.json` for the full machine-readable scale (desktop + mobile size, line-height, weight per step). Groups: Display (xl/lg/md/sm), Heading (01–05), Body (xl/lg/md/sm/xs), Action (xl/lg/md/sm/xs). Sizes below are confirmed from the Figma variables (desktop/mobile pairs) — line-height and weight are from the guidelines deck.

| Step | Desktop | Mobile | Typeface / weight |
|---|---|---|---|
| Display xl | 200px | 96px | Ovo, Regular |
| Display lg | 140px | 80px | Ovo, Regular |
| Display md | 96px | 64px | Instrument Sans, Medium |
| Display sm | 64px | 48px | Instrument Sans, Medium |
| Heading 01 | 64px | 48px | Ovo, Regular |
| Heading 02 | 48px | 40px | Ovo, Regular |
| Heading 03 | 36px | 32px | Instrument Sans, Medium |
| Heading 04 | 24px | 18px | Instrument Sans, Medium |
| Heading 05 | 20px | 14px | Instrument Sans, Medium |
| Body xl | 54px | 32px | Instrument Sans, Medium |
| Body lg | 32px | 24px | Instrument Sans, Medium |
| Body md | 20px | 18px | Instrument Sans, Medium |
| Body sm | 16px | 14px | Instrument Sans, Medium |
| Body xs | 12px | 10px | Instrument Sans, Medium |
| Action xl | 54px | 32px | Instrument Sans, SemiBold |
| Action lg | 32px | 24px | Instrument Sans, SemiBold |
| Action md | 20px | 18px | Instrument Sans, SemiBold |
| Action sm | 16px | 14px | Instrument Sans, SemiBold |
| Action xs | 12px | 10px | Instrument Sans, SemiBold |

**Exception — stat/big numbers:** large callout figures used as a display element (e.g. "35B+",
"2M+" stat blocks in decks) are always set in **Ovo**, regardless of the general Body/Action rule
above — they're functioning as headline-scale display type, not body copy. See
`Components/Presentations/README.md`.

**Flag to note:** Display md/sm are labeled "Medium" weight in the deck, which is why they're set in Instrument Sans rather than Ovo even though their pixel size (96px/64px) clears the "48px minimum" mentioned for Ovo — Ovo only ships in Regular, so it physically can't carry a Medium weight. The 48px rule determines which *category* (Display xl/lg, Heading 01/02) gets Ovo; within that, weight is what actually confirms it. Worth a quick sanity check with whoever owns the Figma file that Display md/sm are deliberately Instrument Sans and not a labeling slip.

## Usage principles (from the guidelines, verbatim intent)

Type should lead with meaning, then build rhythm. Use Ovo to give headlines an editorial, human voice; pair it with Instrument Sans for clear, efficient supporting information. Build hierarchy through scale, weight, and space *before* reaching for color or effects. Keep line lengths comfortable, avoid crowded compositions, and use bold emphasis sparingly. The result should feel assured and distinctive — never ornamental.

## Web `@font-face` (self-hosted, not Google Fonts CDN — see earlier note on GDPR/self-hosting)

```css
@font-face {
  font-family: "Ovo";
  src: url("/fonts/Ovo-Regular.woff2") format("woff2");
  font-weight: 400;
  font-style: normal;
  font-display: swap;
}

@font-face {
  font-family: "Instrument Sans";
  src: url("/fonts/InstrumentSans-VariableFont_wdth,wght.woff2") format("woff2-variations");
  font-weight: 400 700;
  font-style: normal;
  font-display: swap;
}

@font-face {
  font-family: "Instrument Sans";
  src: url("/fonts/InstrumentSans-Italic-VariableFont_wdth,wght.woff2") format("woff2-variations");
  font-weight: 400 700;
  font-style: italic;
  font-display: swap;
}
```
