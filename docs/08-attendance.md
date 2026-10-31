# Attendance (sidebar label: "Classroom")

- Route(s): /attendance (class picker -> per-class "Classroom" page -> Mark Attendance dialog)
- Note: /classroom is a different, public family-portal page - the sidebar "Classroom" item
  links to /attendance.
- Roles that can see this: Manager (as observed)
- Screenshots: ../screenshots/attendance/class-picker.png

## Class picker - "Select Class / Choose the class for attendance"
- Two modes (top-right toggle): "All classes" (default) and "Step-by-step".
- All classes: every class as a card grouped under program headings with shift + time
  (e.g. "FULL TIME HIFZ - MORNING, 9:00 AM - 12:00 PM"), a "Search classes..." box and a
  "Filter by program" dropdown (All programs; the school's programs). Card content: field +
  section ("Field of study - A"), Level, student count ("1 student" / "0 students").
  Cards show NO attendance state - you cannot see from the picker whether a class was marked.
  (Search test: "Nazra" hides the Hifz group entirely.)
- Step-by-step: guided sequence - "Select Field of Study" (cards: Arabic, Field of study,
  Islamic Studies, Qur'an (Nazra); each field card has a three-dot "Edit field of study" menu)
  -> "Select Level" (Level 1-4 cards) -> lands directly on that class's Classroom page
  (no separate section step appeared for these single-section classes).

## Classroom page (one class)
- Heading "Classroom", teacher line, current date, buttons "Create Assignment" and
  "Mark Attendance". (Assignments live here - the only assignments surface found in the app.)
- Five summary cards: Total | Present | Absent | Late | Excused, plus "Unmarked students: N".
- Student cards (initials + name) and a right-hand "Select Date" month calendar.
- Teacher line: Hifz L1 A shows "Bilal Ahmed Khan" (the slice-3 assignment); Nazra L1 A shows
  "No teachers assigned to this section" even though a teacher was assigned to that section
  in Users - the two views disagree (see Notes).

## Mark Attendance dialog (full page)
- Header: class name, date, a "Learning Pathway" button, Close.
  (For the Nazra class the header showed "-" instead of the class name.)
- Exactly four statuses, as bulk "Mark all" buttons and per-student controls:
  Present | Absent | Late | Excused.
- Extra column "NO MATERIAL" with a per-student checkbox. Selecting Absent ticks AND disables
  it; selecting Late leaves it editable. (Material tracking is a Qur'an-school concept:
  the student did not bring / was not given lesson material.)
- "Unmarked only" toggle (default off). Date button (31/10/2026) opens a calendar popup to
  mark a different day. A student's name is a "View attendance history" button.
- THERE IS NO REASON OR NOTE FIELD - not for Absent, not for Late, not anywhere in the dialog
  (checked before marking and after selecting each status, in two classes). An absence reason
  ("Family commitment") and a late note ("Arrived 15 minutes late") from the walkthrough
  scenario could not be recorded. Schools needing absence reasons must track them elsewhere.
- "Save Attendance" is disabled until a status is chosen. Saving opens a confirmation:
  "Are you sure you want to save attendance for 1 student on October 31, 2026? This action
  will record the attendance permanently." (Cancel / Save Attendance) -> toast
  "Attendance saved successfully!".

## Marks recorded in this walkthrough (2026-10-31)
- Full Time Hifz, Field of study, Level 1, Section A: Yusuf Ahmed Siddiqui - LATE.
- Evening Nazra, Qur'an (Nazra), Level 1, Section A: Maryam Ahmed Siddiqui - ABSENT.
- Verified after reload: Hifz Total 1 / Late 1 / Unmarked 0; Nazra Total 1 / Absent 1 /
  Unmarked 0.

## Notes - bugs and quirks found
1. Marks ARE editable after saving (the dialog reopens with "Update Attendance" and all
   statuses clickable) despite the confirmation's "permanently" wording.
2. Classroom summary cards do not refresh when the dialog closes; they update only after a
   page reload.
3. Dashboard counters disagree with the modules: after slice 6 the dashboard showed
   TEACHERS 0 although Users lists two Active teachers, and STUDENTS 3 (it counts the
   orphaned duplicate Yusuf record - see flows/admit-siblings.md).
4. Dashboard "Attendance Today 0%" with 0 Present / 1 Late / 1 Absent: consistent with a
   present-only percentage; the formula is not stated anywhere in the UI.
5. The class picker never shows whether a class has been marked today.
6. Nazra marking-dialog header shows "-" instead of the class name.
