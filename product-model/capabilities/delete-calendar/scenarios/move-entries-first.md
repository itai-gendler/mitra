---
kind: alternative
routes:
  web: Web
steps:
- text: The User chooses Delete calendar on a calendar with entries
  kind: actor
  actor: user
  entities:
  - {entity: calendar, effect: reads, facts: [Name]}
  contexts:
    web:
      place: web::signed-in::calendars-tab
- text: The Product warns that every entry goes too and offers Move entries first…
  kind: product
  actor: user
  entities: []
  contexts:
    web:
      place: web::signed-in::calendars-tab
- text: The User chooses Move entries first…
  kind: actor
  actor: user
  entities: []
  contexts:
    web:
      place: web::signed-in::calendars-tab
- text: The Product keeps the calendar and opens Move entries for it
  kind: product
  actor: user
  entities:
  - {entity: calendar, effect: reads, facts: [Name, Holds]}
  contexts:
    web:
      place: web::signed-in::move-entries
---

# Choose to move the entries first

## Trigger

The calendar still holds entries the user wants to keep.

## Outcome

The calendar stays, and the Product carries the user into moving its entries to another calendar.

## Edge cases

- When no other calendar could take the entries, Keep the calendar is offered instead.
