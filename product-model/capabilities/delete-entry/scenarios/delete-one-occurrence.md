---
kind: alternative
routes:
  web: Web
steps:
- text: The User presses Ctrl and Delete on an open occurrence
  kind: actor
  actor: user
  entities:
  - {entity: event, effect: reads, facts: [Repeat]}
  contexts:
    web:
      place: web::signed-in::entry-editor
- text: The Product excludes the date from the series
  kind: product
  actor: user
  entities:
  - {entity: event, effect: changes, facts: [Repeat]}
  contexts:
    web:
      place: web::signed-in::entry-editor
---

# Delete one occurrence of a series

## Trigger

One session of a weekly class is skipped.

## Outcome

That date is gone and stays gone, even when the series later moves; other apps leave it out too.

## Decision points

### Which occurrences

Without Ctrl, which entries does the user mean?

- This entry → only that date is removed from the series
- This and following entries → the series ends before it
- All entries → the whole series is deleted
