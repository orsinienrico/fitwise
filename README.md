# Fitwise — Claude Code Handoff Package

Questo pacchetto contiene tutto quello che serve per continuare lo sviluppo in Claude Code.

## Contenuto

- `index.html` — demo/app HTML standalone generata finora.
- `docs/CLAUDE_CODE_PROMPT.md` — prompt completo da incollare in Claude Code.
- `docs/PRODUCT_BRIEF.md` — sintesi prodotto, brand, UX, direzione creativa.
- `docs/TODO_FIXES.md` — problemi aperti e fix prioritari.
- `docs/IMPLEMENTATION_NOTES.md` — note tecniche sull'HTML attuale e vincoli.
- `archive/index_current_snapshot.html` — snapshot dell'HTML corrente.

## Come usarlo con Claude Code

1. Apri una cartella locale o un repo GitHub.
2. Estrai questo ZIP.
3. Apri Claude Code nella cartella.
4. Incolla il contenuto di `docs/CLAUDE_CODE_PROMPT.md`.
5. Chiedi esplicitamente: `Apply the changes directly to index.html. Keep it single-file HTML/CSS/JS.`

## Regola importante

Non trasformare la demo in React, Next.js o altro framework. Per ora deve restare un singolo file:

```text
index.html
```

