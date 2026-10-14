---
appliesTo:
- type: capability
  id: move-calendar-entries
- type: capability
  id: move-entry-to-calendar
- type: capability
  id: change-entry-type
references:
- kind: code
  role: implementation
  target: src/features/migration/server/SourceMigration.ts
- kind: doc
  role: intent
  target: docs/calendars.md
  title: Calendars
---

# A move never loses an entry

There is no undo across two providers, so Mitra copies first and deletes the originals only once their copies have landed: if something goes wrong an entry may end up in both calendars, never in neither, and if copying fails the whole move stops and nothing is deleted.
