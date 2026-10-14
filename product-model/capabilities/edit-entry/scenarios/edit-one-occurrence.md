---
kind: alternative
routes:
  web: Web
steps:
- text: The User changes the title of one occurrence of a repeating event
  kind: actor
  actor: user
  entities:
  - {entity: event, effect: reads, facts: []}
  contexts:
    web:
      place: web::signed-in::entry-editor
- text: The Product asks whether this entry, this and following entries, or all entries are meant
  kind: product
  actor: user
  entities:
  - {entity: event, effect: reads, facts: [Repeat]}
  contexts:
    web:
      place: web::signed-in::entry-editor
- text: The User chooses This entry
  kind: actor
  actor: user
  entities: []
  contexts:
    web:
      place: web::signed-in::entry-editor
- text: The Product saves the occurrence as an entry of its own and the series skips its date
  kind: product
  actor: user
  entities:
  - {entity: event, effect: changes, facts: [Title, Repeat]}
  contexts:
    web:
      place: web::signed-in::entry-editor
---

# Change one occurrence of a series

## Trigger

The user renames one meeting of a weekly series.

## Outcome

The change applies to the occurrences the user chose; an occurrence changed on its own leaves the series and later series changes do not reach it.

## Decision points

### Which occurrences

Which entries does the user mean?

- This entry → only the chosen occurrence changes and leaves the series
- This and following entries → the series ends just before it and a new series starts there with the change
- All entries → every occurrence changes

## Edge cases

- The first occurrence does not offer This and following entries, since there it would mean the whole series.
