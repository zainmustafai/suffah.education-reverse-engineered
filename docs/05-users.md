# Users

- Route(s): /users (list), /users/register (add user), /profile (own profile via avatar menu)
- Roles that can see this: Manager (as observed)
- Screenshots: ../screenshots/users/ (captured in browser session; export into repo pending)

## What it does
Central directory of every account in the school: managers, teachers, parents, students.
Registration here is manual and collection-based - you stage one or more users, then register
them in one batch under a compliance agreement. Passwords are auto-generated and emailed.

## Screens

### List - "Users / Manage users and permissions"
- "Add User" link goes to /users/register. Footer: "Showing 1 to 3 of 3 users" (after slice 3).
- Columns: select-all checkbox | Name | Email | Username | Phone | Role | Status | Created |
  Agreements | Actions.
- Rows per page: 10, Previous/Next pager. Clicking a row name does NOT navigate.
- Search: "Search by name, email, phone, or role..." - applies on Enter, not while typing.
  No-match state: 'No users found matching "qqqnomatch".'
- Filters:
  - "All Users" combobox: Status (Active, Inactive) and Program (Full Time Hifz,
    Evening Nazra & Islamic Studies).
  - "All roles" combobox: All roles, Manager, Parent, Student, Teacher.
  - "More" menu: View archived, Send usernames, Unlock delete (menu opened only during the
    walkthrough; none of the three was activated).
- Row actions for a normal user: Check, Reset Password, Archive user, Edit user, Delete user.
- The founding manager row (username "zain", badges "Founding Manager" and "Protected") has all
  actions except Check disabled, with tooltips: only admins can reset/edit/delete the original
  manager account, and it cannot be archived. Created Oct 29, 2026; Agreements "2 accepted".
  (The owner's email/phone appear in this row - redacted in this public repo.)
- "Check" opens an Agreement Details dialog: for the founding manager the header reads
  2 Total / 0 Current / 0 Outdated while the listed items are "Suffah Privacy Policy" v1.0
  OUTDATED and "Terms of Service" v1.0 CURRENT - the header counts do not match the items
  (observed inconsistency).

### Special Care view - /users?role=Student&specialCare=1
- A link from the Tools hub lands on the same list with the role filter preset to Student and a
  "Special care only" switch (ON) under the role filter. No extra columns appear.
- Empty state: 'No users found with role "Student".' Switching the toggle off changed nothing
  while no Student users exist.
- Conclusion: "Special Care" is a student filter flag, not a separate module or column.

### Own profile - /profile (avatar menu > Profile)
- Header: full name, email (redacted here), Manager, "Joined N/A", avatar initials "MA".
- QUIRK: the profile header says "Status: Inactive" while the Users list shows the same
  account as Active.
- Personal Information (Edit button; fields shown disabled): Full Name, Email Address,
  Phone Number (calling-code combobox + number textbox; value redacted here),
  Date of Birth (empty, dd/mm/yyyy).
- Account Settings: "Change Password" heading with a Change Password button.
- Avatar menu also offers Toggle Theme and Log out.

## Add user - /users/register ("User Registration / Add users manually")
See flows/register-user.md for the full run. Structure:
- Card "Add New User":
  - User Role * (required combobox: Manager, Parent, Student, Teacher)
  - PERSONAL INFORMATION: Full Name * (required); Email Address (Optional);
    Phone Number (Optional) = calling-code combobox (defaults to United States (+1), full
    country list) + "Phone number" textbox.
  - FIELD OF STUDY ASSIGNMENTS: "Manage Assignments" button; empty text 'No assignments
    added. Click "Manage Assignments" to add field of study-level-section assignments.'
  - SECURITY note (verbatim): "Password will be auto-generated and sent to the teacher's
    email address when provided." No SMS wording appears anywhere in the flow.
- Assignment dialog "Manage Class Assignments": a strict cascade -
  Program -> Field of Study -> Level -> Section (auto-fills; Level 1 gives Section A).
  Each select stays disabled until the previous one is chosen; "Add Assignment" stays
  disabled until the cascade is complete.
- Submit is collection-based: "Add User to Collection" -> "Ready to Register" ->
  "REGISTER N USER & CONTINUE" -> "User Registration Agreement" dialog (school authority to
  register; information accurate; users will comply with Suffah's Terms of Service; data
  handling follows FERPA and COPPA) -> "Register Users (N)".
- Toasts: "User added to collection / You can set enrollments by clicking edit." then
  "Registration completed - 1 user registered successfully."
- An Excel import path is mentioned in the register page's empty state
  ("import them from an Excel file").

## Records created in this module (fictional, see CREATED_RECORDS.md)
- Bilal Ahmed Khan, Teacher, username bilal.khan, School ID MADT2026001 -
  assignment: Full Time Hifz > "Field of study" > Level 1 > Section A
  (the Hifz program's only field is literally named "Field of study").
- Fatimah Zahra Sheikh, Teacher, username fatimah.sheikh, School ID MADT2026002 -
  assignments: Evening Nazra > Qur'an (Nazra) L1 A and Islamic Studies L1 A.
- Both show Status Active, Agreements "0 accepted", Created Oct 31, 2026.

## States
- Empty states are sentence-style and role-aware ('No users found with role "Student".').
- Registration success is a toast, not a page change.

## Notes - bugs and quirks found
1. PHONE BUG: entering a local number with the +92 calling code stores the country code twice.
   Both teachers show "+9292..." in the list (e.g. +92923215550147 instead of +923215550147).
   The edit form displays the field as "92 321 5550147" and an attempted correction on one
   user ended with "No changes to save" - the doubled code cannot be fixed through Edit.
2. Profile header status (Inactive) contradicts the Users list (Active) for the same account.
3. Agreement Details header counts (0 Current / 0 Outdated) contradict its own listed items
   (one CURRENT, one OUTDATED).
4. Search does not filter live; it needs Enter.
5. The founding manager is hard-protected: no reset, edit, archive, or delete from this UI.
