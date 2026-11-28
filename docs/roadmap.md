# Public Product Roadmap

This roadmap tracks the major milestones for **Go Kart Championship Manager**.

---

## Pre-Launch Milestones (`v0.1.0` – `v0.7.x` · Pre-release / Unstable)

- [x] **`v0.1.0` — Angular Monorepo Foundation**: Isolated `user-app` and `platform-admin` apps with shared domain/data libraries, Tailwind CSS v4, Vitest, and Firebase Local Emulators.
- [x] **`v0.2.0` — Domain Engine & O(1) Security Rules**: Canonical TypeScript schema, drop-round scoring engine, kart draw generator, lap-time formatter, scoped roles, and automated rules tests.
- [x] **`v0.3.0` — Auth, Privacy & Organization Hub**: Email/Google sign-in, public privacy profiles, self-serve org creation, join requests, and private invite links.
- [x] **`v0.4.0` — Racing Operations Core**: Championships, scoring rules, events & RSVP opt-ins, race-night Quick Edit / Kart Draw / Paste Results, driver roster & link claims, and tracks.
- [x] **`v0.5.0` — Isolated Platform Admin Console**: Dedicated admin app for managing organizations, plan quotas, users, Global Track Catalog bulk import/export, and platform settings.
- [x] **`v0.6.0` — Arcade Paddock UI Redesign**: High-contrast dark motorsport aesthetic, public `/tracks` catalog, broadcast podium standings, and profile hub.
- [x] **`v0.7.x` — QA & Emulator Tooling**: Legacy account normalization, staging checks, and deterministic emulator seed tooling.

---

## `v1.0.0` — Public Stable Release

- [ ] End-to-end verification across every user role (`Guest`, `Driver`, `Steward`, `Co-Manager`, `Org Admin`, `Org Owner`, `Platform Admin`) and Spark quota boundary.
- [ ] Desktop & mobile responsive polish across `user-app` and `platform-admin`.
- [ ] Tag `v1.0.0` as the first **Stable (`Latest`)** release.

---

## Post-`v1.0.0` Roadmap

### `v1.1.0` — Social & Racing Polish
- Mutual Friends and Head-to-Head Rivalry views.
- Per-class points scoring and reverse-grid "Copy Grid from Session".
- Session timing sheet CSV export and RSVP waitlists / opt-in deadlines.
- Driver points progression charts.

### `v1.2.0+` — Venue Plans, Billing & Live Timing
- Optional Cloud Functions layer behind `shared-data` repositories:
  - Self-serve Pro / Venue subscription billing webhooks.
  - External timing & LiveTrack lap-time ingestion.
  - Enhanced white-label venue branding and cross-organization career statistics.
