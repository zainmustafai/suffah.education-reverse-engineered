# Admissions

- Route(s): /tools/registration (setup), /tools/registration/applications (review queue)
- Roles that can see this: Manager (as observed)
- Screenshots: ../screenshots/admissions/admissions.png, ../screenshots/admissions/applications.png

## What it does
Not a registrations list and not an internal enrolment tool. Admissions is the school's PUBLIC
sign-up configuration: "How families apply. Seats & shifts are defined in Programs: this is the
sign-up link and form." Internal student creation lives in Families and Users instead.

## Screens

### Setup - /tools/registration
- Stat cards: SEATS FILLED 0 / 45 | OPEN SEATS 45 | ON WAITLIST 0.
- "Capacity by shift" - labelled "LIVE FROM PROGRAMS" with a "Manage in Programs" link:
  Full Time Hifz - Morning - 9:00 AM-12:00 PM - 0/20 - 20 open - NO WAITLIST;
  Evening Nazra & Islamic Studies - Evening - 5:00 PM-7:00 PM - 0/25 - 25 open - NO WAITLIST.
  (Capacities mirror Programs exactly; waitlist flags come from the programs too.)
- "Public sign-up":
  - Term (text, placeholder "e.g. Fall 2026").
  - Registration domain: prefix "suffah.education/" + the school slug ("maddrassah").
  - Public registration link https://suffah.education/maddrassah with Copy button -
    "Families use this link to browse programs and apply. Opens in a new tab."
  - Parent account link https://suffah.education/maddrassah/parent-account with Copy button -
    for children already at the school who never applied through the public form.
- "APPLICATION FORM FIELDS" with an "Add field" button. Current fields:
  Student full name (Text, REQUIRED, locked) | Date of birth (Date, REQUIRED, locked) |
  Program of interest (program, REQUIRED, locked) | Parent / guardian name (Text, REQUIRED) |
  Email (Email, REQUIRED) | Phone (Phone, REQUIRED) | Grade applying for (Select, OPTIONAL) |
  Additional notes (Long text, OPTIONAL).
  The three locked core fields cannot be removed; the rest of the form is school-configurable.
- Top-right: "Review applications" link.

### Review queue - /tools/registration/applications
- Heading "Applications" / "Assign incoming students and approve the waitlist".
- Tab "Assign admitted students 0": an "Assign automatically" toggle (off) with the note
  "Place each admitted student into the first open section of their shift."
  Empty state: "No students waiting to be assigned".
- Tab "Manage waitlist 0": empty state "No students on the waitlist".

## Notes
- The public form was not submitted during this walkthrough (it is a public page; the internal
  Families wizard covers the same intake with full documentation - see flows/admit-siblings.md).
- Seat counts on this page are a live read-model of Programs; nothing is editable here except
  Term, the domain slug, and the form fields.

## Later state (batch-2 capture, same day)
- Seats filled moved to 2 / 45 (43 open) once the two students were enrolled.
- The Applications queue, empty during slice 4, later showed "1 admitted student to assign"
  with level/section assignment controls for the Evening fields (Arabic, Islamic Studies,
  Qur'an (Nazra)). The product does not say who it is; the likely candidate is Maryam, whose
  enrolment was completed through Users rather than through this queue (inference - the queue
  appears to track a different assignment state than Manage Enrollments).
