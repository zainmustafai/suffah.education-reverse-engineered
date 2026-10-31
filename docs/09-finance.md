# Finance

- Route(s): /tools/finance (Stripe connection only, in the observed state) plus the billing
  surfaces inside Families (family drawer: Billing / Charge / Past payments, Billing settings)
- Roles that can see this: Manager (as observed)
- Screenshots: ../screenshots/finance/finance.png

## What Finance actually is
Despite the Tools description ("Pricing, subscriptions & discounts via Stripe") and the page
subtitle ("Manage tuition pricing, subscriptions and discounts, powered by your school's
Stripe account"), /tools/finance in an unconnected school is a SINGLE Stripe-connection
screen. There are no plans, no invoices, no transactions, and no summary figures until Stripe
is connected. Plan creation does not exist pre-connection (the walkthrough's attempt to create
a "Standard Monthly $80" plan had no route at all; the family Billing settings confirm:
"Not on a Finance plan - set the day here").

## Connection options (neither was used in this walkthrough)
1. Stripe Connect ("Recommended"): "Approve through Stripe. No keys to copy." The school is
   sent to Stripe to approve and returned; a school without a Stripe account is walked through
   creating one first. Access granted to Suffah: Products, Prices, Coupons, Customers,
   Subscriptions. "The account stays yours. You can revoke Suffah's access from your Stripe
   dashboard at any time, and we'll show the school as disconnected."
   Buttons: "No Stripe account yet?" / "Connect with Stripe".
2. API keys: Publishable key field ("Safe to expose - it renders the card form in the family's
   browser") and Secret key field (a restricted rk_ key with write access works too).
   Permissions to grant (WRITE): Products, Prices, Coupons, Customers, Subscriptions.
   "Keys are encrypted at rest with AES-256-GCM and can be revoked from Stripe at any time."
   Button: "Connect Stripe".

## Family billing (inside Families -> family drawer)
- Billing tab: Payment breakdown (per-child monthly lines, Subtotal, "Add discount -",
  Total due), "Mark as paid", "Send bill", "Billing settings".
- Billing settings: Billing date "Day 1 of each month"; Billing cycle Monthly / Termly /
  Annual; Auto pay On/Off ("Charge the card on file automatically on each due date" /
  "No card on file yet - the family pays manually until they add one."); Pause billing
  On/Off; Discount None / Apply; Cancel / Save.

## Charges (one-off extras)
- Charge form fields: "What is it for?" (text), Amount ($), Category (Books & materials
  default; Uniform; Trip / event; Late fee; Other - there is NO Registration category),
  For (Whole family, or one named student), "Email receipt" switch (default ON -
  "Sends a receipt to the primary guardian").
- With Stripe unconnected the form notes: "Stripe isn't connected, so this is recorded as
  unpaid. Mark it paid once the family pays."
- There is NO due-date field, NO one-time/monthly type, and NO notes field.
- A charge lives OUTSIDE the monthly bill: after adding a $75 charge, the family's Monthly
  total, Payment breakdown, Total due, list row and the OVERDUE FAMILIES counter all stayed
  at $0 / Due / 0. Charges appear only under their own heading: "Charges - $75 unpaid", with
  per-charge "Mark paid" and "Remove charge" actions. No invoice number is generated.

## Payments - and the partial-payment wall (verified live)
- Charge "Mark paid" dialog: "OUTSTANDING $75", but "Amount received" is DISABLED, fixed at
  the full amount, with the note "A charge is paid in full." Method (Cash default; Zelle;
  Other), Date received, Reference (optional, "Cheque no., note"), Cancel / Record payment.
- Monthly "Mark as paid" dialog (Past payments): OUTSTANDING is the monthly bill only ($0 for
  the Siddiqui family); Amount received is editable but validated: entering 40 produced
  "That is more than the $0 outstanding." and Record payment stayed disabled.
- CONCLUSION: partial payments are impossible in this product today. A charge can only be
  paid in full, and a payment against the monthly bill cannot be applied to a charge. The
  walkthrough scenario (charge $75, pay $40, carry $35) cannot be represented; the $35 balance
  exists nowhere in the UI.

## Send bill - one-click, no preview (UX hazard)
- "Send bill" has NO preview, NO confirmation and NO channel selector. Clicking it sends
  immediately (toast "Bill sent"; the drawer header's "Last bill -" becomes
  "Last bill Oct 31, 2026"). The UI never states whether the bill went by email, SMS, or both,
  nor what it contained. The bill sent is the MONTHLY bill (the $75 charge is not part of it).
- Design lesson: any send-parents-money-information button needs a preview + channel display
  before it fires.

## Notes
- Overdue behaviour could not be exercised: charges carry no due date and the family status
  stayed "Due" throughout; nothing in the observed UI turns a family "Overdue".
- The $75 registration from the admission wizard appears in NO finance surface (see
  docs/06-families.md) - staff must re-add it as a manual Charge, exactly as this walkthrough
  did in flows/record-fees.md.
