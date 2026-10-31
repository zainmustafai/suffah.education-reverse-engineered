# Hours

- Route(s): /tools/hours (tabs: My timesheet, Approvals, School schedule, Analytics)
- Roles that can see this: Manager (as observed; the timesheet is personal - "Your own clock")
- Screenshots: ../screenshots/hours/ - my-timesheet.png, school-schedule.png, analytics.png.
  Print-layout captures (top of screen, no sidebar).

## What it does
Teacher time tracking: personal clock-in/out timesheet, an approvals queue for time entries,
the school's class schedule view, and hours analytics with PDF export.

## Screens

### My timesheet (default)
- Status cards: STATUS "Clocked out / 0h 00m / not started"; THIS MONTH "0h 00m"; AVG / DAY "0h 00m".
- Action: "Clock in" button.
- Week selector: Previous / Next; range label e.g. "Oct 26 - Nov 1, 2026", "5 days - 0h 00m";
  Start date and End date date inputs with pickers.
- Table: DAY | CLOCK IN | CLOCK OUT | TOTAL | STATUS | per-row edit ("Add hours for this day").
- Current week rows Mon Oct 26 - Fri Oct 30 all show "-" times and "Not started".
  No Saturday/Sunday rows rendered even though the range ends Nov 1, 2026.

### Approvals
- Empty state only: "No pending time approvals. You're all caught up."

### School schedule
- Program selector ("Full Time Hifz") with an "Edit in Programs" link.
- Shift card: "Morning shift", "Mon, Tue, Wed, Thu, Fri - 09:00 - 12:00", "0/20 enrolled",
  message "No classes scheduled in this shift." (Matches Programs > Scheduling: 4 classes
  not scheduled, teachers unassigned.)

### Analytics
| Field | Type | Notes |
| --- | --- | --- |
| Start date | Date input | Default 10/05/2026 |
| End date | Date input | Default 10/31/2026 |
| Teacher search | Text input | Placeholder "All teachers - search to pick specific ones" |

- Action: "Export PDF".
- Summary cards: HOURS WORKED "0h / of 0h scheduled"; AVG PER TEACHER / WEEK "0h";
  LATE CLOCK-INS "0"; TIME EDITS "0", "0 awaiting approval".
- Table: TEACHER | WORKED | SCHEDULED | OF SCHEDULE | AVG / WEEK | LATE | EDITS.
  Empty state: "No teachers to show."

## States
- Every tab is in a clean zero/empty state on this fresh account; approvals and analytics
  have friendly empty-state copy.

## Notes
- Hours is the dashboard's "Teacher Timesheet" Quick Action target.
- The timesheet week view silently drops weekend days from the rows while including them
  in the range label - worth rechecking once weekend classes exist.
