---
appliesTo:
- type: entity
  id: participant
references:
- kind: doc
  role: intent
  target: docs/participants.md
  title: Participants
---

# Invitations travel through the calendar server

Mitra never sends email itself. The calendar server behind an entry's calendar sends the invitation, an update when the entry changes and a cancellation when someone is removed or the entry is deleted, and collects the replies, which reach Mitra on the next sync. Mitra shows everyone's reply but does not send the user's own.
