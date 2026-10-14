---
kind: primary
routes:
  web: Web
steps:
- text: The User clicks the zone's name and chooses Make home
  kind: actor
  actor: user
  entities:
  - {entity: user, effect: reads, facts: [Home time zone]}
  contexts:
    web:
      place: web::signed-in::calendar-views
- text: The Product makes it home and keeps the old home on the list
  kind: product
  actor: user
  entities:
  - {entity: user, effect: changes, facts: [Home time zone, Added time zones]}
  contexts:
    web:
      place: web::signed-in::calendar-views
---

# Make a zone home

## Trigger

The user moved to another city.

## Outcome

The new zone is home, marked with a house, and the old home stays as a column.
