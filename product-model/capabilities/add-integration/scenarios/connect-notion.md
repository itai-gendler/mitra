---
kind: alternative
routes:
  web: Web
steps:
- text: The User chooses Notion, pastes the integration token and presses Connect
  kind: actor
  actor: user
  entities:
  - {entity: integration, effect: reads, facts: []}
  contexts:
    web:
      place: web::signed-in::integration-details
- text: The Product lists the table, board, list, calendar, timeline and gallery views of the shared databases that have a Status and a Date property, one per database ticked
  kind: product
  actor: user
  entities:
  - {entity: calendar, effect: reads, facts: [Name, Holds]}
  contexts:
    web:
      place: web::signed-in::integration-details
- text: The User presses Save
  kind: actor
  actor: user
  entities: []
  contexts:
    web:
      place: web::signed-in::integration-details
- text: The Product saves the workspace with the chosen views as calendars of tasks and imports them
  kind: product
  actor: user
  entities:
  - {entity: integration, effect: creates, facts: [Provider, Connection details, Secret, Order]}
  - {entity: calendar, effect: creates, to: Importing, facts: [Name, Provider name, Color, Holds, Read-only, Hidden, Order], with: integration}
  - {entity: task, effect: reads, facts: []}
  contexts:
    web:
      place: web::signed-in::calendars-tab
---

# Connect a Notion workspace

## Trigger

The user tracks tasks in Notion databases.

## Outcome

Each chosen view of a task database is a calendar of tasks syncing both ways; one view per database is ticked to start with.

## Edge cases

- Tempo connects with a site URL, a Tempo API token, the Atlassian account email and an Atlassian API token, and lists one calendar, My worklogs.
