# Go Kart Championship Manager

A cloud-native, multi-organization rental karting championship, race-night timing, and standings platform built with **Angular 19**, **TypeScript**, **Tailwind CSS v4**, and **Google Firebase**.

This public repository hosts **user & self-hosting documentation**, the **versioned changelog**, and **self-hostable release archives** (both **Stable** and **Pre-release / Unstable** builds) so anyone can download a release and run their own instance on their own Firebase project.

> **Looking for a release to run?** Visit the **[Releases](https://github.com/NMarkoh/kart-championship-manager/releases)** page to download either the latest **Stable** release or any **Pre-release (Unstable)** build.

---

## Highlights

- **Multi-Organization League Hub**: Public discovery, closed join requests, private invite links, and self-serve Organization creation with freemium plan/quota guardrails.
- **Championships, Series & Drop-Round Scoring**: Flexible scoring rules, per-session overrides, DNF fastest-lap rules, explicit penalties, countback tie-breakers, drop rounds, and CSV standings export.
- **Race-Night Operations**: Chronological session directory, Quick Edit results grid with live points preview, Kart Draw with saved default pools, Paste Results parser, and automatic track lap-record recomputation.
- **Driver Roster & Profile Linking**: Bulk driver import, soft-archiving, 1-to-1 driver claim/approval links, Teams, and Driver Profiles.
- **Tracks & Global Track Catalog**: Multi-layout venue tracks, per-layout/class lap records, and 1-click import from a shared circuit directory.
- **Isolated Admin Console**: Standalone `platform-admin` app on a separate Firebase Hosting target for managing organizations, plan quotas, users, global tracks, and platform banners.

---

## Stable vs. Unstable Releases

Every tagged version is published to **[GitHub Releases](https://github.com/NMarkoh/kart-championship-manager/releases)** with a clear stability status and a self-contained, privacy-scrubbed archive (`gkcm-<tag>-selfhost.zip` + `SHA256SUMS.txt`):

| Release Channel | Version Pattern | GitHub Badge | Who Should Use It |
| :--- | :--- | :--- | :--- |
| **Stable** | `v1.0.0+` (no suffix) | `Latest` | Leagues & clubs running production seasons |
| **Pre-release (Unstable)** | `v0.x.y`, `-alpha`, `-beta`, `-rc` | `Pre-release` | Testers & early adopters trying upcoming features on local emulators or a staging project |

All release archives have personal project IDs, API keys, and admin emails replaced with clean placeholders so your deployment connects **only** to your own Firebase project.

---

## Documentation

- **[Self-Hosting Guide](docs/self-hosting.md)** — Prerequisites, Firebase project setup, placeholder configuration, local emulator testing, and Firebase Hosting deployment.
- **[Releases & Channels](docs/releases-and-channels.md)** — How Stable and Pre-release (Unstable) versions are tagged, verified, and upgraded.
- **[Product Roadmap](docs/roadmap.md)** — Planned milestones from pre-launch (`v0.x`) through `v1.0.0` and post-launch features.
- **[Changelog](CHANGELOG.md)** — Version-by-version release notes with stability labels.

---

## Feedback & Issues

Found a bug or want to suggest an improvement? Open an issue using the **[Issue Tracker](https://github.com/NMarkoh/kart-championship-manager/issues/new/choose)** and let us know whether you are running a **Stable** or **Pre-release (Unstable)** version.

---

## License

Copyright (C) 2026 NMarkoh.

Licensed under the **[GNU Affero General Public License v3.0 (AGPL-3.0)](LICENSE)** — free to download, self-host, and modify under the terms of the AGPLv3.
