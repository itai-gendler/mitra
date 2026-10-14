---
id: mitra
summary: A self-hosted calendar that puts events and tasks on one timeline, with a planning backlog, subtasks, dependencies, availability and reminders, synced both ways with CalDAV, Google, Apple, Notion and Tempo.
category: calendar
tags:
- calendar
- tasks
- planning
- caldav
- self-hosted
authors:
- name: a11delavar
  url: https://github.com/a11delavar
license: AGPL-3.0-only
languages:
- en
- de
- fr
- es
- pt
- it
- fa
limitations:
- 'Mitra never sends email itself: invitations, updates, cancellations and replies travel through the calendar server behind an entry''s calendar, and a Mitra calendar keeps its participants as a record only.'
- Out of the box a Mitra server is for one person and has no sign-in; with sign-in turned on, people sign in through an OpenID Connect provider, which alone decides who may sign in.
- Calendars stored in Mitra are opened only by Mitra; they are not published to other calendar apps.
- 'A calendar keeps only what its provider can store: Mitra hides the fields a calendar cannot hold and never fills them in silently.'
- 'Calendar subscriptions and calendars shared to view only are read-only: their entries are never created, changed, moved or deleted from Mitra.'
references:
- kind: doc
  role: intent
  target: README.md
  title: README
- kind: doc
  role: intent
  target: docs/README.md
  title: Getting started
- kind: doc
  role: intent
  target: docs/integrations/README.md
  title: Integrations
---

# Mitra

Mitra is a self-hosted calendar for events and tasks. Each user keeps calendars of their own: calendars stored in Mitra itself, and calendars of accounts they connect, which Mitra syncs both ways: CalDAV servers, Google Calendar, Apple Calendar, Notion task databases, Tempo worklogs, and read-only calendar subscriptions. Events, tasks and availability share one timeline in week, month, year, timeline and table views. Tasks carry a schedule and the constraints it has to respect, a due date and an estimate; unscheduled tasks wait in the Planning tab until they are dragged into the week. Entries can have subtasks, dependencies, participants and reminders, and reminders arrive as push notifications on every device the user allows.

## Intent

The project's own words: "Most tools make you choose between a calendar for your time and a to-do app for your tasks. Mitra puts both on one timeline, so you can see when there's actually room to get things done. It runs on your own server, keeps calendars itself if you like, and connects to the ones you already have." It is one small container with a database the operator owns, no telemetry, and sign-in for several people when they need it.
