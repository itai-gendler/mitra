---
entities:
- entity: event
  shows: [Title, Start, Calendar]
- entity: task
  shows: [Title, Start, Calendar]
references:
- kind: code
  role: implementation
  target: src/features/commands/client/CommandPalette.ts
- kind: doc
  role: intent
  target: docs/shortcuts.md
  title: Keyboard shortcuts
---

# Command palette

A search over the titles, descriptions and locations in all the user's visible calendars, beside every command with its keys.
