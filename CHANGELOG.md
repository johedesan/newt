# Newt — Changelog

Newt is the manuscript correction interface of the Newton Principia Project: https://johedesan.github.io/newt/

## How releases work

- **Main version** (`/newt/`): the one everyone uses.
- **Test version** (`/newt/dev/`): new builds are tried here first. A dev build has a red "DEV BUILD" badge in the corner and `[DEV]` in the tab title.
- When a dev build has been tested in real work, it replaces the main version, and its changes are listed here.
- **Both versions share the same browser storage.** Before trying a dev build: export a full backup (Settings → Import & Export), and keep only one Newt tab open.

Newest version first.

---

## v1.28 — 29 October 2026

Replaces v1.25 as the main Newt. Includes v1.26, v1.27 and v1.28, all tested in the dev builds (v1.27-dev1 to dev10, v1.28-dev1) between 14 and 29 October.

Old data opens as before: projects, units and backups made with v1.25 load unchanged, and the old margin markup `{M:…}` still displays.

### Markup

- **Markup row:**
  - **U ▾** chooses between `[?mid: …?]`, `[?low: …?]` and `[?unclear?]`.
  - **ov** writes `{ov:new|}`, with the cursor after `|`, so the letters underneath can be added (optional).
  - New buttons: **b** (bold), **hc** (visible change of hand), **nadd** (addition inside an addition), **supp** (letters hidden in the gutter), **[ ]** (bracket the supplied letters of an abbreviation, e.g. `atq[ue]`).
  - **SD** has left the bar; it stays in the Status column.
- **Structure group** (**H · L · M · AL**):
  - `{h:…}` heading, `{lab:…}` label
  - `[margin: …]` margin note: at the start of the line = left margin, at the end = right margin. It replaces `{M:…}`.
  - `{al:…}` whole added line
- **Extra Markup:** `{cw:…}` catchword.
- **Layout group** (Additional → Layout):
  - **Pos ▾** places `{pos:…}` (3×3 grid) at the start of a line, for blocks on sparse pages.
  - **Sp ▾** writes `{space:N letters|words|lines}`, for a blank left in the manuscript.
  - **Top / Btm** wrap the selection as `[top: …]` / `[bottom: …]`.
- **Ω symbol picker,** now split into **Mathematical** and **Other Signs:**
  - `¬` line-end hyphen and `‸` caret
  - `{sign:double-x}` reference sign, `{sign:asterisk}` Newton's place marker, `{sign:filler}` wavy line filler, `{sign:unknown|…}` with an optional description
  - `⌊` decimal separatrix
- Symbols are inserted at the cursor, not at the end of the line.
- Labels display in bold.

### Per unit

- **Tier** dropdown (1–5, colour-coded), before Cluster.
- **Timer** (optional: Settings → Features): one running total per unit. It pauses and saves when you switch unit.
- **Page notes** (optional: Settings → Features): the 📝 button beside the timer. The note is stored with the unit, appears in the MD export header, and is read at the XML stage. It never goes into the published XML.
- **Page breaks:** `[PAGE BREAK]` rows show as unnumbered dividers, and line numbering restarts at 1 after each one.
- **1→ Renumber** numbers all lines 1, 2, 3… from the top, restarting after page breaks, so numbers like 55.1 become whole numbers.

### Exports and backups

- **Corrected MD** carries the tier, time and page note in its header, and keeps all markup.
- **"All units as Markdown"** now exports the text, not just the headings.
- **Level 0 TEI:** markup is exported exactly as typed, `[PAGE BREAK]` becomes `<pb/>`, and the filename carries the project prefix.
- **Single-project JSON** keeps tier, time and cluster. Backups are stamped `newt_v1_28`.
- **Restore full backup…** (Settings → Import & Export) makes an automatic safety copy first.
- Export headers say "AI" instead of "Gemini".

### Fixes

- Pasting into the HTR column no longer copies the text into Corrected. Move lines across deliberately, with "fill all" or a double-click (v1.26).
- `^` inside `$…$` no longer breaks the display of additions.
- New projects start with LaTeX on, and Feature switches save immediately.
- Pressing Enter in the unit dropdown now clears the table. This was the likely cause of the previous unit's text appearing in a new unit.
- The IIIF/local lock button now updates when a new unit is created.
- The tier display is easier to read, and the timer sits beside Settings, so the export buttons no longer shift.

Aligned with the AI prompt `AI_prompt_Humphrey_Newton_1_9.md` and the TEI Encoding Guidelines v3.5.

---

## v1.25 and earlier

Changes before v1.28 were not recorded in this file. v1.25 was the main version from late September to 29 October 2026.
