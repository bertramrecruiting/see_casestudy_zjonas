# Proposed Target Customer/Account Data Model (as drafted by the implementation team)

## ERP: Customer
Authoritative system of record for the fields below.

| Field | Notes |
|---|---|
| customer_id | ERP-generated primary key |
| legal_name | |
| tax_id | Unique per legal entity |
| billing_address / city / state / zip | |
| shipping_address / city / state / zip | Default ship-to; multiple ship-tos not modeled in v1 |
| payment_terms | e.g. NET30, NET45, Prepay |
| credit_limit | |
| credit_status | Good / Hold / Review |
| active_flag | |
| parent_customer_id | Supports corporate hierarchy / DBA rollups |
| location | Servicing branch (Dayton / Toledo / Fort Wayne) |

## CRM: Account
System of record for relationship/sales fields.

| Field | Notes |
|---|---|
| account_id | CRM-generated primary key |
| account_name | May differ from ERP legal_name (DBA, informal name) |
| erp_customer_id | Foreign key back to ERP; nullable for prospects |
| owner_sales_rep | |
| industry | |
| website | |
| primary_phone | |
| account_status | Prospect / Active Customer / Inactive |

## CRM: Contact
| Field | Notes |
|---|---|
| contact_id | |
| account_id | FK to CRM Account |
| first_name / last_name | |
| email | |
| phone | |
| title | |
| is_primary | |

## Open items the implementation team flagged but did not resolve
- Whether `account_name` in CRM is allowed to diverge from `legal_name` in ERP, and if so, which one displays to sales reps.
- Whether DBAs / sub-brands get their own CRM Account or roll up under the parent.
- Whether `erp_customer_id` on CRM Account is enforced as a hard foreign key or just a soft reference populated by the integration.
- How multiple ship-to addresses per customer will be represented (not in scope for v1 per ERP team, but Sales says they need it day one).
- Whether CRM is allowed to create a new ERP customer directly, or whether ERP is the only system that can originate a customer_id.
