---
availability:
- {place: 'web::signed-in'}
domain: calendars
references:
- kind: code
  role: implementation
  target: src/features/migration/server/SourceMigration.ts
- kind: code
  role: implementation
  target: src/features/migration/MigrationPlan.ts
- kind: code
  role: implementation
  target: src/features/migration/client/DialogSourceMigration.ts
- kind: doc
  role: intent
  target: docs/calendars.md
  title: Calendars
---

# Move calendar entries

Move everything in a calendar to another calendar with Move entries to… in its menu, or Move entries from … in the command palette. Before anything happens Mitra shows what the move would cost by what the destination can hold. Mitra copies first and deletes the originals only once their copies have landed; links between the moved entries come along.
