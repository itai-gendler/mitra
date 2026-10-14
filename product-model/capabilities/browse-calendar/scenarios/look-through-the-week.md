---
kind: primary
routes:
  web: Web
steps:
- text: The User opens Mitra
  kind: actor
  actor: user
  entities: []
  contexts:
    web:
      place: web::signed-in::calendar-views
- text: The Product shows the default view around today with the entries of every visible calendar, and the week view shades availability
  kind: product
  actor: user
  entities:
  - {entity: user, effect: reads, facts: [Default view]}
  - {entity: event, effect: reads, facts: [Title, Start, End]}
  - {entity: task, effect: reads, facts: [Title, Start, End, Due date]}
  - {entity: availability, effect: reads, facts: [Start, End]}
  - {entity: calendar, effect: reads, facts: []}
  contexts:
    web:
      place: web::signed-in::calendar-views
- text: The User presses M and then the forward arrow
  kind: actor
  actor: user
  entities: []
  contexts:
    web:
      place: web::signed-in::calendar-views
- text: The Product shows the next month
  kind: product
  actor: user
  entities:
  - {entity: event, effect: reads, facts: [Title, Start]}
  contexts:
    web:
      place: web::signed-in::calendar-views
---

# Look through the week

## Trigger

The user opens Mitra in the morning.

## Outcome

The default view shows the user's visible calendars around today, events, tasks and availability side by side.

## Edge cases

- Weeks start on the day the language's region starts them on.
- With Hide done tasks on, done and cancelled tasks stay off the week, month and year views.
