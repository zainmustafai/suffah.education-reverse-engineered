# Flow: Record fees for a family (charge + payment attempt)

- Entry: Families -> family drawer -> Charge tab / Past payments tab
- Ran on: 2026-10-31 against the Siddiqui family - see CREATED_RECORDS.md
- Screenshots: ../screenshots/finance/finance.png

## Goal
Represent the admission scenario's money: a $75 registration charge on the family, then a
$40 partial cash payment, leaving $35 outstanding (and ideally overdue).

## What actually happened
1. Charge added: "Registration fees", $75, Category "Other" (no Registration category
   exists), For "Whole family", Email receipt ON. Toast "$75 charge added". The charge sits
   under "Charges - $75 unpaid" (dated Oct 31, 2026) with Mark paid / Remove charge actions.
   It does NOT enter the monthly Payment breakdown, the Families list totals, or the
   OVERDUE FAMILIES counter - all stayed $0 / Due / 0. No invoice number was issued.
2. Partial payment BLOCKED by the product (two routes tried):
   - Charge -> Mark paid: the Amount received field is disabled at the full $75 -
     "A charge is paid in full." Cancelled without recording.
   - Past payments -> Mark as paid: validates against the MONTHLY outstanding ($0);
     40 was rejected with "That is more than the $0 outstanding." Cancelled.
   Result: no payment exists; Past payments still reads "No payments recorded yet";
   the real balance ($75 unpaid) and the scenario balance ($35 after $40) are both
   unrepresentable in the UI.
3. Overdue could not be triggered: charges have no due-date field, and the family status
   never left "Due".
4. "Send bill" was clicked once to inspect it - it has no inspection step. It sent the
   family's monthly bill (Total due $0) immediately, with no preview and no channel shown
   (email vs SMS is not disclosed anywhere in the UI). Drawer header now reads
   "Last bill Oct 31, 2026". Documented as a hazard in docs/09-finance.md.

## Takeaways for a clone build
- One-off charges need due dates, categories that match real school charges (registration!),
  and inclusion in the family's outstanding balance.
- Part-payments are table stakes for school fees; locking "Amount received" to the full
  charge makes the ledger useless for instalment-paying families.
- Never ship a one-click Send with no preview of content and channel.
