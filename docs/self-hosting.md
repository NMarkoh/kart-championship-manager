# Self-Hosting Guide

This guide walks you through downloading any **Stable** or **Pre-release (Unstable)** archive of **Go Kart Championship Manager** and running it locally or deploying it to your own **Firebase Spark (free tier)** project.

Every release archive is scrubbed of personal keys, project IDs, and account details so your deployment connects **exclusively** to your own Firebase project.

---

## Prerequisites

- **Node.js 22+** and `npm`
- **Firebase CLI** (`npm install -g firebase-tools`)
- **Java (JDK 17+)** *(required for running Firebase Local Emulators)*
- A **Google Firebase** project with **Authentication** (Email/Password and/or Google) and **Cloud Firestore** enabled

---

## Step 1 — Download a Release Archive

1. Open the **[Releases](https://github.com/NMarkoh/kart-championship-manager/releases)** page.
2. Choose either:
   - The **`Latest` (Stable)** release for production league use, or
   - Any **`Pre-release` (Unstable)** release to test upcoming changes.
3. Download `gkcm-<tag>-selfhost.zip` and `SHA256SUMS.txt` from the **Assets** section.
4. *(Optional)* Verify the archive checksum before extracting:
   ```bash
   sha256sum -c SHA256SUMS.txt
   ```
5. Extract the archive and enter the extracted directory:
   ```bash
   unzip gkcm-<tag>-selfhost.zip -d gkcm
   cd gkcm
   ```

---

## Step 2 — Configure Your Own Firebase Project

Replace the clean placeholders in these **four files** with values from your Firebase Console (**Project Settings → Your apps → Web app**):

1. **`.firebaserc`** — Set your Firebase project ID and hosting site IDs:
   - Replace every `YOUR_FIREBASE_PROJECT_ID` with your own Firebase project ID (create a second Hosting site in Firebase Console if you want to deploy `platform-admin` separately).
2. **`projects/shared-data/src/lib/firebase.config.ts`** — Fill in your Firebase Web App credentials:
   - `YOUR_FIREBASE_API_KEY`
   - `YOUR_FIREBASE_PROJECT_ID`
   - `YOUR_MESSAGING_SENDER_ID`
   - `YOUR_FIREBASE_APP_ID`
   - `YOUR_MEASUREMENT_ID` *(optional)*
3. **`projects/shared-types/src/lib/roles.types.ts`** — Set `PLATFORM_ADMIN_EMAILS`:
   - Replace the placeholder admin email with `YOUR_ADMIN_EMAIL` (must be a verified email on the Firebase Auth account you use for `platform-admin`).
4. **`firestore.rules`** — Keep the Super-Admin check in sync:
   - Replace the placeholder admin email on the `isPlatformAdmin()` rule with the exact same `YOUR_ADMIN_EMAIL`.

---

## Step 3 — Install & Test Locally with Firebase Emulators

```bash
npm ci
npm run build
npm test
```

Start the Firebase Local Emulators (`auth`, `firestore`, `hosting`) in one terminal:

```bash
npm run emulators
```

In a second terminal, optionally seed deterministic demo data and launch the apps:

```bash
npm run seed:emulators   # Optional: creates sample emulator users and championship data
npm start                # User App at http://localhost:4200
npm run start:admin      # Platform Admin Console at http://localhost:4201
```

To verify Firestore security rules against the local emulator:

```bash
firebase emulators:exec --only firestore "npm run test:rules"
```

---

## Step 4 — Deploy to Your Firebase Project

Once local testing looks good:

```bash
firebase login
firebase deploy --only firestore:rules,firestore:indexes
npm run build
firebase deploy --only hosting
```

> **Tip**: Keep `platform-admin` on its own separate Firebase Hosting site target (as configured in `firebase.json`) so admin code is never shipped to regular league users.
