---
kind: unattended
routes:
  web: Web
steps:
- text: An event's reminder is due
  kind: condition
  unattended: true
  entities:
  - {entity: event, effect: reads, facts: [Reminders, Start]}
  contexts:
    web:
      place: web::signed-in::reminder-notification
- text: The Product sends the reminder to every device of the user, written in each device's language and time zone
  kind: product
  entities:
  - {entity: event, effect: reads, facts: [Title, Start, Location]}
  - {entity: device, effect: reads, facts: [Language, Time zone]}
  - {entity: user, effect: reads, facts: []}
  contexts:
    web:
      place: web::signed-in::reminder-notification
---

# Remind the user of a meeting

## Trigger

A meeting with a reminder 30 minutes before is about to start.

## Outcome

Every device of the user shows the meeting's title, when it is and its location, in its own language and time zone, until dismissed; tapping it opens the entry.

## Edge cases

- A calendar the user hid still reminds; a calendar turned off does not.
- A wall clock entry reminds at its clock time in each device's zone.
