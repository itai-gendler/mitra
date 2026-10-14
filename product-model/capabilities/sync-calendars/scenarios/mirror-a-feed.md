---
kind: unattended
routes:
  web: Web
steps:
- text: A subscription is due to sync, every 15 minutes whether or not anyone has Mitra open
  kind: condition
  unattended: true
  entities:
  - {entity: calendar, effect: reads, facts: [Name]}
  contexts:
    web:
      place: web::signed-in::calendar-views
- text: The Product asks the feed's server whether anything changed and, only when it did, downloads it and mirrors it
  kind: product
  entities:
  - {entity: event, as: added, effect: creates, facts: [Title, Calendar, Description, Location, Start, End, All day, Time zone, Repeat]}
  - {entity: event, as: removed, effect: removes}
  contexts:
    web:
      place: web::signed-in::calendar-views
---

# Mirror a subscription's feed

## Trigger

A sports club adds and cancels fixtures in its feed.

## Outcome

Entries added to the feed appear, and entries removed from it disappear.
