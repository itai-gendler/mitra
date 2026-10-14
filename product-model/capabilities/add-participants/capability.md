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

# Add participants

Add people to an event or task by typing email addresses into Add participants, several at once separated by commas, semicolons or spaces. In a calendar with an account behind it, the first person added makes the user the organizer, and the calendar server sends the invitations and collects the replies; in a Mitra calendar the list is a record only. Notion and Tempo calendars have no participants.
