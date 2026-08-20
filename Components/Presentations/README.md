# Presentations — cover, content page, and divider rules

Rules for decks (PPTX, HTML, Keynote, Google Slides — format doesn't matter, the rules do).

**Reference template:** `../../Templates/Presentation Template.html` is the living example of
every rule below applied together. When generating a new deck, use it as the starting structure
and CSS reference rather than building layout values from scratch. It's built as a single-slide
viewer (one slide visible at a time, with previous/next arrow controls and left/right arrow-key
support) rather than a long scrolling page of stacked slides — keep that viewer shell when
producing a new deck from this template, just swap in the slide content.

## No dashes in slide copy

Never use an en dash (`–`) or em dash (`—`) in generated slide content — titles, subtitles, lede
copy, card text, anything the audience reads. Rephrase with a period, comma, or a connecting word
("and", "then") instead.

## Page margin

Standard slide margin is **64px on all four edges — left, right, top, and bottom equally** on a
1920×1080 canvas (scale proportionally for other canvas sizes). This applies to every slide type
— covers, dividers, and content pages. Don't let one edge end up tighter than another (e.g. a
smaller bottom margin than top) — 64px all around, every time.

## Text boxes / filled containers (e.g. light-grey cards)

When content sits inside a filled box (card, tile, chip), padding must be equal on all four sides
of the text — including below the last line. In practice this means sizing the box to its
content plus fixed padding (e.g. `padding: 32px` with `height: auto`), not fitting variable-length
text into a fixed-height box, which leaves uneven (usually too little) padding at the bottom.

**Fill color:** any light background box/panel sitting on a white slide (cards, tiles) uses
`color.neutral.20`, not `neutral.10` or `neutral.0`. This is the standard "light box" fill —
use it consistently everywhere a filled container appears on a light page.

## No widows or orphans

This is a generic rule that applies to every text block in every layout, not just headlines:
titles, ledes, card copy, stat labels, agenda topics, talking-point body text, all of it. Never
end a line/paragraph with a single stranded word (widow) or leave a single word alone at the top
of a wrapped block (orphan). Apply `text-wrap: pretty` (or equivalent balancing) to every
multi-line text element, and when hand-tuning manual line breaks, check the last line of every
wrapped block for a lonely single word.

## Body text color

Main body text (lede paragraphs, card body copy, etc.) on a white/light background is always
`color.neutral.90`, not `neutral.80` or a lighter gray. The one exception is a big stat number
set in Ovo (see below) — those can be `color.pink.80` instead.

## Titles: leading

Every title (cover title, divider title, content-page title) uses a **0.9 line-height ratio** —
tighter than body copy, on purpose, for a confident display feel.

## Subtitle size is standardized

The "subtitle" tier — cover subtitle and content-page lede — is a single consistent size:
**32px, matching `typography.body.lg`.** Don't let the cover subtitle and content lede drift to
different sizes; they're the same tier and should read as the same tier everywhere in the deck.

## Front cover

- Background: `color.neutral.100`.
- Logo (Lockup, dark-mode/light-colored variant): bottom-left corner. Never top-left.
- No eyebrow/kicker text, ever. Covers do not carry a category label.
- No footer text and no page number on the cover.
- Only three elements on the page: title, subtitle, logo. Nothing else.
- **Title position is fixed, not per-deck.** The title always starts from the same X/Y position
  — top-left, at the top of the content area (roughly where the logo used to sit before it moved
  to the bottom-left). Don't re-tune this per deck; treat it as a fixed anchor point.
- **Title and subtitle never run past the horizontal middle of the page.** If a title or subtitle
  would extend past mid-page, wrap it onto a second line instead of shrinking the font or letting
  it run wide. Both blocks stay within the left half of the slide.
- Subtitle: sits below the title, smaller, supporting copy, same wrap rule as the title, and set
  in Instrument Sans **Regular weight** (not Medium) — lighter than the title, on purpose.

## Back cover

- Background: always `color.neutral.100`. No exceptions — never lime, pink, or any other color.
- Logo (Lockup, dark-mode/light-colored variant): centered both horizontally and vertically on
  the page.
- Nothing else on the page. No buttons, no CTAs (e.g. "Book a demo"), no headline, no body copy.
- Only permitted addition: small, quiet text with the year the deck was created (e.g. "2026"),
  placed unobtrusively (e.g. bottom center, small type, muted color like `color.neutral.60`/`70`).

## Main content pages

