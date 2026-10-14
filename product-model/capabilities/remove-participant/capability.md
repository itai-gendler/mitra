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
  target: src/features/participants/client/ParticipantsField.ts
- kind: doc
  role: intent
  target: docs/participants.md
  title: Participants
---

# Remove participant

Take one person off an entry with the cross beside them, or empty the list with Remove all. The calendar server tells removed people the entry was cancelled for them.
