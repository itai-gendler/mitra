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
  target: src/features/recurrence/Recurrence.ts
- kind: code
  role: implementation
  target: src/features/recurrence/client/RepeatField.ts
- kind: doc
  role: intent
  target: docs/repeats.md
  title: Repeats
---

# Change entry repeat

Pick a repeat rule in the Repeat row, which shows once the entry has a start, or a due date for an unscheduled task. The list offers rules built from the date the series starts; Custom… builds any interval with an end; Does not repeat stops it. A change to the rule always applies to the whole series. Notion and Tempo calendars cannot repeat entries.
