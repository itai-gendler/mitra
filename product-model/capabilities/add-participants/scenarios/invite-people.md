---
kind: primary
routes:
  web: Web
steps:
- text: The User types two email addresses into Add participants and presses Enter
  kind: actor
  actor: user
  entities:
  - {entity: event, effect: reads, facts: []}
  - {entity: participant, as: invitee, effect: reads, facts: []}
  contexts:
    web:
      place: web::signed-in::entry-editor
- text: The Product adds both people and the user's own address as organizer, accepted
  kind: product
  actor: user
  entities:
  - {entity: participant, as: invitee, effect: creates, facts: [Email, Role, Reply]}
  - {entity: participant, as: organizer, effect: creates, facts: [Email, Organizer, Reply]}
  - {entity: integration, effect: reads, facts: [Own addresses]}
  contexts:
    web:
      place: web::signed-in::entry-editor
---

# Invite people to an event

## Trigger

The user sets up a meeting in a calendar on a calendar server.

## Outcome

The invitees are listed, awaiting a reply, with the user as organizer, accepted; the server sends the invitations.

## Edge cases

- A server that only stores calendars sends nothing, so nobody hears about the entry and every reply stays pending.
- Moving the entry to another calendar later may make some servers tell the participants it was cancelled.
