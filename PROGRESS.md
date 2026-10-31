# Progress

Status key: [ ] not started · [~] in progress · [x] done

## Setup
- [x] Repo created on GitHub (public, by owner choice)
- [x] Sign in and map navigation/modules (2026-10-31, see docs/00-overview.md)

## Blockers
- None for pushes: pushes go through the Muse GitHub App connector (snapshot pushes, small
  commits). The fine-grained PAT still cannot write to this repo (403) and is not used.

## Screenshots
- First batch exported 2026-10-31 (12 files, 7 web-upload commits): dashboard, school-settings
  (school-info.png redacted), programs, hours, tools hub, announcements, subscription.
- Captures are print-layout (top of screen, no sidebar) - the only file-export route from the
  browser. Users-module captures still pending.

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
- [ ] To be filled as flows are documented (see docs/01-use-cases.md for the scenario plan).
