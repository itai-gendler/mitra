---
kind: primary
routes:
  web: Web
steps:
- text: The User picks Every week in the Repeat row
  kind: actor
  actor: user
  entities:
  - {entity: event, effect: reads, facts: [Start, Repeat]}
  contexts:
    web:
      place: web::signed-in::entry-editor
- text: The Product saves the rule on the series
  kind: product
  actor: user
  entities:
  - {entity: event, effect: changes, facts: [Repeat]}
  contexts:
    web:
      place: web::signed-in::entry-editor
---

# Make an entry repeat weekly

## Trigger

A meeting becomes a weekly one.

## Outcome

The entry is one series with a weekly rule, and every occurrence shows a repeat icon.

## Edge cases

- For a start on the 13th that is a Tuesday, the list offers every day, every weekday, every week or 2 weeks on Tuesday, every month on the 13th or on the 2nd Tuesday, and every year; in the last seven days of a month also the last Tuesday.
