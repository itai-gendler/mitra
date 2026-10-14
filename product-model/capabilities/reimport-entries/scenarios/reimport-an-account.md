---
kind: alternative
routes:
  web: Web
steps:
- text: The User chooses Re-import entries in an account's menu
  kind: actor
  actor: user
  entities:
  - {entity: integration, effect: reads, facts: [Provider]}
  contexts:
    web:
      place: web::signed-in::calendars-tab
- text: The Product re-imports each of the account's turned-on calendars
  kind: product
  actor: user
  entities:
  - {entity: calendar, effect: changes, from: Imported, to: Importing, facts: []}
  contexts:
    web:
      place: web::signed-in::calendars-tab
---

# Re-import a whole account

## Trigger

The Jira profile's time zone changed and every worklog should move.

## Outcome

Every turned-on calendar of the account is read again.
