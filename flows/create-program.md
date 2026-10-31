# Flow: Create a program (7-step wizard)

- Entry: Programs (/tools/programs) -> "+ New program"
- Ran on: 2026-10-31
- Created: "Evening Nazra & Islamic Studies" (see CREATED_RECORDS.md)
- Screenshots: ../screenshots/programs/ (captured in browser session; export into repo pending)

## Steps

### Step 1 - Basics: "What's the program called?"
| Field | Type | Required | Value used |
| --- | --- | --- | --- |
| Program name | Text input (placeholder "e.g. Full-time Hifz") | Yes - Next disabled until filled | Evening Nazra & Islamic Studies |
| Tagline | Text input, labeled "(optional)" | No | Part-time evening classes for school-going children |
| About this program | Textarea, markdown with live Preview, labeled "(optional)" | No | Evening-program description with a bold "Focus" list (Nazra Qur'an, duas/Islamic studies, akhlaq) |

### Step 2 - Program type: "How do families pay for it?"
Two radio cards only - this step is about the PAYMENT MODEL, not the kind of program:
- "Default: One price for the program. A child enrols in a single shift - e.g. Morning or Afternoon" (preselected)
- "Pay per session: The price is set per session. A child can select more than one session, and the family is charged for each one."
Chosen: Default (closest fit for a single Evening shift). There is no full-time/part-time choice here.

### Step 3 - Curriculum: "Set up the curriculum"
Two entry cards:
- "Import from existing setup: Found in School Settings: 1 field of study, 4 sections, 0 students"
- "Create new curriculum: Add fields of study, levels & sections from scratch" (chosen)
Per field of study: name text input (placeholder "e.g. Quran"), Delete control; per level: level name
text input (placeholder "e.g. Qā'idah"), Sections number (default 1), Remove level; plus
"Add level" and "Add field of study". Every field requires at least one named level.
Entered: Qur'an (Nazra) with Level 1-3; Islamic Studies with Level 1; Arabic with Level 1.
Result: 3 fields, 5 levels, 5 sections.

### Step 4 - Shifts: "Organise your sections into shifts"
The wizard pre-creates one shift (initially named "Morning"). Fields: shift name text input;
start/end time pickers (hour/minute/AM-PM); Seats number (default 20); day toggles Mon-Sun;
a "YOUR CURRICULUM" panel lists sections to place ("0 of 5 not placed yet" - all 5 auto-placed
into the single shift); "Add shift" button. NO waitlist control exists in the wizard.
The pre-created shift was renamed instead of adding a second one.
Entered: Evening, 5:00 PM - 7:00 PM, 25 seats, days intended Mon-Thu.

### Step 5 - Pricing: "Set the price"
| Field | Type | Notes | Value used |
| --- | --- | --- | --- |
| Tuition | Number ($) | Placeholder 80 | Left blank (program stays free) |
| Billing | Dropdown | Shown as "Per month"; other options not opened | Per month |
| Registration fee | Number ($) | Placeholder 50 | 25 |
No Finance payment-plan field exists in the wizard. The saved Pricing tab confirms
"No plan (free)" - plans come from Tools -> Finance - and "No price set. This program is free."

### Step 6 - Sibling discount
Toggle (already ON), text "First child pays full; each additional sibling gets the discount",
type buttons Percentage (selected) / Fixed / Stepped, Percent off (default 10).
Confirmed: ON, Percentage, 10.

### Step 7 - Review: "Review & create"
Summary cards with Edit buttons: PROGRAM (name), CURRICULUM ("Built from scratch"),
SHIFTS ("Evening - 5:00 PM - 7:00 PM"), PRICING ("Free", "Sibling discount: 10% off each additional").
"Create program" completes the wizard. Success notice: "Program created: 5 sections placed."

## Result and verification
- Programs list now shows "Evening Nazra & Islamic Studies - Free - sibling discount - 1 shift,
  5 levels, 5 sections" next to the untouched Full Time Hifz.
- A newly created program starts in the LOCKED state, same as Full Time Hifz.
- Saved detail verified: name/tagline/About match Step 1; Evening shift 05:00 PM - 07:00 PM,
  0/25 seats, 5 sections placed; Pricing: No plan (free), registration fee $25, sibling discount
  ON / Percentage / 10.

## Discrepancies found (product quirks, left as-is)
1. DAYS: Friday was deselected in the wizard, but the saved shift summary reads
   "Mon, Tue, Wed, Thu, Fri - 5:00 PM - 7:00 PM". The Friday deselection did not stick.
2. WAITLIST: not offered in the wizard; on the saved program the WAITLIST switch exists but is OFF.
Fixing either requires unlocking the program (an edit flow not yet documented).
