# Translation Tool for Content Pages — prototype

Interactive prototype for **[LPD-102773](https://liferay.atlassian.net/browse/LPD-102773) — Translation Tool for Content Pages**, built with Lexicon Vanilla (Clay-faithful HTML + CSS, no build).

**▶ Live:** https://mariaarcevich.github.io/LPD-102773-Translation-Tool/

Figma (epic): [LPD-102773 — Translation Tool for Content Pages](https://www.figma.com/design/EtKyUuJfrxk8EIj5SN1T2O/LPD-102773--EPIC--Translation-Tool-for-Content-Pages?node-id=0-1)

## Flow to try

1. **Site Builder › Pages** (`index.html`) — open **⋮ › Translate** on *Orbit Summit 2026*.
2. **Translations table** — every language of the page with its status (Translated / Translating x/16 / Not Translated). Multi-select for bulk actions, filter by status, search, per-row ⋮ (Auto-translate, Mark as Translated, Reset Translation). The preview shows the page in the default language.
3. **Open a language** (e.g. French) — translatable fields on the left, live preview on the right:
   - the default-language text is always shown under each field as reference;
   - a field turns green (**✓ Translated**) when you leave it; *Marked as Translated: Uses Default Value* when it holds the default text; purple **AI Translated** after Auto-translate;
   - click a preview element to jump to its field (and vice versa); filter / search fields;
   - drag the divider to resize the panel.
4. **Experience** (top of the panel) scopes the translation; each experience shows **Draft** / **Published**.
5. **Save as Draft** keeps your progress and returns to Pages. **Publish** asks for confirmation, listing every experience with changes.

Edge cases: *Spring Campaign* is a blank page ("No Content to Translate"); *Search* is a widget page (no Translate action). On screens under 768px the preview is replaced by **⋮ › Preview in a New Tab**.

> Drafts are stored in your own browser (localStorage) — each reviewer has their own.

## Files

- `index.html` — Site Builder › Pages (entry point)
- `translation-editor.html` — the translation tool
- `tokens*.css`, `components.css`, `icons.js`, `illustrations/` — Lexicon Vanilla kit
