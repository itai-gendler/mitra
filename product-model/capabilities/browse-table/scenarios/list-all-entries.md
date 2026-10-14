---
kind: alternative
routes:
  web: Web
steps:
- text: The User chooses All entries in the When column's menu
  kind: actor
  actor: user
  entities: []
  contexts:
    web:
      place: web::signed-in::table-view
- text: The Product lists every entry and each series once, where it starts
  kind: product
  actor: user
  entities:
  - {entity: event, effect: reads, facts: [Title, Start, Repeat]}
  contexts:
    web:
      place: web::signed-in::table-view
---

# List all entries to tidy up

## Trigger

The user tidies up years of entries.

## Outcome

Every entry is listed, a repeating entry once for its whole series.
