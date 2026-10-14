---
availability:
- {place: 'web::signed-in'}
references:
- kind: code
  role: implementation
  target: src/features/migration/server/IcsImport.ts
- kind: code
  role: implementation
  target: src/features/migration/client/DialogIcsImport.ts
- kind: code
  role: implementation
  target: src/app/launch.ts
- kind: doc
  role: intent
  target: docs/calendar-files.md
  title: Calendar files
---

# Add calendar file

Add the entries of an .ics file to a calendar by dragging the file onto Mitra, or by opening it with Mitra installed as an app. Mitra asks which calendar, shows what that calendar cannot store, and adds a new copy of each entry; nothing already in the calendar is overwritten. Subtasks and dependencies within the file stay linked.
