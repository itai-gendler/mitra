---
kind: edge
routes:
  web: Web
steps:
- text: A reminder went out while a device was offline
  kind: condition
  unattended: true
  entities:
  - {entity: event, effect: reads, facts: [Start]}
  - {entity: device, effect: reads, facts: []}
  contexts:
    web:
      place: web::signed-in::reminder-notification
- text: The Product lets the reminder lapse on that device five minutes after the entry starts
  kind: product
  entities:
  - {entity: device, effect: reads, facts: [Name]}
  contexts:
    web:
      place: web::signed-in::reminder-notification
---

# Drop a reminder a device gets too late

## Trigger

A phone was offline when a reminder went out.

## Outcome

The phone drops the reminder five minutes after the entry's start instead of showing it late.
