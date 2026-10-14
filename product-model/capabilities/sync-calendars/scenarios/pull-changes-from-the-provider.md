---
kind: unattended
routes:
  web: Web
steps:
- text: A turned-on calendar of a connected account is due to sync
  kind: condition
  unattended: true
  entities:
  - {entity: calendar, effect: reads, facts: [Name]}
  contexts:
    web:
      place: web::signed-in::calendar-views
- text: The Product fetches what changed at the provider and applies it to its copy
  kind: product
  entities:
  - {entity: event, effect: changes, facts: [Title, Start, End, Location, Description]}
  contexts:
    web:
      place: web::signed-in::calendar-views
---

# Bring in changes made elsewhere

## Trigger

Someone changes an event in another app using the same CalDAV calendar.

## Outcome

The change shows in Mitra after the next sync, and only what changed was fetched.