- **No Lockup logo on content pages.** The full logo only appears on the front and back cover.
  Content pages instead carry:
  - **Top-left:** a small quiet footnote that is always the deck's own title (e.g. "GWI for
    people in a hurry"), sitting exactly where the logo used to sit. This is not a page
    description or section label — it is always the presentation's title, verbatim, on every
    content page.
  - **Top-right:** the small "The Link" mark (see color rule below), unchanged position.
- **No eyebrow/kicker text** (e.g. "WHAT GWI IS") — this was already replaced by "The Link" mark
  and stays replaced.
- **Page numbers, if used, are a plain two-digit number** (e.g. `02`), never a "current / total"
  format (e.g. `02 / 04`). Only include a page number if the deck genuinely needs one — don't add
  it by default.
- **Stat/big numbers (e.g. large callout figures like "35B+", "2M+") are always set in Ovo, and
  set noticeably large** — bigger than a heading, since they're the visual anchor of the slide.
  Don't undersell them; they should read as the most prominent element after the title.
- With the top-left logo removed, the content-page title moves further up the page than before
  — use the freed vertical space rather than leaving a gap.
- **Title and lede (the content-page "subtitle") never run past the horizontal middle of the
  page**, same rule as the front cover — wrap onto a second/third line instead of running wide.
  Cards, stat rows, and other supporting content are not held to this width rule, only the title
  and lede text blocks.

## Divider pages

- **No Lockup, no Wordmark.** Dividers carry no full logo. They do, however, carry **"The Link"
  mark, top-right, in the same position as on main content pages.**
- **"The Link" mark color must contrast correctly with the divider background:**

  | Divider background | "The Link" color |
  |---|---|
  | `color.pink.100` | `color.neutral.0` |
  | `color.pink.10` | `color.neutral.100` |
  | `color.lime.20` | `color.lime.50` |
  | `color.lime.50` | `color.lime.20` |

  (Open gap: the "The Link" asset library currently ships Neutral 10, Neutral 100, Pink, Pink
  Light, Lime Dark, and Orange Dark variants — there is no exact Neutral 0 or Lime Light cut yet.
  Until those are added, use Neutral 10 as the closest stand-in for Neutral 0, and Lime Dark as
  the closest stand-in for `color.lime.50`; there is currently no usable stand-in for
  `color.lime.20` as a mark color, so flag that gap if a lime.50 divider is needed.)

- **Background must not be `color.neutral.100`.** That token is reserved for covers. Use
  `color.pink.100`, `color.pink.10`, `color.lime.20`, or `color.lime.50` instead — see
  `../../tokens/color-usage.md`.
- Layout: a small label (e.g. the deck/system name) top-left, then the header in Ovo, large,
  left-aligned, below it. No rule/divider line under the label — just the label, then the header.
  Nothing else on the page — no subtitle, no body copy, no card content.
- **The divider header is always the presentation's own main title** (the exact same text as the
  front cover title), not a section-specific line. Set it at the **same size and anchor position
  as the front cover title** (120px, `top: 140px; left: 64px; width: 880px`) so it reads as a
  restatement of the deck title, not a new heading style.

## Content page variants

Both variants below keep the same content-page rules as above (top-left title footnote, top-right
"The Link" mark colored for contrast, no eyebrow, title/lede width and wrap rules) — only the
layout below the header differs. See the reference template for both, in full.

### Agenda (numbered list, light)

- Background `color.neutral.0` (white), same as a standard content page.
- Title sits in the normal top-left title position/width.
- To the right, a vertical list of numbered rows: a small square chip (`color.lime.20` fill,
  4px radius, number in Ovo, dark text) on the left of each row, a topic label right-aligned on
  the right, and a 1px `color.neutral.30` rule under each row.
- No body copy, no cards, no stats. This layout is for a topic list only.

### Talking points (numbered columns, dark)

- Background `color.neutral.100` (same as covers), title and footer treatment match a dark
  content page (light "The Link" mark, light title footnote).
- Below the title, a row of equal-width columns (not boxed/carded), each with a large number in
  Ovo, `color.lime.20`, followed by a short paragraph in Instrument Sans (standard body size,
  24px, matching other supporting copy in the deck — this text stays small; it's the number and
  the page title that carry the visual weight, not the paragraph).
- **The page title ("Talking points") is set larger than a standard content-page title** (around
  104px vs. the usual 80px), and the numbers above each paragraph are bigger still, so the
  hierarchy reads: title, then number, then paragraph.
- Use for 3 to 4 short talking points; more than 4 columns will crowd the 64px margins.

## Rationale

Covers and dividers are brand real estate — calm, consistent, minimal across every deck. Content
pages carry the working information (kickers replaced by the mark, stats, cards, body copy) but
should stay quiet and predictable rather than reinvented per deck.
