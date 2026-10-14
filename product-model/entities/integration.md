---
domain: calendars
relations:
- entity: calendar
  verb: has
  cardinality: one-to-many
references:
- kind: code
  role: implementation
  target: src/integrations/Integration.ts#Integration
- kind: code
  role: implementation
  target: src/integrations/registerIntegrations.ts
- kind: doc
  role: intent
  target: docs/integrations/README.md
  title: Integrations
---

# Integration

One account a user connected, or the Mitra integration that keeps calendars on the server itself. Its calendars sit under its heading in the sidebar. Each account is connected once; the Mitra integration is added once and holds as many calendars as the user likes.

## Information kept

- **Provider** — Mitra, CalDAV, Google Calendar, Apple Calendar, Calendar Subscription, Notion or Tempo
- **Connection details** — what identifies the account: a server URL and username, an Apple ID, a Google account, a feed address, a Notion workspace, or an Atlassian site and email
- **Secret** — the password, app-specific password, token or Google grant Mitra uses to reach the account, kept on the server and never shown again
- **Order** — its place among the user's integrations in the sidebar
- **Own addresses** — the user's email addresses at the provider, which make them the organizer of what they invite people to
