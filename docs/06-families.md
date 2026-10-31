# Families

- Route(s): /tools/families (list, detail drawer, 6-step Create Family wizard)
- Roles that can see this: Manager (as observed)
- Screenshots: ../screenshots/families/ (pending - batch 2)

## What it does
Groups students under one billing family: "Group students into families to simplify billing,
discounts and tracking." One family = one primary guardian (the payer), optional co-guardians,
and one or more students, billed monthly as a unit with sibling discounts applied automatically.

## Screens

### List
- Stat cards: OVERDUE FAMILIES | FAMILIES | STUDENTS GROUPED | MONTHLY BILLED (all zero when empty).
- Controls: search "Search family or student...", "Filter and group" button, "New family" button,
  "Unlock deletion" (tooltip: "Deletion locked. Click to unlock.").
- "Filter and group" is a misnomer: the popover holds only grouping options - "Group: Status",
  "Group: Cycle", "No grouping" (default), "Archived". No actual filters.
- Empty state: "No families yet" / "Create your first family to group students for billing."
- Columns once populated: Family | Students | Guardians | Monthly total | Status | actions
  ("More actions" menu). Example row: "AR / Ahmed Raza Siddiqui / Siddiqui family - Father",
  student initials, "1 guardian", $0, Status "Due".

### Detail drawer (click a family row)
- Tabs: Billing | Charge | Past payments.
- Collapsible Guardians and Students sections, each with an Add button.
- Payment breakdown panel, "Mark as paid" (disabled when nothing is due), "Send bill",
  "Billing settings", "Done".
- Family facts shown for the Siddiqui family: Cycle Monthly, Status Due, Auto pay On.
- HAZARD (found live, see flows/admit-siblings.md): each student row in this drawer has a small
  UNLABELED icon button that removes the student immediately ("Student removed" toast). No label,
  no confirmation, no undo.

### Create Family wizard - 6 steps: Guardian, Co-guardians, Students, Programs, Costs, Review
Step 1 - Guardian: First name*, Last name*, Relation (dropdown, default Father), Phone
(calling-code dropdown, default United States (+1); plus number field), Email.
Note on the step: a password is generated automatically and emailed with the sign-in link.
Next stays disabled until the step is valid. THERE IS NO ADDRESS FIELD anywhere in the wizard.
Step 2 - Co-guardians (optional, skippable): Full name, Relation (default Mother), Phone, Email,
"Add guardian".
Step 3 - Students (per child): First name, Last name, Date of birth (Month dropdown + Day + Year),
School grade (dropdown, default Grade 1), Gender (Male/Female toggle), "Requires special care"
checkbox, Allergies (text), Medical notes / conditions (optional text). "Add student" button;
Next requires at least one student.
Step 4 - Programs (per child): program buttons showing price ("Full Time Hifz $0/mo - $50 reg"),
then a Shift button. NO Level/Section/Class choice exists here - class placement happens later
(see flows/admit-siblings.md). A second child in a discounted program is badged
"2nd child - sibling discount 10% off".
Step 5 - Costs: per-child monthly lines, one-time registration total, and "Add a further
discount" (No/Yes) with the note "Sibling discounts are already applied. This is anything on
top, such as hardship support."
Step 6 - Review: main guardian (with phone/email), children with program + price, the parent
account note (generated password emailed with sign-in link), monthly cost panel.
Buttons: Back / "Create family". Success toast: "Family created: <guardian name>".

## Money behaviour (verified with the Siddiqui family, both programs free)
- Sibling discount applies ONLY to monthly tuition, never to registration fees.
- Registration: $50 (Hifz) + $25 (Evening Nazra) = "One-time registration $75", charged in full.
- With $0 tuition the 10% sibling discount is worth exactly $0.
- After creation, the family Payment breakdown shows ONLY monthly lines (per child $0,
  Subtotal $0, "Add discount -", Total due $0). The $75 registration does not appear there.
- Wizard cost panel states: "No payment is taken here - the family sets up billing themselves
  in the parent portal."

## Records created in this module
See CREATED_RECORDS.md: the Siddiqui family (guardian + 2 students in family), plus an orphaned
duplicate student record left by the drawer-removal incident (documented in
flows/admit-siblings.md).

## Notes - bugs and quirks found
1. Unlabeled destructive icon in the detail drawer removes a student with no confirmation
   (hit during this walkthrough; restoration created a duplicate user - see the flow doc).
2. Phone country-code doubling also applies here (+9292...), same root bug as Users.
3. No address field for guardians anywhere in the creation flow.
4. "Filter and group" contains no filters.
5. Registration fees vanish from the family's own payment breakdown after creation.
