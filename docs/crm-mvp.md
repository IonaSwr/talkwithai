# CRM MVP

This is the smallest CRM/database direction for selling AI-enabled services with usage-based billing.

## Goal

Track:

- who the customer is
- who the important contacts are
- what service they use
- how much AI usage they consume
- what should happen next to close or expand revenue

## Smallest useful entities

### 1. Accounts
Represents a company or an individual paying customer.

Suggested fields:

- `id`
- `name`
- `type` (`individual` or `company`)
- `status` (`lead`, `active`, `paused`, `lost`)
- `industry`
- `website`
- `notes`
- `created_at`

### 2. Contacts
Represents important people connected to an account.

Suggested fields:

- `id`
- `account_id`
- `full_name`
- `role`
- `email`
- `phone`
- `relationship_strength` (1-5)
- `decision_maker` (true/false)
- `notes`

### 3. Offers
Represents a productized service or micro-app offer.

Suggested fields:

- `id`
- `name`
- `description`
- `pricing_type` (`fixed`, `usage_based`, `hybrid`)
- `base_price`
- `active`

### 4. Subscriptions or engagements
Represents what an account is currently buying.

Suggested fields:

- `id`
- `account_id`
- `offer_id`
- `start_date`
- `end_date`
- `status`
- `billing_notes`

### 5. Usage events
Represents measurable AI usage for billing or review.

Suggested fields:

- `id`
- `account_id`
- `engagement_id`
- `event_type`
- `units`
- `unit_cost`
- `internal_cost`
- `customer_price`
- `recorded_at`
- `metadata_json`

### 6. Opportunities
Represents pipeline and follow-up actions.

Suggested fields:

- `id`
- `account_id`
- `title`
- `stage`
- `estimated_value`
- `next_step`
- `next_step_due_at`
- `owner`
- `notes`

## Suggested first workflows

### Workflow A: Add a new lead
1. Create account.
2. Add primary contact.
3. Create one opportunity.
4. Write one next step.

### Workflow B: Start a paid engagement
1. Link account to one offer.
2. Set engagement status to active.
3. Record usage manually.
4. Review margin before automation.

### Workflow C: Weekly review
1. View active accounts.
2. View top usage accounts.
3. View overdue next steps.
4. View opportunities close to closing.

## What not to build yet

Do not start with:

- complex RBAC
- multi-team hierarchies
- advanced analytics
- automated invoicing
- custom workflow builders
- generalized prompt marketplace

## Best next implementation step

The best first technical step is:

1. create these six tables in a simple relational database
2. build one internal form for account + contact creation
3. build one list page for opportunities with next-step dates
4. manually enter usage data before integrating any AI providers

This keeps the system cheap, understandable, and easy to validate.
