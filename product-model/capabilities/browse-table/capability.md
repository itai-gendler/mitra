---
availability:
- {place: 'web::signed-in'}
domain: views
references:
- kind: code
  role: implementation
  target: src/features/calendar/client/Table.ts
- kind: code
  role: implementation
  target: src/features/calendar/client/TableWindow.ts
- kind: doc
  role: intent
  target: docs/views/table.md
  title: Table view
---

# Browse table

List the user's entries as rows in the table view: choose the span in the When column's menu (Past 30 days, Today, Next 7 days, Next 30 days, Next 12 months, All entries or a custom range), search titles, locations, descriptions and calendars, sort and filter by column, and show, hide, move and resize columns. Tasks without a date and overdue open tasks are listed whatever the span.
