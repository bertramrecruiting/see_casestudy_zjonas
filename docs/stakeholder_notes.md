# Stakeholder Discovery Notes

## Sales (VP of Sales + 2 reps)
- "We need one single screen that shows everything about a customer — don't make us
  log into the ERP to see if someone's on credit hold."
- "Reps should be able to create a new account in CRM the moment they get a lead,
  without waiting on anyone in finance or IT."
- "Our account names in CRM are sometimes different from whatever the 'official' name
  is in the ERP — customers go by nicknames, DBAs, etc. Don't force us to use the legal
  name everywhere."
- "We've had reps create duplicate accounts for the same customer because there's no
  good way to search/dedupe today. That needs to get fixed in the new system."
- One rep specifically: "Some of our biggest customers have 3-4 locations that all
  order separately — I don't know if that's 1 account or 4 in the new system and I
  don't think anyone's decided."

## Finance / Credit (Controller)
- "Credit status and credit limit must only ever be set in the ERP. If Sales could
  edit that in CRM we'd have a compliance problem."
- "We need to know immediately if a customer's payment terms or credit status change
  — reps keep promising terms we can't honor."
- "Tax ID is how we identify a legal entity for 1099 and credit purposes. I don't
  trust that it's been captured consistently — we've had audit findings on this before."
- "I don't want Sales creating 'new customers' that are really just existing customers
  with a different name. That's caused billing and credit limit messes in the past."

## Operations / Customer Service
- "We use whatever's in the spreadsheets more than either system because neither one
  has the contact who actually answers the phone at the loading dock."
- "Shipping addresses change more often than people think — sometimes a customer has
  a new site and nobody updates the ERP for weeks."
- "We've flagged some customers inactive in the ERP when they stopped ordering, but
  some of those come back a year later and place an ecommerce order anyway — then
  nobody notices because the account's marked inactive."

## IT
- "Our ERP license tier caps API call volume, and that quota is shared across every
  integration hitting the ERP — the ecommerce site, the EDI connector to our
  distributors, nightly reporting extracts, and now the CRM. We don't have headroom
  to assume the CRM can poll or sync aggressively without pushing something else
  over the limit."
- "If the CRM integration is 'chatty' — polling frequently, or syncing field-by-field
  instead of batching — we'll either get throttled or have to pay for a higher tier.
  Nobody's budgeted for that yet."
- "We lean toward batch/nightly sync as the default specifically to stay within quota,
  not because of some old-school uptime restriction — the ERP API itself is available
  around the clock."
- "We don't have a true unique identity key across systems today. Tax ID is close but
  not every record has one, and distributors without a US tax presence (if we ever
  have them) wouldn't have one at all."
- "Nobody owns data quality today. Sales, CS, and whoever exports the spreadsheet all
  make their own judgment calls about what's 'the same customer.'"
- "We can stand up the integration, but someone needs to decide what happens when the
  ERP and CRM disagree about who owns a field, because right now everyone assumes
  their own system is right."

## Executive (CFO + CEO, informal comments during kickoff)
- CFO: "I don't want this migration to quietly merge or lose any customer that's still
  active or has open AR. I'd rather something sit in a review queue too long than
  get merged incorrectly."
- CFO: "The board approved this ERP spend on the assumption we go live in twelve
  weeks — that date is tied to our lender reporting commitments, not just internal
  convenience. I need to know as early as possible if that's at risk, not at week 11."
- CFO: "That said, don't let 'we hit the date' become the excuse for bad data getting
  into the new systems. If I have to choose between on-time and correct, I want to
  have that conversation explicitly — I don't want it decided by default because
  nobody raised it."
- CFO: "We've acquired companies before where the 'quick and dirty' data migration
  became a six-month cleanup project after go-live. I'd rather hear bad news now
  about what's really achievable in twelve weeks than get a surprise later."
- CEO: "Customers should not notice this transition. If a customer calls in and their
  account looks different, is missing a ship-to, or their pricing looks wrong, that's
  a problem — I don't care which system is 'technically correct.'"
- CEO: "I trust the team to make the right call on the technical details. What I need
  is a clear answer, before go-live, on what's guaranteed to work day one versus
  what's a known gap we're accepting."
