# Senior Enterprise Engineer: Case Study

## Background

Bertram Capital recently acquired Acme Industrial, a fictional $75M industrial products distributor operating from three locations.

Acme currently uses:

- A legacy ERP for customers, inventory, pricing, invoicing, and order processing
- A lightweight CRM used inconsistently by the sales organization
- Several spreadsheets maintained by sales and customer service
- An ecommerce site that submits orders to the ERP

Acme is moving to a new ERP and adopting a shared CRM platform.

The target operating model is expected to look roughly like this:

### ERP

The ERP will be authoritative for financial customer information, billing and shipping addresses, payment terms, credit status, product information, pricing, inventory, sales orders, invoices, and payments.

### CRM

The CRM will support prospects, accounts, contacts, sales activities, opportunities, and customer-facing sales workflows.  CRM users need enough ERP information to effectively manage customers without requiring routine access to the ERP.

The planned ERP go-live is twelve weeks from now.  You have been asked to lead the customer/account portion of this effort.

## Materials Provided

You have been provided with a small set of CSV files containing representative data from the existing environment.  The supplied data is intentionally imperfect and is representative of what you might encounter in a real enterprise-system migration.

You have also been provided with:

- A proposed target customer/account data model and field definitions
- Notes collected from business stakeholders in Sales, Finance, Operations, and IT
- A short description of the integration capabilities available in the target ERP and CRM

The stakeholder notes reflect the viewpoints and requirements expressed during discovery.  They should be treated as input to the solution, not necessarily as finalized technical requirements.

The target ERP and CRM both provide conventional APIs capable of creating, retrieving, and updating the relevant records.  The CRM can also produce outbound notifications when account or contact information changes.  You do not need to implement an API integration as part of this exercise.  Assume normal enterprise API constraints and failure conditions.

You should not assume that the proposed mappings, data ownership decisions, stakeholder requirements, or system boundaries are necessarily correct.

## Your Assignment

Spend no more than three hours on this exercise.

We are more interested in how you approach the problem, what you notice, the decisions you make, and how you communicate those decisions than in the completeness or polish of your deliverables.  A project plan, detailed schedule, RACI, resource plan, or other project-management artifacts are outside the scope of your deliverables.

Use whatever tools you would normally use to inspect and work with the provided CSV files.  You are free to use SQL, Python, another programming language, database tools, spreadsheets, AI tools, or a combination of approaches.

### 1. Assess the problem

Briefly describe how you would approach this project.

Identify:

- Important questions you would want answered before proceeding
- Assumptions you made
- Major technical, data, or business-process risks
- Areas where the proposed system boundaries or requirements should be challenged
- Decisions that need to be made by business stakeholders before implementation can proceed safely

### 2. Design the customer/account architecture

Describe or diagram how you would manage customer and account information across the CRM, ERP, and ecommerce systems.

We are particularly interested in:

- System and field-level data ownership
- Identity and relationships across systems
- Creation/update workflows and synchronization direction
- Integration reliability, failure handling, and reconciliation
- Auditability and observability

### 3. Evaluate and Transform the Data

Inspect the supplied CSV files.  Identify data quality, integrity, or mapping issues you believe should be addressed and explain how you would handle them.

Create a small working transformation that converts the supplied legacy customer data into the proposed target customer/account structure.

Your solution should produce:

1. A set of records that you believe are safe to migrate automatically
2. A set of records requiring business or technical review
3. Any records you believe should not be migrated, with an explanation

Include queries, scripts, or other artifacts showing how you inspected or transformed the data.

### 4. Communicate with the Business

Write a short update you would send to Acme's CFO and VP of Sales after your initial assessment.

Assume they are technically knowledgeable business leaders but are not software engineers.

Your update should explain:

- What you believe the proposed approach should be
- Any assumptions or stakeholder requirements you believe should be challenged or clarified
- The most important risks or unresolved decisions
- Decisions or input you need from the business
- Any technical or business decisions that could materially threaten the planned twelve-week go-live

Keep the update to approximately one page or less.

## Deliverables

Your solution should be added to this repository and contain the following:

1. Your assessment and recommendations
2. An architecture diagram or equivalent description
3. Your data transformation, including any supporting SQL, code, or queries
4. The resulting datasets and a description of records not selected for migration
5. Your stakeholder update

A single document plus supporting code or files is perfectly acceptable.  Clear thinking, technical judgment, and clear communication are more important than presentation polish.

## Follow-Up Discussion

The submitted exercise will be used as the basis for a follow-up discussion.  You should be prepared to walk through key decisions in your submission, demonstrate how you approached the supplied data, and respond to changes in the scenario.

The discussion may introduce additional business or technical requirements that were not included in the original exercise.  The goal is not to test your ability to react quickly to a trick question.
