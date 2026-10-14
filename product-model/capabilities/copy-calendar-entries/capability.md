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

# Copy calendar entries

Put a copy of every entry of a calendar in another calendar with Copy instead, leaving the originals where they are. It is how entries leave a read-only calendar, such as a subscription.
