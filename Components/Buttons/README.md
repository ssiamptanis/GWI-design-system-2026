# Buttons

Derived directly from the SVG exports in `Components/Buttons/SVG/`. Naming convention of the files (matches Figma variant properties):

```
Colour=<Lime|Hot pink|White>, Size=<Big|Medium|Small>, icon=<left|right|off>, State=<Default|Hover|Active|Inactive>.svg
```

108 files = 3 colors × 3 sizes × 3 icon positions × 4 states.

**Naming rule: always "Lime," never "Lime."** Files were renamed accordingly (`Colour=Lime` → `Colour=Lime`).

## Colors — what each one maps to

| File color | Fill token | Stroke | Text/icon color | Likely role |
|---|---|---|---|---|
| Lime | `color.lime.30` (`#D2EA88`) | `#1E1B1A` (2px) — matches `color.neutral.100` | `color.neutral.100` (`#1E1B1A`) | **Primary CTA** — Default fill exactly matches `color.accessory.cta_primary` and stroke matches `cta_primary_stroke` already in `tokens/color.json` |
| Hot pink | `color.pink.80` (`#FF0077`) | none | `color.neutral.20` (`#F9F7F6`) | Secondary / brand-accent button |
| White | `color.neutral.10` (`#FBFAFA`) | `#1E1B1A` (2px) | `color.neutral.100` (`#1E1B1A`) | Tertiary / outline button, for use on colored or dark backgrounds |

**Flag for you to confirm:** `color.accessory.cta_secondary` in `tokens/color.json` is currently `#0088FF` (blue), but no button variant in this export uses blue — only Lime, Hot pink, and White exist. Either `cta_secondary` needs updating to match one of these three, or a 4th button color is missing from the export. Worth resolving before this becomes the reference other systems pull from.

## States

| State | Meaning | How it's shown |
|---|---|---|
| Default | Resting, interactive | Base fill color |
| Hover | Cursor over button | Fill steps one shade darker (e.g. Lime: `lime.30` → `lime.40`; Hot pink: `pink.80` → `pink.90`) |
| Active | Pressed / mouse down | Fill steps one shade darker again (e.g. Lime: `lime.40` → `lime.50`; Hot pink: `pink.90` → `pink.100`) |
| Inactive | Disabled — not currently actionable | Fill drops to the lightest step in that color's ramp (e.g. Lime → `lime.10`, Hot pink → `pink.20`), text/icon mutes to a gray (`neutral.50`–`neutral.60`) |

No separate Focus state exists in this export yet — worth adding if keyboard accessibility needs a visible focus ring (see earlier discussion on button states).

**Flag for you to confirm:** for the White button, `Active` and `Inactive` currently share the exact same fill (`#D4D0CE` / `neutral.40`) and only differ by text color. That makes Active and Inactive visually hard to tell apart at a glance for this one color — worth double-checking this was intentional in Figma, since Lime and Hot pink both give Inactive its own distinct (lighter) fill step.

## Sizes

| Size | Dimensions (icon=off) | Corner radius |
|---|---|---|
| Big | 257 × 93 | 16px |
| Medium | 171 × 60 | 12px |
| Small | 123 × 40 | 8px |

## Icon position

`left`, `right`, or `off` (no icon) — same button, icon placed before or after the label, or omitted entirely.

## Label copy

"Call to action" in every SVG is placeholder text, not real copy — it's there to show the style, not to dictate what buttons should say. The actual button is not a static asset: label text is editable, and the button should resize (width, and icon spacing when present) to fit whatever the new copy is, rather than truncating or overflowing. Height, corner radius, and padding stay fixed per size (see Sizes table above) — only the width flexes with the label.

## Rule of thumb

- Use **Lime** for the primary action on a screen/slide — it's the one wired to `cta_primary` in the token file.
- Use **Hot pink** for a secondary brand-forward action.
- Use **White** for buttons that need to sit on a colored or dark surface without competing with it.
- Never use Inactive styling to mean anything other than "not currently actionable" — it should not be used as a fourth color choice.
