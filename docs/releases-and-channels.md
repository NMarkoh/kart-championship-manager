# Releases & Stability Channels

Every version of **Go Kart Championship Manager** is published on **[GitHub Releases](https://github.com/NMarkoh/kart-championship-manager/releases)** with an explicit stability classification and a self-contained, scrubbed self-hosting bundle (`gkcm-<tag>-selfhost.zip` + `SHA256SUMS.txt`).

---

## Stability Channels

### 1. Stable (`Latest`)
- **Version format**: `v1.0.0`, `v1.0.1`, `v1.1.0`, … *(major version `>= 1` with no pre-release suffix)*
- **Release title**: `<tag> — Stable`
- **GitHub flag**: Marked as **Latest** (non-prerelease).
- **Recommended for**: Production karting leagues, venues, and clubs running active championships.

### 2. Pre-release (Unstable)
- **Version format**:
  - Pre-`1.0.0` releases (`v0.7.1`, `v0.8.0`, …), or
  - Any SemVer pre-release suffix (`v1.0.0-rc.1`, `v1.1.0-beta.2`, `v1.2.0-alpha.1`)
- **Release title**: `<tag> — Pre-release (Unstable)`
- **GitHub flag**: Marked as **Pre-release** so it never overrides the `Latest` stable release.
- **Recommended for**: Contributors, league organizers, and testers who want to try upcoming features early on local Firebase Emulators or a dedicated staging Firebase project.

> **Heads-up for Pre-release (Unstable) builds**: Unstable releases may introduce breaking changes to Firestore rules, indexes, or document fields before the next stable milestone. Always test unstable builds against local emulators or a non-production Firebase project first.

---

## Downloading & Trying Any Version

1. Go to **[Releases](https://github.com/NMarkoh/kart-championship-manager/releases)**.
2. Pick the **Latest** (Stable) release or scroll to any **Pre-release** (Unstable) tag you want to try.
3. Download `gkcm-<tag>-selfhost.zip` and follow **[Self-Hosting Guide](self-hosting.md)** to run it on local Firebase Emulators or deploy it to your own Firebase project.

---

## Upgrading Between Versions

1. Review the **[Changelog](../CHANGELOG.md)** for any Firestore rule, index, or schema notes between your current version and the target version.
2. Back up your Firestore data if upgrading across minor/major versions or testing a Pre-release build.
3. Re-apply your `.firebaserc`, web app config, and Super-Admin email to the new release archive, then run:
   ```bash
   npm ci
   npm run build
   npm test
   firebase deploy --only firestore:rules,firestore:indexes,hosting
   ```
