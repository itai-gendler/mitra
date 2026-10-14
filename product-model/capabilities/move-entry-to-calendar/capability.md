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
- kind: doc
  role: intent
  target: docs/calendars.md
  title: Calendars
---

# Move entry to calendar

Move one entry to another calendar from its editor, or the selected rows of the table view with Move to…. The list leaves out calendars that could not keep something the entry has. Mitra saves the entry in the new calendar first and deletes the original only once that succeeded, so a failure never loses the entry.
