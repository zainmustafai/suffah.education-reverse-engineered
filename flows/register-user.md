# Flow: Register a user manually (collection + agreement)

- Entry: Users (/users) -> "Add User" -> /users/register
- Ran on: 2026-10-31, twice (two teachers) - see CREATED_RECORDS.md
- Screenshots: ../screenshots/users/ (captured in browser session; export into repo pending)

## Steps
1. Open /users/register - "User Registration / Add users manually", card "Add New User".
2. Pick User Role (required): Manager, Parent, Student, or Teacher.
3. Personal Information: Full Name (required); Email (optional); Phone (optional) -
   calling-code combobox defaults to United States (+1); pick the right code first.
4. Field of Study Assignments -> "Manage Assignments": cascade Program -> Field of Study ->
   Level -> Section (auto). "Add Assignment" unlocks only when the full cascade is chosen.
   A user can hold several assignments (Fatimah holds two).
5. "Add User to Collection" - toast "User added to collection / You can set enrollments by
   clicking edit." The staged row shows the auto-generated login username
   (first name + last name, e.g. bilal.khan).
6. "Ready to Register" -> "REGISTER N USER & CONTINUE".
7. "User Registration Agreement" dialog: the school confirms authority to register these
   users, that the information is accurate, that users will comply with Suffah's Terms of
   Service, and that data handling follows FERPA and COPPA. Confirm with "Register Users (N)".
8. Toast: "Registration completed - 1 user registered successfully." The user appears in
   /users as Active with a School ID (MADT2026001, MADT2026002 - "MAD" prefix + year + serial).

## Credential delivery
- SECURITY note on the form (verbatim): "Password will be auto-generated and sent to the
  teacher's email address when provided."
- No SMS is involved anywhere in this flow. With no email provided, no delivery channel is
  documented in the UI - an open question for a later slice (Reset Password action in the list).

## Gotchas
- Phone country-code doubling: with +92 selected, typing the local number stores "+9292..."
  (see docs/05-users.md, bug 1). The same trap likely applies to other country codes.
- The register page is also the Excel import entry point (mentioned in its empty state).
