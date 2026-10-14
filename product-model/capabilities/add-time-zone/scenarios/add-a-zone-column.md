---
kind: primary
routes:
  web: Web
steps:
- text: The User presses the plus at the top of the time column and picks Tokyo
  kind: actor
  actor: user
  entities:
  - {entity: user, effect: reads, facts: [Added time zones]}
  contexts:
    web:
      place: web::signed-in::calendar-views
- text: The Product adds the zone to the user's list
  kind: product
  actor: user
  entities:
  - {entity: user, effect: changes, facts: [Added time zones]}
  contexts:
    web:
      place: web::signed-in::calendar-views
---

# Add a zone to the week

## Trigger

A colleague works from Tokyo.

## Outcome

A column shows Tokyo's hours beside the user's, headed by the zone's short name.

## Edge cases

- Adding a zone always brings folded columns out.
