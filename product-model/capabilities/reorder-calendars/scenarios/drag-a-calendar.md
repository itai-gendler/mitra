---
kind: primary
routes:
  web: Web
steps:
- text: The User drags a calendar to the top of its account
  kind: actor
  actor: user
  entities:
  - {entity: calendar, effect: reads, facts: [Order]}
  contexts:
    web:
      place: web::signed-in::calendars-tab
- text: The Product saves the order of the account's calendars
  kind: product
  actor: user
  entities:
  - {entity: calendar, effect: changes, facts: [Order]}
  contexts:
    web:
      place: web::signed-in::calendars-tab
---

# Drag a calendar within its account

## Trigger

The user wants their main calendar on top.

## Outcome

The calendar keeps its new place; with no default calendar, the top one is where new entries go.

## Edge cases

- A calendar turned on later joins the end of its account.
