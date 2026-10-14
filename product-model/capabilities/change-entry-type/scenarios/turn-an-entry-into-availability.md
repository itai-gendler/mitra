---
kind: alternative
routes:
  web: Web
steps:
- text: The User picks Availability under Type
  kind: actor
  actor: user
  entities:
  - {entity: event, effect: reads, facts: [Title]}
  - {entity: availability, effect: reads, facts: []}
  contexts:
    web:
      place: web::signed-in::entry-editor
- text: The calendar can hold availability
  kind: condition
  actor: user
  entities:
  - {entity: calendar, effect: reads, facts: [Holds]}
  - {entity: availability, effect: reads, facts: []}
  contexts:
    web:
      place: web::signed-in::entry-editor
- text: The Product saves availability with the entry's times and deletes the event
  kind: product
  actor: user
  entities:
  - {entity: availability, effect: creates, facts: [Name, Calendar, Place, Start, End, Time zone, Repeat, Busy or free]}
  - {entity: event, effect: removes}
  contexts:
    web:
      place: web::signed-in::entry-editor
---

# Turn an entry into availability

## Trigger

A one-off block of focus time should become availability.

## Outcome

The entry is availability in the same calendar, shaded in the week view, without participants or reminders.
