<div align="center">

# Pario

### Your week. Your pace.

A student planner that keeps your timetable, homework and grades close at hand — even offline.

**[Open Pario ↗](https://bsu-schedule-pwa.netlify.app)** · **[Русский](README.ru.md)** · **[Share an idea](https://github.com/AlexKweb/pario-student-planner-pwa/issues)**

PWA · Offline first · Designed for phones

</div>

## A clearer view of your student day

University timetables often live in a spreadsheet. Finding today's classes on a phone means opening the file, locating your group and checking the right row — again.

Pario turns that routine into a week you can scroll through. Open it from your Home Screen, see today's classes, and keep your own homework, notes and grades alongside the timetable.

## What you can do today

| A part of your day | What Pario does |
| --- | --- |
| **Find your next class** | The whole Monday–Saturday week, a today marker, automatic scrolling and a quick return to today. |
| **Know where you are in a lesson** | Elapsed lesson time with animated progress, plus a countdown to the next class. |
| **See your own timetable** | Group selection, one or both subgroups, distinct lecture and practice layouts. |
| **Keep track of coursework** | A subject diary for homework and notes, optional due dates, editing and completion. |
| **Record your progress** | Personal grades from 1 to 10 and a calculated average for each subject. |
| **Look ahead** | A month calendar with Belarusian holidays and weekends, an exam-session countdown, and winter/spring study plans. |
| **Make it comfortable** | Light, dark or system theme, compact cards and saved display preferences. |
| **Use it without a connection** | The app and timetable are cached after a successful online load. Personal entries stay on your device. |

## Add it to your iPhone

1. Open **[Pario in Safari](https://bsu-schedule-pwa.netlify.app)** while online.
2. Open **Share → Add to Home Screen** and confirm.
3. Launch the Home Screen icon. After the app has finished caching, the timetable is available offline.

The current app may still appear as **«Расписание»** in the installation dialog. Pario is the product name; unifying the in-app branding is listed as a future idea.

## Built around a fast first screen

The phone doesn't download a spreadsheet every time the app opens. A separate update pipeline parses and validates the timetable before it becomes part of the application build. A service worker caches the app and its data for later use.

- **Daily source checks:** scheduled for **22:00 Europe/Minsk (19:00 UTC)**. GitHub Actions may start later than the scheduled time.
- **Safe updates:** a failed download, validation or build leaves the previous published timetable in place.
- **Honest freshness:** the last successful source check is tracked separately from the source file's modification time.
- **Local personal data:** grades, homework, notes and preferences are stored on the device; Pario does not synchronize them to an account.

**Stack:** React · TypeScript · Vite · Workbox / PWA · Vitest · GitHub Actions · Netlify.

Read the **[architecture](docs/architecture.md)** and **[data & offline guide](docs/data-and-offline.md)** for decisions, safeguards and tradeoffs.

## Current scope

Pario currently serves **BSU, second-year Applied Mathematics, stream 2, groups 5–7**. Group 7 and both subgroups are selected by default. The interface is in Russian; these project documents are available in English and Russian.

The timetable currently covers the **third semester of 2026–2027**. The study plan includes winter and spring subjects. This is an independent student project, not an official university service. The university source remains authoritative for classes and changes.

An initial online load is required. Offline access uses the last cached version, and new timetable releases require a connection. Personal records are **local to this browser/device**: they do not follow you to another phone and can be lost if site data is cleared. Backup and sync are not available yet.

## Where Pario is going

The next planned navigation layout puts a dedicated **Planner** in the middle:

**Schedule · Study · Planner · Calendar · Settings**

The Planner's behavior is still being designed. The current app has four primary sections; the diary already lives inside Study.

**[Roadmap](ROADMAP.md)** · **[Changelog](CHANGELOG.md)**

## About this repository

This is Pario's public home for product documentation, screenshots, plans and feedback. **The application source code is maintained in a private repository and is not included here.** Cloning this repository does not install or build the app; use the live link above to try it.

Found a bug or have an idea? **[Open an issue](https://github.com/AlexKweb/pario-student-planner-pwa/issues)** — English and Russian are both welcome. Documentation corrections are welcome as pull requests.

If Pario is useful to you, a **star** helps others discover the project.
