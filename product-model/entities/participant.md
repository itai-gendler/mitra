---
references:
- kind: code
  role: implementation
  target: src/features/participants/Participant.ts
- kind: doc
  role: intent
  target: docs/participants.md
  title: Participants
---

# Participant

A person involved in an event or task, kept with the entry in the standard calendar format so every app using the calendar sees the same list. Rooms and equipment are not participants.

## Information kept

- **Email** — their address
- **Name** — their name, when the calendar knows it
- **Role** — Required or Optional
- **Organizer** — whether they organize the entry; the first person added in a calendar with an account behind it makes the user its organizer
- **Reply** — Accepted, Declined, Tentative, or awaiting a reply
