# Flow: Admit siblings under one guardian (Family wizard + class enrolment)

- Entry: Families (/tools/families) -> "New family"; class placement afterwards in
  Users -> Edit User -> Manage Enrollments
- Ran on: 2026-10-31 - see CREATED_RECORDS.md for every record
- Screenshots: ../screenshots/families/ (pending - batch 2)

## Steps
1. Guardian: First name "Ahmed Raza", Last name "Siddiqui" (the wizard splits first/last name),
   Relation Father, calling code Pakistan (+92), phone 300 5550117,
   email ahmed.siddiqui@example.org. The scenario's street address could NOT be entered -
   the wizard has no address field.
2. Co-guardians: skipped (optional step).
3. Students: Yusuf Ahmed Siddiqui (DOB Jun 14, 2015; shown "Grade 1 - Male - age 11") and
   Maryam Ahmed Siddiqui (DOB Mar 02, 2017; "Grade 1 - Female - age 9"). Grade was not part of
   the scenario; the product default Grade 1 was left for both. Allergies / medical notes /
   special care left blank (not required).
4. Programs: Yusuf -> Full Time Hifz, shift Morning 09:00-12:00. Maryam -> Evening Nazra &
   Islamic Studies, shift Evening 17:00-19:00, badged "2nd child - sibling discount 10% off".
   No Level/Section is chosen in the wizard.
5. Costs: Yusuf $0/mo; Maryam "2nd child - 10% off" $0/mo; "One-time registration $75";
   further discount left at No.
6. Review -> "Create family". Toast: "Family created: Ahmed Raza Siddiqui". The parent account
   is created with a generated password emailed with the sign-in link (email only - no SMS
   anywhere in this flow). Guardian username: ahmedsiddiqui, role Parent, no School ID
   (School IDs appear only on student records). Family: "Siddiqui family - 2 students -
   1 guardian", Cycle Monthly, Status Due, Auto pay On.
7. Class enrolment (the wizard does not do this): Users -> Edit User -> Manage Enrollments ->
   dialog "Select Field of Study and Level" (Program, Shift/session, Field of Study, Level,
   Section) -> "Add Enrollment" -> "Save" -> "Update User" ("User updated successfully").
   Maryam: Evening Nazra, Qur'an (Nazra), Level 1, Section A - shown as
   "Qur'an (Nazra)-Level 1 - Level 1(A)".
8. Verification in Classroom (/attendance, "Select Class"): "Field of study - A / Level 1 /
   1 student" (Yusuf) and "Qur'an (Nazra) - A / Level 1 / 1 student" (Maryam); every other
   listed class shows 0 students.

## Money truth (exact UI figures)
- Registration $50 + $25 = $75 one-time, NOT discounted, and afterwards it does not appear in
  the family's Payment breakdown (which lists monthly lines only, Total due $0).
- Sibling discount (10%) applies only to monthly tuition; on $0 tuition it is worth $0.
- "No payment is taken here - the family sets up billing themselves in the parent portal."

## INCIDENT - accidental removal and the duplicate it created (read before building yours)
- In the family detail drawer, each student row carries a small UNLABELED icon button that is
  a remove (trash) button. It was clicked by mistake: toast "Student removed", family dropped
  to 1 student. No confirmation, no undo.
- Yusuf was restored with the drawer's Students "Add" dialog (name, Program Full Time Hifz,
  Shift Morning, Class "Field of study - Level 1 - A", Fee $0) -> toast "Student added".
  That dialog collects NO date of birth, gender, or grade.
- Consequences, all verified in Users:
  - The family now holds the RESTORED Yusuf: username yusufahmedsiddiqui1, School ID
    MAD2026003, enrolled in Hifz Level 1 A - but with no DOB/gender/grade on record.
  - The ORIGINAL wizard Yusuf still exists as a separate Active student: username
    yusufahmedsiddiqui, School ID MAD2026001, "No enrollments added", and it alone carries
    the wizard-entered DOB (2015-06-14). It is not in the family billing list and not in any
    class, but it is still checked in the guardian's child-assignment list (the guardian's
    list therefore shows three student records).
  - Users offers no fix: the Delete button is disabled for these records, and the Edit User
    dialog has no date-of-birth field for any student. The orphan must be archived/reconciled
    by the school manually.
- Design lessons: label destructive icons, confirm removals, offer undo, and make re-adding a
  removed member restore the original record instead of minting a new identity.

## Other gotchas
- Phone doubling bug again: the guardian's phone is stored/displayed as +92923005550117
  for an intended +92 300 5550117.
- Parents get no School ID; students do (MAD2026xxx - note the teachers are MADT2026xxx).
- A student's "Program & schedule" line in Edit User points to Tools -> Programs ->
  Enrolled students for program enrolment, while class (field/level/section) enrolment is
  the separate Manage Enrollments dialog used above.
