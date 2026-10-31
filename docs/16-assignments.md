# Assignments (inside Classroom)

- Entry: /attendance -> a class -> Classroom page -> "Create Assignment"
- Roles that can see this: Manager (as observed)
- Screenshots: ../screenshots/attendance/ (pending - batch 2)
- Outcome of the walkthrough attempt: NOT CREATED - the wizard's recipient step is broken
  (see "The blocker" below). Field documentation is complete for steps 1-4 of 6.

## The wizard (6 steps, side sheet with Fullscreen / Close)
An "Assignment History" footer sits under the wizard ("No assignments created yet.").

Step 1 - Choose Assignment Type:
- "Quran - Simple standardized inputs for Quran assignment."
- "Custom - Flexible assignment details for any subject."

Step 2 - Schedule & Submission:
- Custom path: Submission Type (Text default; File Upload; External Link; In Person),
  Description (optional), Due Date (optional, date picker; displays DD/MM/YYYY),
  Due Time (optional), "Allow late submission - Students can submit after the due date."
  switch (off).
- Quran path: adds a Material combobox (default "Quran"); Submission Type defaults to
  "Read" with options Read / Memorize / Review; the rest identical.

Step 3 - Custom Assignment Details: Title (required - the only field on the step).

Step 4 - Grading Options: "Max score" checkbox (checked) with a Max Score spinbutton
(default 10); "Pass/Not yet" checkbox (unchecked).

Step 5 - Recipients: "Search students..." box, "Select all visible" checkbox.
Step 6: never reached (see below).

## The blocker (product bug, verified 2026-10-31)
At Step 5 the wizard sat on "Please wait while we load class details..." with
"0 recipient(s) selected"; Next refused with the toast "No students found for selected
class/section" - for a class whose Classroom roster visibly contains a student
(Yusuf Ahmed Siddiqui, Hifz Level 1 A). The intended assignment ("Surah Al-Fatiha revision",
due 7 November 2026, description entered, default grading) could not be created.
Assignments are therefore effectively unusable for this class in the observed build.

## Related inconsistency
The Classroom page's teacher line is unstable: entering Hifz L1 A during slice 6 showed
teacher "Bilal Ahmed Khan"; entering the same class during the sweep showed "No teachers
assigned to this section" (the line slice 6 saw on the Nazra class instead). Treat teacher
display on the Classroom page as unreliable.
