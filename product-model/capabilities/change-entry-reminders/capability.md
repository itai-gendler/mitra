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
  target: src/features/reminders/client/RemindersField.ts
- kind: doc
  role: intent
  target: docs/reminders.md
  title: Reminders
---

# Change entry reminders

Add or remove an entry's reminders on its row with the bell: at the start, 5 or 10 minutes, half an hour, an hour or a day before, or any custom time. An entry can have several. Notion and Tempo calendars cannot hold reminders, and availability has none.
