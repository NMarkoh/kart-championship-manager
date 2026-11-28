# Changelog

All notable releases of **Go Kart Championship Manager** are documented here.
Versions marked **(Pre-release / Unstable)** are pre-`1.0.0` or pre-release snapshots intended for testing; versions marked **(Stable)** are production-ready releases.

---

## [v0.7.2] - 2026-11-28 (Pre-release / Unstable)

### Fixed
- **Platform Admin Sign-In Diagnostics & Recovery**: Added explicit `auth/unauthorized-domain`, `auth/operation-not-allowed`, and `auth/cancelled-popup-request` error messages, single-flight account hydration during Google OAuth, and profile-error + verification-email resend/refresh controls in the Platform Admin sign-in gate.
- **Global Track Import & Sync Reliability**: Added defensive Global Track normalization (`normalizeGlobalTrackDoc`, `buildOrgTrackFromGlobal`, `normalizeDefaultKartPool`) with guaranteed layout fallbacks, Firestore rules length caps (`defaultKartPool <= 60`), and safe `stats.trackCount` updates when importing or syncing catalog circuits into an organization.

---

## [v0.7.1] - 2026-11-27 (Pre-release / Unstable)

### Fixed
- Normalized legacy user documents during authentication hydration so existing accounts load profile and organization memberships cleanly.
- Refined Firestore security rules for self-upgrade account flows.
- Updated Organization Hub version indicator and status polish.

---

## [v0.7.0] - 2026-11-26 (Pre-release / Unstable)

### Added
- End-to-end QA fixes across race-night workflows, driver link claims, and organization settings.
- Local Firebase Emulator seeding tooling (`npm run seed:emulators`) with deterministic test accounts and sample racing data.

---

## [v0.6.0] - 2026-11-26 (Pre-release / Unstable)

### Added
- **Arcade Paddock UI Redesign**: High-contrast dark motorsport theme with chamfered headers, checkered accents, broadcast podium cards (`P1`–`P3`), and zebra-striped standings tables.
- Public `/tracks` Global Track Directory with `All / Outdoor / Indoor` filtering and circuit spotlight cards.
- Tabbed Account / Profile Hub with career stats (`WINS | POLES | PODIUMS | FL`) and upcoming races overview.

---

## [v0.5.0] - 2026-11-25 (Pre-release / Unstable)

### Added
- Isolated **Platform Admin Console** (`platform-admin`) on a dedicated hosting target with verified Super-Admin guard.
- Organization plan and quota management (`free`, `pro`, `venue` presets and custom limits).
- Global Track Catalog CRUD editor with multi-layout support and CSV/JSON bulk import/export.
- Global theme accent and announcement banner settings.

---

## [v0.4.0] - 2026-11-24 (Pre-release / Unstable)

### Added
- **Racing Operations Core**: Championship CRUD, optional Series grouping, scoring rules editor, and drop-round standings with CSV export.
- Events directory with structured dates and driver RSVP opt-ins.
- Race-night sessions: Quick Edit results grid with live points preview, Kart Draw generator, Paste Results parser, and automatic lap-record recomputation.
- Driver Roster with bulk add, soft-archive, Teams, and 1-to-1 driver claim links.

---

## [v0.3.0] - 2026-11-23 (Pre-release / Unstable)

### Added
- Firebase Auth & Firestore repository layer strictly isolated inside `projects/shared-data`.
- Email/Password and Google sign-in flows with racing username and privacy controls.
- Self-serve Organization Hub supporting public discovery, join requests, private invite links, and scoped staff roles.

---

## [v0.2.0] - 2026-11-22 (Pre-release / Unstable)

### Added
- Canonical domain-split TypeScript contracts (`projects/shared-types`).
- Pure motorsport domain engine (`projects/shared-domain`): standings with drop rounds, tie-breakers, DNF fastest-lap rules, kart draw, lap-time parser, and permissions matrix.
- O(1) Firestore security rules (`firestore.rules`), composite indexes, and automated emulator rules test suite.

---

## [v0.1.0] - 2026-11-21 (Pre-release / Unstable)

### Added
- Initial Angular 19 multi-project monorepo (`user-app`, `platform-admin`, `shared-types`, `shared-domain`, `shared-data`), Tailwind CSS v4, Vitest, and Firebase Local Emulators setup.
