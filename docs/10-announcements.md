# Announcements

- Route(s): /announcements
- Roles that can see this: Manager (as observed)
- Screenshots: ../screenshots/announcements/ (first batch already pushed)

## What it does
School-wide broadcast: "Broadcast to SMS, Email and in-app notification." Sending is metered:
the header shows "200 credits ($0.05 each)" with an "Add credits" button. Every announcement
passes an admin-approval gate AFTER creation before it is delivered.

## List screen
- Cards, not a table; no per-card action buttons visible. Each card shows: title, status
  badge (PENDING APPROVAL / PUBLISHED), priority, school, author, "To: All", date, a message
  snippet, and the fixed footer "This message was sent by <school> powered by Suffah. If you
  want to stop receiving these messages text NO."
- A banner counts the approval queue ("2 announcements waiting for admin approval" after the
  walkthrough's test item).
- Display bug: a card shows "To: All" even when the announcement was composed for specific
  recipients only (verified with the walkthrough's test announcement, 6 named recipients).
- Content note: the list also contains platform seed/demo items not created by this school -
  10+ PUBLISHED cards titled "Asselamu Aleykum" by "Huzeyfa S." from "Unknown school", and one
  PENDING APPROVAL item "Voluptas eos facere accu" (URGENT, Oct 30, 2026, authored under the
  owner's name). Demo data bleeds into a real school's announcement list.

## Composer - 6 steps (Basics, Schedule, Delivery, Recipients, Review, Payment)
1. Basics: Title (MAX 25 CHARACTERS - the walkthrough's 29-character title was truncated to
   "Walkthrough test announce"), Message (max 200 characters), the fixed footer above, and
   the note "Only standard SMS characters (GSM-7) are allowed. Emoji and special symbols are
   removed." Priority: LOW / MEDIUM (default) / HIGH / URGENT.
2. Schedule: "Send immediately - Deliver as soon as published" (default) or "Schedule for
   later" (Date & Time picker) with a Recurring switch - Frequency Daily / Weekly / Monthly
   and an optional End date.
3. Delivery: SMS (ON BY DEFAULT), Email (off by default), In-app notification ("Always on" -
   locked on, "Notification in the Suffah web app"). A school that does not notice the SMS
   default will spend credits and text parents by accident.
4. Recipients: role checkboxes (Students / Teachers / Parents / Managers - "Click a category
   to select everyone in it, then untick anyone you want to leave out below") plus
   "Specific Users": name search, a Filter (Field / Level / Section, all default All), and
   individual checkboxes. There is no class or family picker as such - Field/Level/Section
   filtering is the class selector. The specific-user list showed all 7 walkthrough-era users,
   including BOTH Yusuf records (the duplicate is a full citizen here too).
5. Review: restates title, message, footer, priority, channel states (e.g. "Email: Off /
   SMS: Off / In-app: On"), send timing, recipient count and names.
6. Payment: "Recipients: 6 / Required credits: 0 / Estimated charge: $0.00 / Current
   balance: 200", "Pay with credits" (default) vs "Pay with Stripe". In-app-only delivery
   costs 0 credits. Final button: "Create Announcement".

## Approval gate
Creation is not delivery. The new announcement lands as PENDING APPROVAL (toast "Announcement
created successfully") and is delivered only after an admin approves it - the composer itself
contains no approval step. The walkthrough's test announcement was left unapproved on purpose.

## Test announcement created in this walkthrough
"Walkthrough test announce" (title truncated by the 25-char cap), body "This is a test
announcement created during a product walkthrough. No action needed.", MEDIUM, send
immediately, IN-APP ONLY (SMS off, Email off), exactly 6 fictional recipients (both Yusuf
records, Maryam, Ahmed Raza, and the two fictional teachers), 0 credits. Status:
PENDING APPROVAL - never approved, never delivered. See CREATED_RECORDS.md.
