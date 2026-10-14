---
availability:
- {place: 'web::signed-in'}
references:
- kind: code
  role: implementation
  target: src/features/entries/server/entries.ts#entriesRouter
- kind: code
  role: implementation
  target: src/features/entries/Entry.ts#Entry
- kind: code
  role: implementation
  target: src/features/entries/Transparency.ts
- kind: doc
  role: intent
  target: docs/entries.md
  title: Entries
- kind: doc
  role: intent
  target: docs/availability.md
  title: Availability
---

# Change busy or free

Choose whether an event or availability shows as Busy or Free. Events start Busy and availability starts Free. Tasks have neither.
