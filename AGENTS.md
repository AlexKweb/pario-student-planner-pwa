# Working on Pario's public repository

## Purpose and boundaries

This repository presents Pario, a student PWA. It contains public documentation,
screenshots, product plans and feedback templates. The application's source and
upstream schedule files belong to a separate private repository.

- Do not copy application source, source workbooks, generated timetable catalogs,
  credentials, deployment identifiers or private repository links into this repo.
- Personal grades, homework and notes must never be published. Use synthetic
  entries for demonstrations, and use display preferences to hide teacher names.
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
- `CHANGELOG.md`: verified, user-facing changes; exclude routine source checks.
- `.github/ISSUE_TEMPLATE/`: concise bug and feature forms.

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
