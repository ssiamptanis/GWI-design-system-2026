# Color usage rules

Guardrails for which colors are acceptable in which context. This is guidance for humans (and for the Claude Skill to enforce) — `color.json` holds the values, this file holds the rules.

## Backgrounds

Acceptable for backgrounds:

| Token | Hex | Use for |
|---|---|---|
| `color.neutral.0` | `#FFFFFF` | Default background for light applications — slides, reports, website |
| `color.neutral.10` | `#FBFAFA` | More unique slides within presentations — CTA slides, feature slides |
| `color.neutral.100` | `#1E1B1A` | Presentation covers, dividers (presentations, reports) |
| `color.pink.100` | `#CC005F` | Dividers (presentations, reports) |
| `color.pink.10` | `#FFF1F5` | Dividers (presentations, reports) |
| `color.lime.20` | `#EDFFB8` | Dividers (presentations, reports) |
| `color.lime.50` | `#729508` | Dividers (presentations, reports) |

## Rule

**Not listed above = not approved.** Any color/step not in the table is accent/UI use only, not a background, until it's explicitly added here. This currently rules out all of `color.orange.*` and `color.accessory.*` (success/warning/error/info/cta) as backgrounds.

## Notes

- Reference tokens by path (`color.group.step`), not by hex, so this doc stays correct if a value changes.
- If a background color needs a minimum contrast ratio against text (e.g. WCAG AA), note it here per color.
