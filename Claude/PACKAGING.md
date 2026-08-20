# Packaging a standalone skill from this repo

The repo is the single source of truth. `Claude/SKILL.md` is the *source* skill — it uses
relative paths (`../tokens/...`) that only resolve when this repo is checked out (Cursor,
Claude Code, git-aware tools). For Claude apps (chat, Cowork) that can't read the repo directly,
package a **standalone, self-contained `.skill` bundle** instead, and re-share it whenever
there's a major milestone update.

## What goes in the bundle

Copy these into one flat skill folder (all as siblings, no repo-relative paths):

- `Components/` (Buttons, Flags, Icons, Logo, Presentations)
- `Typography/`
- `tokens/`
- `Templates/Presentation Template.html` only — **not** `Templates/test-outputs/` (that's test
  output, not a system asset)
- `FILE-STRUCTURE.md`

Then add a `SKILL.md` at the root of that folder — a copy of `Claude/SKILL.md` with every
`../` stripped from its file paths (since the sibling folders now live inside the skill itself,
not one level up), plus a short note at the bottom that this is a snapshot, not a live sync.

Exclude: `.git`, `.DS_Store`, `node_modules`, and anything under `Templates/test-outputs/`.

## How to package it (ask Claude to do this)

1. Copy the folders above into a fresh flat directory.
2. Write the adjusted `SKILL.md` at its root.
3. Run the skill-creator's packager against that directory:
   `python -m scripts.package_skill <path-to-folder> <output-dir>`
4. This validates frontmatter and zips it into a `.skill` file.

## Naming and versioning

Name each package `gwi-design-system-2026-V<n>-<Month>-<Year>.skill` (e.g.
`gwi-design-system-2026-V2-October-2026.skill`), incrementing V on every repackage.

## Where it lives

Drop the new `.skill` file into `Claude/Latest skill packaged/`, replacing the previous one
(delete the old file/version once the new one is confirmed good — don't let old versions pile
up and cause confusion about which is current).

## Distributing it

Either of these, per the org-wide distribution decision already made:

- Give the file to a Claude Team/Enterprise admin to upload at `claude.ai/admin-settings/skills`
  and provision org-wide (enabled by default for everyone, no install step per person).
- Or host it somewhere central (e.g. a "latest skill" page/link) for people to grab and use
  "Save skill" themselves.

## Size discipline

Skills have a **30MB uncompressed** ceiling. Fonts and flag illustrations are the heaviest
items per file — if the repo grows a lot (many more icons, more typefaces, more flags), consider
dropping PNGs from the bundle (SVG-only) before dropping content, since PNGs largely duplicate
what the SVGs already provide.
