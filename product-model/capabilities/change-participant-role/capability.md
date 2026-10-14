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

# Change participant role

Mark a person optional, or required again, with the button beside them, or everyone at once with Mark all required or Mark all optional.
