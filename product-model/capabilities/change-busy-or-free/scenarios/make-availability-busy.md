---
kind: alternative
routes:
  web: Web
steps:
- text: The User picks Busy on a window of availability
  kind: actor
  actor: user
  entities:
  - {entity: availability, effect: reads, facts: [Busy or free]}
  contexts:
    web:
      place: web::signed-in::entry-editor
- text: The Product saves Busy and writes the busy events to the calendar's provider
  kind: product
  actor: user
  entities:
  - {entity: availability, effect: changes, facts: [Busy or free]}
  - {entity: calendar, effect: reads, facts: []}
  - {entity: event, effect: reads, facts: []}
  contexts:
    web:
      place: web::signed-in::entry-editor
---

# Make availability busy

## Trigger

Focus time should show as taken to people who invite the user.

## Outcome

The availability is Busy; in a CalDAV, Google or Apple calendar it is also written as repeating busy events with its name, or "Busy", its place and its visibility.

## Edge cases

- Inside Mitra busy and free availability look the same; busy events are not shown twice.
- A calendar that holds only tasks, or one the user cannot write to, gets no busy events.
