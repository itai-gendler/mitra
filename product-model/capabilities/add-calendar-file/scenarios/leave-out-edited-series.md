---
kind: alternative
routes:
  web: Web
steps:
- text: The User opens a file whose series has an edited occurrence and picks a calendar
  kind: actor
  actor: user
  entities:
  - {entity: calendar, effect: reads, facts: [Name]}
  contexts:
    web:
      place: web::signed-in::calendar-file-import
- text: The Product lists the series among the entries it leaves out
  kind: product
  actor: user
  entities:
  - {entity: event, effect: reads, facts: [Title]}
  contexts:
    web:
      place: web::signed-in::calendar-file-import
---

# Leave out a series with edited occurrences

## Trigger

The file holds a meeting series with one meeting moved.

## Outcome

The rest is added; that series is left out, since a series cannot be added together with its edits.
