# Programs

- Route(s): /tools/programs (list, detail, and a 7-step create wizard on the same route)
- Roles that can see this: Manager (as observed)
- Screenshots: ../screenshots/programs/ (captured in browser session; export into repo pending)

## What it does
A program is the overall package families enrol into: curriculum (fields of study with levels),
shifts, sections, class scheduling, and pricing with sibling discounts. Programs also feed the
public portal (program page + registration list) and Admissions/billing.

## Screens

### List
- Heading "Programs", helper: "Choose a program to manage its curriculum, shifts, sections, pricing & schedule."
- One program exists: "Full Time Hifz" - "Free - sibling discount", badges "1 shift", "4 levels",
  "4 sections", action "Manage >". No schedule times on the card.
- Actions: "+ New program" (top right) and a dashed "New program" placeholder card.

### Program detail - Full Time Hifz (LOCKED)
- Banner: "This program is locked - unlock it to change curriculum, shifts, pricing or scheduling."
  with an Unlock button and a Locked badge. Every field below was disabled while locked.
- Sub-tabs: Program setup, Shifts, Scheduling, Pricing.

Program setup:
- Program name (text) = "Full Time Hifz"; "Request deletion" button (disabled).
- Curriculum: one "Field of study" with 4 levels (Level 1-4). Helper: removing a field here only
  removes it from this program, not the shared school curriculum. Controls (disabled): Field name,
  "+ Add field", "New level name (attaches to program)", "+ Add level", Remove actions.
- Public listing: Tagline = "A Lifelong Connection to the Book of Allah" (helper: "One line, shown
  under the program name."); About this program (markdown textarea: bold, italic, lists, links;
  "Leave empty to hide the section on the portal."); Curriculum includes (one item per line, each
  becomes a bullet on the program page).

Shifts:
- 1 shift: Morning, 09:00 AM - 12:00 PM, Mon-Fri, Seats 20 ("0 / 20", "20 open"), Waitlist off.
- Sections: 4 placed - one "Section A" per level, all in Morning. "+ Section" placeholders.
- "Sections in each shift" repeats the shift summary: "4 SECTIONS AVAILABLE".

Scheduling:
- "Set each class's hours and teacher within its shift." Summary badge "4 not scheduled".
- Table: CLASS | SHIFT | DAYS | TIME | TEACHER. Four rows (Level 1-4, Section A, Morning):
  Days "Not scheduled", Time "-", Teacher "Unassigned", "Schedule this class" (+) disabled.

Pricing:
- Payment plan dropdown = "No plan (free)" (helper: "Plans come from Tools -> Finance"), "+ New plan".
- Registration fee (number, $) = 50.
- Sibling discount toggle ON. Helper: "First child pays full; each additional sibling gets the
  discount." Discount type: Percentage (selected) / Fixed / Stepped. Percent off = 10.
- Message: "No price set. This program is free."

### Create wizard - "New program", 7 steps
Steps: Basics, Program type, Curriculum, Shifts, Pricing, Sibling discount, Review.
Step 1 "Basics" - heading "What's the program called?" Helper: "A program is the overall package
families enrol into. The tagline and description below appear on the public program page."
| Field | Type | Required | Notes |
| --- | --- | --- | --- |
| Program name | Text input | Effectively yes - Next stays disabled while empty | Placeholder "e.g. Full-time Hifz" |
| Tagline | Text input | No - labeled "(optional)" | Placeholder "A Lifelong Connection to the Book of Allah" |
| About this program | Textarea | No - labeled "(optional)" | Markdown supported (helper text) |

Actions: Cancel, "Next >", X close. Steps 2-7 are documented in flows/create-program.md
(the full wizard run that created "Evening Nazra & Islamic Studies" on 2026-10-31).
Key discovery: Step 2 "Program type" is really the payment model - "Default" (one price,
single shift) vs "Pay per session" - not the kind of program.

## States
- Locked program: all editing controls disabled with an explanatory banner; Unlock is the gate.
- Scheduling empty state is per-row ("Not scheduled" / "Unassigned"), not a blank page.

## Notes
- Locking is a distinctive Suffah pattern: a program can be frozen against curriculum, shift,
  pricing and scheduling changes.
- Pricing is plan-driven from Finance; a program with no plan is simply free, and the sibling
  discount still applies on top of the registration/price structure.
