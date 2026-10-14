---
availability:
- {place: 'web::signed-in'}
references:
- kind: code
  role: implementation
  target: src/features/commands/client/CommandPalette.ts
- kind: code
  role: implementation
  target: src/features/entries/server/entryWindow.ts
- kind: doc
  role: intent
  target: docs/shortcuts.md
  title: Keyboard shortcuts
---

# Search entries

Search the titles, descriptions and locations in all the user's visible calendars, not just the days on screen, from the command palette opened with /, Ctrl+K or Ctrl+P. Choosing an entry goes to its date and opens it.
