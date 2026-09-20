# Working on Pario's public repository

## Purpose and boundaries

This repository presents Pario, a student PWA. It contains public documentation,
screenshots, product plans and feedback templates. The application's source and
upstream schedule files belong to a separate private repository.

- Do not copy application source, source workbooks, generated timetable catalogs,
  credentials, deployment identifiers or private repository links into this repo.
- Personal grades, homework and notes must never be published. Use synthetic
  entries for demonstrations. Prefer captures that do not expose teacher names
  or unnecessary source data; do not assume a hide-names setting exists.
- Do not change the private application or deploy it as a side effect of editing
  these documents.
- Do not add an open-source license or badge that implies the app is open source.
- Do not claim Pario is an official university product or a registered trademark.

## Content structure

- `README.md`: English product overview and primary entry point.
- `README.ru.md`: equivalent Russian overview.
- `assets/`: real screenshots and presentation assets.
- `docs/`: architecture, data lifecycle and user guidance.
- `ROADMAP.md`: planned and exploratory work, clearly separated from shipped work.
- `CHANGELOG.md`: verified product, engineering and documentation changes;
  exclude routine automated source checks.
- `.github/ISSUE_TEMPLATE/`: concise bug and feature forms.

## Repository presentation settings

Recommended values for GitHub's About panel (these are repository settings, not
fields that GitHub automatically reads from this file):

- Description: `Offline-first student planner with schedules, homework, grades and an academic calendar.`
- Website: `https://bsu-schedule-pwa.netlify.app`
- Topics: `pwa`, `student-planner`, `offline-first`, `schedule`, `react`, `typescript`

Keep the repository public and the application source private. Do not change
repository visibility, rename repositories or add a license as part of updating
presentation settings. If the current integration cannot edit About, report that
limitation instead of claiming these settings were applied.

## Keep the public history current

The owner requires a public update for **every assistant-authored commit pushed
to the private application repository**. The private commit and its public
documentation follow-up are one task; this is a contributor workflow, not an
automated mirroring service.

1. Add a concise English and Russian entry to `CHANGELOG.md` after each private
   commit. Record the date, what changed and its practical effect. Append a new
   bullet or subsection under the date instead of replacing earlier history.
2. Include fixes, internal refactoring and maintenance. Label engineering work
   honestly; do not describe it as a new user-facing feature. Separate committed
   work from deployed behavior when publication has not yet been confirmed.
3. Bring both READMEs and relevant guides up to date when behavior, scope or
   architecture changes. Replace screenshots only when the interface changes.
4. Publish a curated explanation, never raw private diffs, commit messages or
   hashes, source files, private links or infrastructure identifiers. Keep the
   existing personal-data boundaries intact.
5. Save a focused public commit before reporting the private task complete or
   starting the next private change. If access fails, report the pending public
   update explicitly and complete it when access is restored.

Routine automated source-check commits are not separate product milestones and
remain excluded. Do not create another private commit just to acknowledge this
public follow-up, or trigger a deployment for documentation-only changes.

## Writing and evidence

1. Keep the two README versions aligned whenever behavior, scope or links change.
2. Verify claims against the current app or authorized source. Do not invent
   benchmarks, user counts, dates, test totals, synchronization or notifications.
3. Describe shipped behavior in the present tense; label proposed features.
4. The planned fifth navigation item, Planner, is not shipped yet.
5. Explain that offline use requires an initial online load and retained browser
   storage. Personal entries are local and currently have no backup or sync.
6. Daily source refresh is scheduled for 22:00 Europe/Minsk (19:00 UTC), not a
   guaranteed delivery time. Do not restore the old weekly-refresh description.
7. Prefer relative links for repository files and absolute HTTPS links for the app.
8. Technical documentation should explain decisions and tradeoffs without
   publishing implementation source or private infrastructure details.

## Visual assets

- Capture the real interface. Never fabricate UI screenshots or depict planned
  screens as already implemented.
- Use demo personal entries; document capture date, theme and relevant settings.
- Check every screenshot visually before publishing, including its edges.
- Keep file names lowercase and descriptive. Supply meaningful image alt text.
- A presentation cover may add framing around unchanged captures, but must not
  suggest a different application interface.

## Verification and commits

- Check Markdown links, local file references and image dimensions.
- Parse issue-template YAML and inspect its structure before committing.
- Review the staged file list and content for accidentally included private data.
- Inspect GitHub's rendered README after publication when browser access permits.
- Make small, focused commits as each useful part is ready; do not force-push.
- Preserve concurrent upstream changes by basing each commit on the current head.
- This docs-only repo has no application build or application test command. Do not
  add artificial tests or package dependencies just to create a status badge.
