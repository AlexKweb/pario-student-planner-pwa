# Changelog / История изменений

Product improvements, fixes, engineering work and documentation updates.
Each assistant-authored application commit receives a curated public note.
Routine automated timetable checks are not releases and are not listed here.

Здесь отмечаются новые возможности, исправления, рефакторинг и обновления
документации. Каждый коммит ассистента в приложении сопровождается краткой
публичной записью. Ежедневные автоматические проверки расписания не считаются
отдельными релизами.

## 2026-09-20 — Project history / История проекта

- Established a paired-commit workflow: every assistant-authored application
  commit must be followed by a public change note before the task is complete.
- Brought the architecture and offline guides up to date and added the verified
  application changes from September 19 below. This is a documentation update;
  it does not introduce an automatic publishing service.

Закреплено правило: каждый коммит ассистента в приложении сопровождается
обновлением публичного журнала до завершения задачи. Обновлены описания
архитектуры и офлайн-режима, ниже добавлены проверенные изменения от 19 сентября.
Это изменение процесса ведения документации; отдельная автоматическая
синхронизация репозиториев не добавлялась.

## 2026-09-19 — Reliability and refactoring / Надёжность и рефакторинг

### Changes

- **Dates and record limits:** centralized calendar-date validation and diary
  ordering. New records are rejected at capacity instead of silently removing
  older grades or diary entries.
- **Local saving:** shared persistence now confirms edits only after a successful
  write. Failed saves retain diary drafts, and failed reads do not overwrite
  unseen stored records with empty defaults.
- **Navigation and app updates:** unified browser history for the main sections
  and Study views. Failed update checks can retry sooner, without overlapping
  requests; the lesson clock pauses while the page is hidden.
- **Timetable preparation:** separated workbook traversal, time validation and
  subgroup handling. Added synthetic-workbook regression coverage for merged
  cells, reordered groups and incomplete source data.
- **Homework deadlines:** creation and editing now save the date submitted by
  the native date input. Verified that deadlines remain after reloading.

### Изменения

- **Даты и лимиты записей:** проверка календарных дат и сортировка дневника
  вынесены в общие модули. При достижении лимита новые записи не добавляются,
  а старые оценки и записи дневника сохраняются.
- **Локальное сохранение:** изменение подтверждается только после успешной
  записи. При ошибке сохранения черновик ДЗ остаётся в форме, а ошибка чтения
  не приводит к перезаписи хранилища пустыми данными.
- **Навигация и обновления:** объединена работа браузерной истории основных
  разделов и вкладок «Учёбы». После сбоя проверка обновлений повторяется раньше,
  без параллельных запросов; часы пары приостанавливаются на скрытой странице.
- **Подготовка расписания:** разделены обход таблицы, проверка времени и обработка
  подгрупп. Добавлены проверки на искусственной таблице с объединёнными ячейками,
  переставленными группами и неполными данными.
- **Сроки ДЗ:** создание и редактирование записи сохраняют дату, переданную полем
  выбора срока. Сохранность даты после перезагрузки проверена в браузере.

These application changes were published. Type checks, lint, regression tests
and the production build passed. Browser checks covered persistent grades,
homework creation and editing, and back/forward navigation.

Изменения опубликованы в приложении. Проверки типов, стиля кода, тесты и сборка
прошли успешно. В браузере проверены сохранение оценок, создание и редактирование
ДЗ, переходы «назад/вперёд».

## 2026-09-18 — Public project page / Публичная страница проекта

- Established Pario's public product repository with English and Russian READMEs.
- Documented architecture, offline behavior, daily updates and current limitations.
- Added a roadmap that distinguishes the planned Planner from shipped features.
- Added structured bug-report and feature-request forms.
- Added the owner's iPhone screenshot and live captures with demo diary/grade data.
- Added an About section in the app settings with AlexKweb and a link to this
  public repository.

Публичный репозиторий получил описание на двух языках, техническую документацию,
планы развития, формы обратной связи и галерею настоящих скриншотов. В настройках
приложения появились упоминание AlexKweb и ссылка на публичный репозиторий.
Код приложения остаётся приватным.

### Current application snapshot / Текущее состояние приложения

The app already includes the weekly timetable, live lesson status, settings,
academic calendar, study-plan table, personal grades and subject diary. This entry
records what is available at the public launch; it does not assign new release
dates to features delivered earlier.

На момент оформления репозитория уже доступны расписание, статус пары, настройки,
календарь, таблица учебного плана, оценки и дневник. Эта запись фиксирует текущее
состояние и не меняет даты появления уже существовавших функций.
