# Target System Integration Capabilities (summary)

## ERP
- REST API supporting create / read / update for Customer, Address, Credit, Order,
  Invoice, and Payment objects.
- Synchronous request/response only; no native outbound event/webhook mechanism.
- Rate-limited (standard enterprise license tier): the quota is shared across all
  integrations calling the ERP (ecommerce, EDI, reporting extracts, and any new CRM
  integration), not allocated per-integration. High call volume from one integration
  can throttle or degrade the others.
- Supports idempotency via a client-supplied external reference ID field on Customer
  records.
- Nightly extract/export jobs available in addition to the API (flat file to SFTP).

## CRM
- REST API supporting create / read / update for Account, Contact, Opportunity, and
  Activity objects.
- Supports outbound webhook-style notifications when Account or Contact fields change
  (configurable per field group).
- Has a native "external ID" field on Account and Contact for storing a foreign
  system's key.
- Standard API rate limits; bulk API available for larger batch operations.

## Ecommerce
- Submits orders directly to the ERP via the ERP's order API today.
- Does not currently integrate with the CRM.
- Supports guest checkout (no required customer match), which is a known source of
  orders with no reliable ERP customer linkage.

## General constraints to assume
- Both systems can fail, time out, or return partial success on bulk operations.
- Neither system natively provides cross-system distributed transactions.
- Both APIs enforce their own required-field and uniqueness validation independent of
  whatever the other system allows.
