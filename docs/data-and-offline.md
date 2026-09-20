# Data, updates and offline use

[English overview](../README.md) · [Обзор на русском](../README.ru.md) · [Architecture](architecture.md)

## What is stored where

| Data | Where it lives | What users should expect |
| --- | --- | --- |
| University timetable | Validated snapshot bundled in each app release | Everyone on the same release gets that snapshot |
| Study plan and calendar rules | Bundled application data | Available offline, maintained with app releases |
| App shell and assets | Browser service-worker cache | Available offline after a successful online load and caching |
| Group, subgroup, theme and display preferences | Local browser storage | Remembered in the same browser/app storage context |
| Personal grades | Separate versioned local storage | No account synchronization or cloud backup |
| Homework and notes | Separate versioned local storage | No upload to the university source or the project repository |

Local storage is not an account or a backup. A different phone, browser, or storage
context may have a different set of entries. Clearing site data or browser storage
eviction can remove personal records. Keep important information elsewhere until
a backup/export feature is actually available.

Edits are confirmed only after local storage accepts them. A failed save leaves
the existing record intact and retains a diary draft in its form for retrying.
An unreadable store or an unsupported record format is not treated as an empty
store to overwrite. At the record limit, the app asks users to remove an unneeded
entry before adding another; it does not automatically discard older records.

## Two different update mechanisms

### 1. Checking the university source

A GitHub Actions workflow is scheduled **every day at 19:00 UTC, which is 22:00 in
Europe/Minsk**. Scheduled jobs can run late; this is not a promise that every phone
receives fresh data at exactly 22:00.

The workflow downloads the source, parses all supported groups, validates the
generated catalog and runs the application's quality checks. It commits a
successful check, and the site is rebuilt from the resulting data. Failures leave
the previous published release available.

The metadata keeps two meanings separate:

- **Last checked:** when the source was last successfully verified by the pipeline.
- **Source modified:** when the upstream file reports that it was last changed.

An unchanged file can still have been checked today. A failed check must not make
old data look newly verified. The displayed timestamp belongs to the app release
currently loaded on the device.

### 2. Receiving an app release

The PWA caches the application and its bundled timetable. It checks for a new
service-worker version during normal use and when returning to the app, subject
to network availability and page visibility. Successful checks are throttled to
one per hour. After a failed check, another attempt is allowed after one minute;
requests do not overlap. The app is configured to activate updates automatically.

This does **not** mean iOS wakes a closed app every day at 22:00. The server-side
source check and the phone's receipt of a release are separate events. A phone
that remains offline continues using its cached release.

## Common situations

| Situation | Expected behavior |
| --- | --- |
| First visit, online | App assets and the bundled timetable load; caching is established |
| First visit, offline | There is no cached app to load |
| Returning offline, with cache retained | The last cached timetable, study data and local personal entries remain available |
| Source cannot be downloaded or parsed | The pipeline does not replace the working published data |
| A release exists, but the phone is offline | The phone keeps its previous release until it can update |
| A local save fails | Existing saved records remain; the diary draft stays in the form and an error is shown |
| A record limit is reached | The app rejects a new entry until space is made, without silently deleting older records |
| The source-check date looks old | Reconnect, reopen the app and allow the update check; a pipeline failure may also explain an old date |
| Site data is cleared | Cached app data and local personal records may be removed |

Do not clear site data as a routine troubleshooting step if you have grades or
diary entries you want to keep. There is currently no built-in way to restore them.

## Current limits

- The timetable is for a specific BSU course, stream and set of groups, not every
  university or arbitrary calendar import.
- Grades are self-entered records, not university-certified results.
- The timetable and calendar may contain source or interpretation errors. For an
  important change, check the university's official information.
- Personal-data synchronization, export, accounts, push reminders and a dedicated
  Planner section are not current features.

See [the roadmap](../ROADMAP.md) for the distinction between agreed work and ideas.
