# Student Analytics and History

- Route(s): /tools/student-analytics
- Roles that can see this: Manager (as observed)
- Screenshots: ../screenshots/analytics/ (pending - batch 2)

## What it does
"Generate reports across a selected date range - attendance, grades, notes and more."
This is the product's real reporting engine (Reports, docs/18-reports.md, is not).

## Controls
- From / To dates (pre-filled 08/02/2026 - 10/31/2026 in the observed session).
- Report scope: "Individual student" (the only enabled option); "By field & level" DISABLED;
  "All students (3)" DISABLED.
- Student search box ("Search students by name or class") - there is no browsable student
  list; on selection, the student's class appears auto-selected and disabled
  ("Only class - selected automatically").
- "Include in report" toggles: Attendance, Grades, Notes (on by default); under "More":
  Assignments (off), Learning pathway progress (off).
- "Generate report" (disabled until a student is chosen); after generation, "Export PDF"
  and "Export CSV" appear (neither was run in this walkthrough).
- Empty state: "No report yet - Choose a student and a date range above, then generate a
  report to see attendance, grades and notes."

## Generated reports (2026-08-02 to 2026-10-31, "1 school day" each)
- Yusuf Ahmed Siddiqui (Hifz L1 A): AVERAGE GRADE - (none); NOTES LOGGED 0; ABSENCES 0.
  Grades: "No graded work in this range." Attendance table: Present 0, Late 1, Absent 0,
  ATTENDANCE RATE 100% - a Late day counts fully toward the rate (contrast the Dashboard's
  present-only 0%, docs/12-dashboard.md).
- Maryam Ahmed Siddiqui (Nazra L1 A): AVERAGE GRADE -; NOTES LOGGED 0; ABSENCES 1.
  Attendance: Present 0, Late 0, Absent 1, RATE 0%. Notes: none in range.
- With "Learning pathway progress" enabled for Maryam: "Learning pathway progress - Current
  step on each class pathway" - "None of these classes has a learning pathway yet."
