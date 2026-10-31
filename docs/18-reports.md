# Reports (system-attention inbox)

- Route(s): /tools/reports
- Roles that can see this: Manager (as observed)
- Screenshots: ../screenshots/reports/ (pending - batch 2)

## What it actually is
NOT a report generator. "Things the system noticed that may need your attention. Each links
to the place where it can be fixed." An exception inbox driven by configurable flag rules.
(Actual generated reporting lives in Student Analytics, docs/17-student-analytics.md.)

## Screen
- Severity filters: "All - 0", "Needs action - 0", "Attention - 0", "Notice - 0", and a
  "Show resolved / Hide resolved" toggle.
- Empty state: "Nothing needs your attention right now. Reports appear here as the system
  notices attendance and academic issues."
- "Settings 5" opens Report settings: "Choose what the system flags and how you're
  notified." Five rules, all ON by default (thresholds shown as displayed):
  ATTENDANCE - "Consecutive absences" (flag after 3 missed sessions in a row);
  "Attendance drops below" (flag under 70%); "Attendance not recorded" (flag classes with
  no attendance logged for a past day; no threshold); "Repeated lateness" (flag after
  4 late arrivals in a month).
  ACADEMICS - "Assignments unreviewed" (flag submissions waiting longer than 7 days).
- No rule fired during the walkthrough (Maryam's single absence is below the threshold of 3).
