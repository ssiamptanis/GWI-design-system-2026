# Tokens

Format: [DTCG](https://design-tokens.github.io/community-group/format/) (`$type` / `$value` / `$description`) — this is what Style Dictionary v4 and Tokens Studio for Figma both read natively, so this same file can later sync straight into Figma variables or compile to CSS.

## Structure

Each color group has `light` / `base` / `dark` steps (brand colors) or a `10–100` numeric scale (`neutral`). Fill in any empty `"$value": ""` with a hex code — leave `$description` as-is or improve it.

- `color.pink`, `color.lime`, `color.orange` — brand colors, one step already pulled from the logo files
- `color.neutral` — grayscale ramp, only 10 and 100 are known so far (from logo light/dark mode)
- `color.semantic` — success/warning/error/info, all empty, add as needed

## Adding a new group

Copy the same pattern — a nested object per color, each step as `{ "$type": "color", "$value": "#hex", "$description": "..." }`. Keep naming lowercase, no spaces.

## Next files to add here as the system grows

- `typography.json` — font families, weights, size scale
- `spacing.json` — spacing/sizing scale
- `radius.json`, `shadow.json` — if needed
