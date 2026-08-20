# Icons

8 icons — Flow, Group, Quadrant, Spread, Stack, Storage, User, World — each exported in 8 colors, as SVG and PNG.

## File naming

```
Name of icon - Colour.svg
Name of icon - Colour.png
```

e.g. `User - Pink.svg`, `World - Neutral 100.png`.

## Colors — linked to `tokens/color.json`

Every icon color is a direct read of an existing color token — nothing here is a one-off hex. Verified against the SVG fills:

| File color | Token | Hex |
|---|---|---|
| Lime Dark | `color.lime.50` | `#729508` |
| Lime Light | `color.lime.40` | `#B9DB51` |
| Orange Dark | `color.orange.50` | `#D5661B` |
| Orange Light | `color.orange.20` | `#FFE3D1` |
| Pink | `color.pink.80` | `#FF0077` |
| Pink Light | `color.pink.30` | `#FFD2DF` |
| Neutral 10 | `color.neutral.10` | `#FBFAFA` |
| Neutral 100 | `color.neutral.100` | `#1E1B1A` |

**Rule: an icon's color must always resolve to one of these tokens.** If a new color variant of an icon is ever needed, it should map to an existing (or newly added) step in `color.json` — never a hardcoded hex that doesn't exist in the token file. This keeps icons and the rest of the system (buttons, backgrounds, etc.) moving together if a color value ever changes.

## Choosing a color for context

- **Pink (`color.pink.80`) — default.** Use this unless a specific reason (below) calls for something else.
- **Neutral 100** — alternative for light backgrounds where Pink doesn't fit (e.g. next to already-heavy brand color).
- **Neutral 10** — alternative for dark backgrounds, same reasoning.
- **Lime Dark / Orange Dark** — use to tie an icon to a specific brand color elsewhere on the page (e.g. matching a Lime CTA button), not as a general substitute for the Pink default.
- **Pink Light / Lime Light / Orange Light** — muted versions of the above, for lower-emphasis or decorative use.

*(Flag: this section is a reasonable default based on how the other components use these same token steps — worth confirming with whoever owns the Figma file rather than treating it as settled.)*
