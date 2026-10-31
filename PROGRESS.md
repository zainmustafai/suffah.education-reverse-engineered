# Progress

Walkthrough status: COMPLETE - 2026-10-31 (all 22 modules documented, 4 flows run, 30 screenshots in repo).

Status key: [ ] not started · [~] in progress · [x] done

## Setup
- [x] Repo created on GitHub (public, by owner choice)
- [x] Sign in and map navigation/modules (2026-10-31, see docs/00-overview.md)

## Blockers
- None for pushes: pushes go through the Muse GitHub App connector (snapshot pushes, small
  commits). The fine-grained PAT still cannot write to this repo (403) and is not used.

## Screenshots
- Batch 1 (12 files): dashboard, school-settings (school-info.png redacted), programs, hours,
  tools hub, announcements, subscription.
- Batch 2 (18 files, 2026-10-31): users (list + profile redacted), families, admissions,
  finance, attendance, chat, school-page, learning-pathway, analytics, reports, activity-log,
  backups, in-development. All 30 screenshots are in the repo.
- Captures are print-layout renders of the desktop pages (top of page, no sidebar) - the only
  file-export route from the browser; exact 1920x1080 viewport capture was not achievable.

## Modules - deep walkthrough (docs + flow + FHD desktop screenshots each)
- [x] Dashboard (/dashboard)
- [x] Announcements (/announcements) - composer documented; in-app-only test announcement sits PENDING APPROVAL
- [x] Chat (/chat) - read-only documentation; nothing sent
- [x] Classroom / Attendance (/attendance) - Yusuf LATE, Maryam ABSENT on 2026-10-31; no reason/note field exists
- [x] Subscription (/subscription) - tiers documented; Pay never clicked
- [x] School Settings (/school-settings)
- [x] Programs (/tools/programs) - list, locked detail, and full create wizard (flows/create-program.md); created: Evening Nazra & Islamic Studies
- [x] Admissions (/tools/registration)
- [x] School Page (/tools/school-page) - plus the public home and news pages
- [x] Hours (/tools/hours)
- [x] Users (/users) - plus flows/register-user.md; created 2 teachers
- [x] Families (/tools/families) - plus flows/admit-siblings.md; Siddiqui family created (see the incident note in the flow)
- [x] Special Care (/users?role=Student&specialCare=1) - documented inside docs/05-users.md
- [x] Finance (/tools/finance) - Stripe-gated shell pre-connection; partial payments impossible (see docs/09-finance.md)
- [x] Learning Pathway (/tools/learning-pathway)
- [x] Course Tool (/tools/course) - in-development stub - in development
- [x] Interactive Qur'an (/tools/interactive-quran) - redirects to a working /quran browser - in development
- [x] Student Analytics and History (/tools/student-analytics) - reports generated for both students
- [x] Reports (/tools/reports) - it is an exception inbox, not a generator
- [x] Activity Log (/tools/activity) - coverage gaps documented
- [x] Backups (/tools/backups) - existing backup cannot be downloaded or restored
- [x] Profile (/profile) - documented inside docs/05-users.md

## Flows
- [x] flows/create-program.md - Evening Nazra & Islamic Studies created end to end
- [x] flows/register-user.md - two teachers registered via the collection flow
- [x] flows/admit-siblings.md - Siddiqui family: 1 guardian, 2 siblings, sibling discount traced
- [x] flows/record-fees.md - $75 charge added; partial payment proven impossible
- Scenario-plan items that could not run because the product lacks the feature: exams/report
  cards (no such module), timetable clash + leave substitution (no timetable module; class
  scheduling lives inside Programs), parent-message replies (Chat documented read-only).
