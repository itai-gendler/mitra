---
kind: primary
routes:
  web: Web
steps:
- text: The User drags an .ics file onto Mitra and picks a calendar
  kind: actor
  actor: user
  entities:
  - {entity: calendar, effect: reads, facts: [Name, Holds]}
  contexts:
    web:
      place: web::signed-in::calendar-file-import
- text: The Product shows the entries it would leave out and the details some would lose
  kind: product
  actor: user
  entities:
  - {entity: event, effect: reads, facts: [Title]}
  contexts:
    web:
      place: web::signed-in::calendar-file-import
- text: The User presses Add 12 entries
  kind: actor
  actor: user
  entities: []
  contexts:
    web:
      place: web::signed-in::calendar-file-import
- text: The Product adds a new copy of each entry
  kind: product
  actor: user
  entities:
  - {entity: event, effect: creates, facts: [Title, Calendar, Description, Location, Start, End, All day, Time zone, Repeat, Reminders]}
  contexts:
    web:
      place: web::signed-in::calendar-file-import
---

# Drop a calendar file onto Mitra

## Trigger

An invitation arrived as an .ics attachment.

## Outcome

The entries are added to the picked calendar as new copies.

## Edge cases

- Adding the same file twice gives every entry twice.
- A repeating series keeps its deleted occurrences deleted.
- Several files open one after another.
