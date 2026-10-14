---
kind: validation
routes:
  web: Web
steps:
- text: The User opens an event organized by someone else
  kind: actor
  actor: user
  entities:
  - {entity: event, effect: reads, facts: [Organized by someone else]}
  contexts:
    web:
      place: web::signed-in::entry-editor
- text: The Product hides the plus and offers only Email participants and Copy participants' emails
  kind: product
  actor: user
  entities:
  - {entity: participant, effect: reads, facts: [Email, Reply]}
  contexts:
    web:
      place: web::signed-in::entry-editor
---

# Leave someone else's list alone

## Trigger

The user opens an invitation someone else organized.

## Outcome

The list can be read, emailed and copied, but not changed; the rest of the entry can still be edited.

## Edge cases

- The server refuses a change to the list from anyone but the organizer too, with "Only the organizer can modify participants".
- To accept or decline, the user answers in their mail app or another calendar app, and the reply syncs back.
