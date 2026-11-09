# Method369 — Privacy Policy

**Effective Date:** 2026-05-17
**Last Updated:** 2026-11-08
**Version:** 1.2.0

Published by **Sudarshan Tech Labs** | https://sudarshantechlabs.com | sudarshantechlabs@gmail.com

---

Method369 is a daily manifestation app for Android. Everything you write stays on your device. Sudarshan Tech Labs operates no backend server, collects no personal data, and receives nothing from the App — not even crash reports.

The App contains no networking code at all. It does not request the `INTERNET` permission, so it is incapable of sending your data anywhere.

---

## Data Collection

### Data Stored Locally on Your Device

| Data | Purpose | Storage |
|---|---|---|
| Your intentions (free text) and their category | The text you write 3, 6 and 9 times a day | Room database on your device |
| Daily progress — which of the morning, afternoon and evening sessions you completed | Tracking your 33-day streak | Room database on your device |
| Session logs — session type, repetitions completed, completion timestamp | Progress history and statistics | Room database on your device |
| Reminder times and whether reminders are enabled | Scheduling your three daily notifications | Room database on your device |

**Nothing is collected by us.** There is no account, no sign-in, no identifier, no analytics and no advertising.

---

## How We Use Your Data

We do not use your data, because we never receive it. Everything the App stores is read only by the App, on your device, to show you your intentions, your progress and your reminders.

---

## Data Storage and Security

- **All data is stored locally** in a Room database inside the App's private directory
- **No transmission is possible:** the App declares no `INTERNET` permission and contains no HTTP client, no Firebase, and no analytics or crash-reporting SDK
- **Android sandbox:** the database sits in app-private storage, isolated from other apps by Android

## Data Retention

| Data | Retention |
|---|---|
| All local app data | Until you delete it or uninstall the App |

---

## Data Sharing

Nothing is shared. We do not sell user data, and your intentions never leave your device. There are no third-party SDKs in this App.

---

## Background Behaviour

Method369 schedules three daily reminder notifications using Android's WorkManager. This runs on your device only and sends nothing outward. After a device reboot, WorkManager re-registers those reminders so your notifications keep arriving — that is the sole purpose of the `RECEIVE_BOOT_COMPLETED` permission.

The App also provides a home-screen widget showing your current progress. It reads the same local database and makes no network calls.

---

## Permissions Explained

The App itself asks for two permissions:

| Permission | Why It Is Needed |
|---|---|
| `POST_NOTIFICATIONS` | Show your three daily reminder notifications |
| `RECEIVE_BOOT_COMPLETED` | Re-schedule your reminders after the device restarts |

### Permissions added by Android libraries

The finished app also carries permissions that the Android libraries it is built on declare for themselves. They appear in the app's permission list even though the App's own code never asks for them, so they are listed here for completeness:

| Permission | Comes from | What it does |
|---|---|---|
| `ACCESS_NETWORK_STATE` | WorkManager | Lets a library check whether a network exists. It does **not** grant network access, and without `INTERNET` nothing can be sent |
| `WAKE_LOCK` | WorkManager | Lets a scheduled reminder finish without the device sleeping mid-task |
| `FOREGROUND_SERVICE` | WorkManager | How Android runs scheduled background work |

So the App declares two permissions and the finished build requests five.

Three other permission names — `BIND_JOB_SERVICE`, `BIND_REMOTEVIEWS` and `DUMP` — also appear inside the merged manifest, but not as requests. They sit on the service and widget components that WorkManager and Glance contribute, as a requirement on anything trying to call those components. The App is not granted them and they do not appear in its permission list.

**`INTERNET` is absent from the finished app too.** Verified against the merged manifest, not just the App's own file — so the statement that the App cannot transmit your data holds for the shipped build.

---

## Your Rights and Controls

- **Turn reminders off:** in the App's settings
- **Delete all data:** uninstall the App, or go to Android Settings → Apps → Method369 → Storage → Clear Data

Because your data exists only on your device and we hold no copy, a data access or deletion request to us would return nothing — you already have the only copy, and clearing app data destroys it permanently.

---

## Children's Privacy

Method369 is not directed at children under 13. We collect no personal information from anyone.

---

## Changes to This Policy

We may update this Privacy Policy from time to time. We will notify you of significant changes via:

- In-app notification
- Updated policy date on this page

Continued use of Method369 after changes become effective constitutes your acceptance of the updated policy.

---

## Contact Us

For privacy questions:

- **Email:** sudarshantechlabs@gmail.com
- **Developer:** sunny.sudarshan@gmail.com
- **Website:** https://sudarshantechlabs.com
- **Response Time:** Within 48 hours

---

## Play Store Data Safety Summary

| Data type | Collected | Shared | Purpose |
|---|---|---|---|
| Personal info | No | No | — |
| Your intentions and progress | Local only, never collected | No | App functionality |
| Crash logs | No | No | — |
| Device or other IDs | No | No | — |

Declare **"No data collected"** in the Play Console data safety form. The App has no network capability, so there is no transfer to disclose.

---

## Recent Updates (Version 1.2.0 - November 8, 2026)

- **Rewrote the policy from the app's source.** The previous text described Firebase Analytics, Authentication, Firestore and Crashlytics collection, with retention tables. Method369 uses none of them: there is no Firebase dependency, no `google-services.json`, and no networking code at all.
- **Stated plainly that the app cannot transmit data.** It declares no `INTERNET` permission, verified against the merged manifest rather than the app's own file.
- **Removed scaffold sections** for location data, location sharing and account management, which did not apply to an app with no location and no account.
- **Listed the permissions Android libraries merge in** — `ACCESS_NETWORK_STATE`, `WAKE_LOCK` and `FOREGROUND_SERVICE`, all from WorkManager — since the Play Store shows the merged set, not just the two the app declares. The app declares two and the finished build requests five. An earlier draft of this section also listed `BIND_JOB_SERVICE`, `BIND_REMOTEVIEWS` and `DUMP` as permissions the app carries; they appear in the merged manifest only as requirements guarding WorkManager's and Glance's own components, never as requests, so they are not in the app's permission list and have been removed.
- **Gave the Play data safety answer directly:** no data collected.

---

## Recent Updates (Version 1.1.0 - May 17, 2026)

- **Aligned policy with the shared privacy-policy structure.**
- **Clarified local ritual data and notification permissions.**

---

**This privacy policy complies with:**
- Google Play Store requirements
- GDPR (General Data Protection Regulation)
- CCPA (California Consumer Privacy Act)

**Last reviewed:** 2026-11-08

---

This is the published policy, served at https://sudarshanchaudhari.github.io/method369-privacy-policy/ from the `main` branch of this repository. `index.html` carries the same content for the web and must be updated alongside this file. The copy in the [Method369 app repository](https://github.com/SUDARSHANCHAUDHARI/Method369/blob/main/PRIVACY_POLICY.md) is kept identical.
