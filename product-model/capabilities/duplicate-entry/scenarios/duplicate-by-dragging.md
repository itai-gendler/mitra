---
kind: alternative
routes:
  web: Web
steps:
- text: The User holds Alt and drags an entry to another time
  kind: actor
  actor: user
  entities:
  - {entity: event, effect: reads, facts: [Start]}
  contexts:
    web:
      place: web::signed-in::calendar-views
- text: The Product saves a copy at the drop time
  kind: product
  actor: user
  entities:
  - {entity: event, effect: creates, facts: [Title, Calendar, Description, Location, Color, Start, End, All day, Time zone, Busy or free, Visibility, Reminders]}
  contexts:
    web:
      place: web::signed-in::calendar-views
---

# Copy an entry by Alt-dragging

## Trigger

The user books more time on the same Jira issue.

## Outcome

A copy lands at the drop time; the original stays.
