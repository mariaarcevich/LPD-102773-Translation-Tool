# Translation Tool for Content Pages — prototype

Interactive prototype for **[LPD-102773](https://liferay.atlassian.net/browse/LPD-102773) — Translation Tool for Content Pages**, built with Lexicon Vanilla (Clay-faithful HTML + CSS, no build).

**▶ Live:** https://mariaarcevich.github.io/LPD-102773-Translation-Tool/

Figma (epic): [LPD-102773 — Translation Tool for Content Pages](https://www.figma.com/design/EtKyUuJfrxk8EIj5SN1T2O/LPD-102773--EPIC--Translation-Tool-for-Content-Pages?node-id=0-1)

## Flow to try

1. **Site Builder › Pages** (`index.html`) — open **⋮ › Translate** on *Orbit Summit 2026*.
2. **Translations table** — every language of the page with its status (Translated / Translating x/16 / Not Translated). Multi-select for bulk actions, filter by status, search, per-row ⋮ (Auto-translate, Mark as Translated, Reset Translation). The preview shows the page in the default language.
3. **Open a language** (e.g. French) — live preview on the left, translatable fields in the panel on the right:
   - the default-language text is always shown under each field as reference;
   - a field turns green (**✓ Translated**) when you leave it; *Marked as Translated: Uses Default Value* when it holds the default text; purple **AI Translated** after Auto-translate;
   - click a preview element to jump to its field (and vice versa); filter / search fields;
   - **Translations › es-ES** breadcrumb takes you back to the table;
   - the panel sits on the right of the preview (**⋮ › Move Panel to the Left** to compare); drag the divider to resize it (30% by default, 300–600px).
4. **Experience** (top of the panel) scopes the translation; each experience shows **Draft** / **Published**.
5. **Autosave** — every change is saved as a draft automatically (check icon in the header, spinner while saving), so leaving never loses work. **⋮ › Discard Draft** restores the last published version. **Publish** asks for confirmation, listing every experience with changes.

### CMS content

6. From **Pages**, open the **Applications Menu** (grid icon, top right) › **CMS**.
7. In **Contents**, open **⋮ › Translate** on a content. The same tool opens, in CMS mode:
   - no experiences (display pages and the CMS have none) and CMS Style (rounded corners);
   - the blue preview bar adds **Channel** (None · the sites connected to the content's space · External URL) and **Display Page** (that site's templates), so you choose where to preview the translation;
   - *The Future of Conversational AI* (space connected to two sites) previews in *Partner Portal* (Classic theme) or *Liferay DXP Site* (Article / Article Minimal);
   - *Behind the Scenes at Orbit Summit* (space with no site) previews by default as the plain, read-only content form (**Channel: None**).
   Back and Cancel return to the CMS list.

Edge cases: *Spring Campaign* is a blank page ("No Content to Translate"); *Search* is a widget page (no Translate action). On screens under 768px the preview is replaced by **⋮ › Preview in a New Tab**.

> Drafts are stored in your own browser (localStorage) — each reviewer has their own.

## Files

- `index.html` — Site Builder › Pages (entry point)
- `cms.html` — CMS › Contents
- `translation-editor.html` — the translation tool
- `tokens*.css`, `components.css`, `icons.js`, `illustrations/` — Lexicon Vanilla kit
