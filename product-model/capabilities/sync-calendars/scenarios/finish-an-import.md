---
kind: unattended
routes:
  web: Web
steps:
- text: A calendar is importing
  kind: condition
  unattended: true
  entities:
  - {entity: calendar, effect: reads, facts: [Name]}
  contexts:
    web:
      place: web::signed-in::calendars-tab
- text: The Product imports its entries in the background and marks the calendar imported once a full pass completes
  kind: product
  entities:
  - {entity: calendar, effect: changes, from: Importing, to: Imported, facts: []}
  - {entity: event, effect: creates, facts: [Title, Calendar, Description, Location, Start, End, All day, Time zone, Repeat, Busy or free, Visibility, Reminders]}
  contexts:
    web:
      place: web::signed-in::calendars-tab
---

# Finish importing a calendar

## Trigger

A calendar was just turned on.

## Outcome

All its entries are in Mitra and it syncs only changes from now on.
