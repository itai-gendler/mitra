---
scope: The Mitra server and web app under src/, with the app manifest that registers calendar files and links.
method: Static inspection of source and the project's English documentation at the pinned commit; nothing was run.
covered:
- description: Entries, planning, repeats, relationships, participants, availability and reminders.
  paths:
  - src/features/entries/
  - src/features/planning/
  - src/features/recurrence/
  - src/features/relations/
  - src/features/participants/
  - src/features/availability/
  - src/features/reminders/
  - src/features/routines/
- description: Calendars, moving and copying entries, and calendar file import.
  paths:
  - src/features/sources/
  - src/features/migration/
- description: Views, time zones, search and the command palette.
  paths:
  - src/features/calendar/
  - src/features/time/
  - src/features/commands/Command.ts
  - src/features/commands/KeyPress.ts
  - src/features/commands/termsMatch.ts
  - src/features/commands/client/CommandPalette.ts
- description: Sign-in, sessions, the user record and their settings.
  paths:
  - src/features/identity/
  - src/features/settings/
  - src/app/ThemeSetting.ts
  - src/app/settings.ts
  - src/infrastructure/i18n/LanguageSetting.ts
  - src/infrastructure/i18n/AppLocale.ts
  - src/infrastructure/i18n/RegionPreview.ts
- description: Location suggestions.
  paths:
  - src/features/locations/
- description: Provider integrations, their sync engines, import and pacing.
  paths:
  - src/integrations/Integration.ts
  - src/integrations/registerIntegrations.ts
  - src/integrations/apple/
  - src/integrations/caldav/
  - src/integrations/google/
  - src/integrations/ics/
  - src/integrations/mitra/
  - src/integrations/notion/
  - src/integrations/tempo/
  - src/integrations/server/
  - src/integrations/client/
- description: App shell, sidebar, server routes, launch handling, service worker and app manifest.
  paths:
  - src/app/Mitra.ts
  - src/app/Sidebar.ts
  - src/app/server.ts
  - src/app/launch.ts
  - src/app/serviceWorker.ts
  - src/app/pwa.ts
  - src/app/client.ts
  - src/app/commands.ts
  - scripts/indexHtml.ts
exclusions:
- description: User documentation, the website and release notes.
  paths:
  - docs/
  - website/
  - releases/
  - README.md
- description: Images, icons and screenshots.
  paths:
  - assets/
- description: The design library of controls and styling fragments.
  paths:
  - src/design/
  - src/app/fonts.css
- description: Database, HTTP, logging, model, realtime and routing plumbing.
  paths:
  - src/infrastructure/database/
  - src/infrastructure/http/
  - src/infrastructure/logging/
  - src/infrastructure/model/
  - src/infrastructure/realtime/
  - src/infrastructure/routing/
  - src/infrastructure/environment.ts
  - src/mitra.d.ts
- description: Translation dictionaries and their wiring.
  paths:
  - src/infrastructure/i18n/de.json
  - src/infrastructure/i18n/en.json
  - src/infrastructure/i18n/es.json
  - src/infrastructure/i18n/fa.json
  - src/infrastructure/i18n/fr.json
  - src/infrastructure/i18n/it.json
  - src/infrastructure/i18n/pt.json
  - src/infrastructure/i18n/dictionaries.ts
  - src/infrastructure/i18n/index.ts
  - src/infrastructure/i18n/keys.auto-generated.ts
- description: Build, release, capture, CI and repository tooling.
  paths:
  - scripts/build.ts
  - scripts/capture-release.ts
  - scripts/capture.ts
  - scripts/changelog.ts
  - scripts/db.ts
  - scripts/dev.ts
  - scripts/esbuild.ts
  - scripts/film.ts
  - scripts/goldenZones.ts
  - scripts/i18n.ts
  - scripts/injectRandomUUIDPolyfill.ts
  - scripts/injectTemporalPolyfill.ts
  - scripts/precompress.ts
  - scripts/release.ts
  - scripts/releaseAssets.ts
  - scripts/releaseBody.ts
  - scripts/scenes.ts
  - scripts/screenshots.ts
  - scripts/test.ts
  - .github/
  - .claude/
  - Dockerfile
  - compose.yaml
  - package.json
  - package-lock.json
  - tsconfig.json
  - eslint.config.mjs
  - cliff.toml
  - .dockerignore
  - .gitignore
  - .nvmrc
  - data/
  - AGENTS.md
  - LICENSE
unmapped:
- description: 'Update check, About dialog and What''s New: a server check against GitHub and release notes, peripheral to planning.'
  paths:
  - src/features/about/
- description: Demo mode, with a sandbox per visitor and the sample calendar, which runs the project's public demo.
  paths:
  - src/integrations/demo/
  - src/features/identity/server/Sandbox.ts
- description: The first-run welcome dialog.
  paths:
  - src/features/onboarding/
- description: The keyboard shortcuts list and app-level commands such as Copy version.
  paths:
  - src/features/commands/client/DialogKeyboardShortcuts.ts
  - src/features/commands/client/appCommands.ts
limitations: []
---

# Coverage
