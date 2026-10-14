---
kind: validation
routes:
  web: Web
steps:
- text: The User drops a file that is not a calendar and picks a calendar
  kind: actor
  actor: user
  entities:
  - {entity: calendar, effect: reads, facts: [Name]}
  contexts:
    web:
      place: web::signed-in::calendar-file-import
- text: The Product refuses the file and says why
  kind: product
  actor: user
  entities: []
  contexts:
    web:
      place: web::signed-in::calendar-file-import
---

# Refuse an unreadable file

## Trigger

The file is not a calendar.

## Outcome

Nothing is added; the user reads "The file is not a readable calendar (.ics) file".

## Edge cases

- A file with no events or tasks is refused with "The file contains no events or tasks".
- A file larger than 20 MB is refused with "The file is too large to import".
