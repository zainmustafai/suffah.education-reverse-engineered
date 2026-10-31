# School Settings

- Route(s): /school-settings (tabs: School Info, Roles, Holidays)
- Roles that can see this: Manager (as observed)
- Screenshots: ../screenshots/school-settings/ - school-info.png (owner email, phone and street
  address blacked out - this repo is public), roles.png, holidays.png. Print-layout captures:
  they show the top of each screen and omit the sidebar.

## What it does
The foundation's core configuration: school identity and contact details, custom roles and
permissions, and holiday management. Header shows the "3/5 set up" checklist link on all tabs.

## Screens

### School Info - "School information / Basic details about your foundation."
| Field | Type | Required | Notes |
| --- | --- | --- | --- |
| School name | Text input | No asterisk shown | Value: maddrassah |
| Registration domain | Text input, prefixed "suffah.education/" | No asterisk shown | Value: maddrassah. Helper: "Families register at suffah.education/maddrassah. 'demo' is reserved." |
| Foundation type | Shaded display field | No asterisk shown | Quran |
| Contact email | Text input | No asterisk shown | Account owner's real email is stored here - redacted in this public repo |
| Contact phone - country code | Dropdown (all countries) | No asterisk shown | Pakistan (+92) selected |
| Contact phone - number | Text input | No asterisk shown | A real personal number is stored here - redacted in this public repo |
| Street address | Text input | No asterisk shown | A real street address in Jhelum is stored here - redacted in this public repo |
| City | Text input | No asterisk shown | JHELUM |
| State / Province | Text input | No asterisk shown | Punjab |
| ZIP / Postal | Text input | No asterisk shown | 49600 |
| Country | Text input | No asterisk shown | Pakistan |

Actions: "Save changes" (bottom right). No validation hints shown on load.

### Roles - "Roles & Permissions / Manage roles and their permissions"
- List screen has no fields. Empty state: "No Roles Found - No roles have been created yet."
- Actions: Refresh; Create Role; "Create Your First Role" (same dialog).
- Create Role dialog ("Create New Role" - "Create a new role and assign permissions to it."):
  - Role Name text input, placeholder "e.g., Manager, Editor".
  - A "Permissions" area exists but no permission items rendered in the views checked (possible loading gap - recheck in a later slice).
  - Buttons: Cancel, Close, Create Role. Create Role stays disabled while Role Name is empty, so a name is effectively required even without an asterisk.

### Holidays - "Holiday management / Mark non-teaching days. Class times themselves are set per program in Programs."
| Field | Type | Required | Notes |
| --- | --- | --- | --- |
| Include federal holidays | Toggle | n/a | Off. Helper: "US federal public holidays are marked as non-teaching days." |
| Include state holidays | Toggle | n/a | Off. Helper: "Add your state's public holidays to the calendar." No state selector visible while off. |
| Holiday name | Text input | Not stated | Placeholder "Holiday name (e.g. Eid al-Fitr)" |
| Date | Date input (mm/dd/yyyy + picker) | Not stated | |

Actions: "+ Add" adds a custom holiday. No separate Save button on this tab.
Empty state: "No school holidays added yet."

## States
- Roles and Holidays both have clear empty states. No error or validation states were triggered (nothing was submitted).

## Notes
- PRIVACY: this tab holds the owner's real email, phone and street address. Values are redacted in
  these docs because the repo is public; only the field structure matters as build reference.
- The product assumes a US school context in places (federal/state holidays, $ pricing) even for a
  Pakistan-based foundation.
