---
kind: alternative
routes:
  web: Web
steps:
- text: The User chooses Delete calendar on a calendar with no entries
  kind: actor
  actor: user
  entities:
  - {entity: calendar, effect: reads, facts: [Name]}
  contexts:
    web:
      place: web::signed-in::calendars-tab
- text: The Product deletes it
  kind: product
  actor: user
  entities:
  - {entity: calendar, effect: removes, from: Imported}
  contexts:
    web:
      place: web::signed-in::calendars-tab
---

# Delete an empty calendar

## Trigger

The calendar holds nothing.

## Outcome

The calendar is deleted without a question.
