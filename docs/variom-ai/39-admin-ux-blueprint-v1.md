# VARIOM Admin – Complete UX Blueprint V1.0

## 1. Document Purpose

This document defines the complete User Experience architecture and functional behavior of VARIOM Admin.

The objective is to create a secure, comprehensive, and operational Platform Administration Center through which the Platform Owner can manage the platform’s commercial, operational, financial, and administrative activities.

The administration interface must be functional, not merely a visual dashboard.

It must reuse existing platform capabilities, avoid duplicated systems, and clearly identify any functionality that requires backend development or external integrations.

### Governing Principles

1. Security First.
2. Maximum Quality – Minimum Complexity.
3. Complete Administrative Control.
4. Reuse Existing Architecture.
5. No Duplicate Systems.
6. No Fake or Nonfunctional Controls.
7. Clear Separation Between Existing and Planned Capabilities.
8. Consistent Arabic and English Experience.

The VARIOM Product Vision & Simplified UX Specification V2.0 remains the highest authority for product scope and customer-facing functionality.

VARIOM Admin is a separate administrative application and must not expand the customer-facing product scope.

---

## 2. Product Ownership and Administrative Model

### 2.1 Platform Owner

The primary administrator is the Platform Owner.

The Owner has complete administrative permissions.

Owner protections:

- Another administrator cannot deactivate the Owner.
- Another administrator cannot delete the Owner.
- Another administrator cannot remove the Owner’s privileges.
- Owner account changes require strong authentication.
- All sensitive Owner actions must be recorded.
- Owner account recovery must follow a secure recovery procedure.

### 2.2 Future Administrators

The architecture must support additional administrators in the future.

The system must support:

- Administrator accounts.
- Role-based access control (RBAC).
- Granular permissions.
- Permission-based navigation.
- Restricted access to sensitive financial and security operations.
- Administrator activity tracking.

Initially, only the Owner interface is required. Do not build unnecessary multi-administrator workflows unless needed for the underlying security architecture.

### 2.3 Administrative Access

Administrative access must be separate from normal customer access.

Customer accounts must never automatically receive administrative privileges.

Administrative authorization must be enforced by the backend, not only by hiding frontend elements.

---

## 3. Global Application Architecture

### Main Navigation

1. Dashboard.
2. Users & Accounts.
3. Plans & Subscriptions.
4. Payments & Finance.
5. Credits & Usage.
6. AI & Operations.
7. Analytics & Reports.
8. Support Center.
9. Platform Settings.
10. Security & Administration.

### Global Header

The header must provide:

- Current page title or navigation context.
- Global search.
- Notifications.
- Language switcher.
- Administrator profile.
- Account security access.

### Global Search

One search interface for authorized administrative records:

- Users.
- Subscriptions.
- Payment transactions.
- Credit transactions.
- Generation jobs.
- Support requests.

Search results must respect permissions and must not expose sensitive information.

### Global Notifications

A unified notification center with:

- Critical security events.
- Payment failures.
- Subscription issues.
- AI provider outages.
- Generation failures.
- Background processing problems.
- Important system warnings.

Each notification should link directly to the relevant administrative record.

Support read/unread states, severity, timestamps, and resolution status.

Do not create duplicate notification systems inside individual modules.

---

## 4. Dashboard

### Purpose

Provide a concise overview of the platform’s current condition.

### Main KPI Cards

- Total registered users.
- Active users.
- New users.
- Active subscriptions.
- Revenue for the selected period.
- Credits consumed.

### Business Overview

- User growth.
- Subscription distribution.
- Revenue trends.
- Plan distribution.

### Operational Overview

- Total generation jobs.
- Successful jobs.
- Failed jobs.
- Active jobs.
- AI provider health.
- Infrastructure status.

### Alerts and Attention Required

Show only actionable issues.

Each alert must include:

- Severity.
- Description.
- Affected entity.
- Detection time.
- Recommended next action.
- Link to the relevant record.

### Recent Activity

Display recent important administrative and system events.

### Dashboard UX Rules

- Date-range selection.
- Clear metric definitions.
- Loading, empty, and error states.
- Clickable metrics leading to relevant filtered records.
- No fabricated values.
- No unverified revenue or cost calculations.
- No mixing estimated and confirmed financial data.

---

## 5. Users & Accounts

### 5.1 User List

Required capabilities:

- Search by name, email, and account identifier.
- Filter by account status.
- Filter by registration date.
- Filter by subscription.
- Filter by plan.
- Sort and paginate results.
- View account summary.
- Export authorized user data.

### 5.2 User Details

The user profile must be a centralized administrative workspace.

Sections:

**Account Overview**

- User identity.
- Registration date.
- Account status.
- Account identifiers.

**Subscription**

- Current plan.
- Subscription status.
- Start date.
- Expiration date.
- Renewal information.

**Credits**

- Current balance.
- Credit transaction history.
- Grants and adjustments.

**Brands**

- Associated brands.
- Brand count.
- Relevant account relationships.

**Usage**

- Image generation activity.
- Video generation activity.
- Relevant content-generation jobs.

**Payments**

- Payment history.
- Refund history.
- Related invoices.

**Activity**

- Important account events.
- Administrative actions.
- Security-relevant events.

### 5.3 Administrative Actions

Authorized actions:

- Activate account.
- Suspend account.
- Restore account.
- Deactivate account.
- Edit permitted administrative information.
- Review subscription.
- Perform authorized subscription adjustments.
- Grant compensatory Credits.
- Review account activity.

Every sensitive action must require confirmation and create an audit record.

### 5.4 Account Preview

Provide a secure, non-impersonating account preview.

Requirements:

- Read-only preview.
- No customer identity impersonation.
- No ability to perform customer actions under the customer’s identity.
- Visible administrative preview indicator.
- Access logging.
- Permission checks.

### 5.5 Account Deletion

Account deletion must respect the platform’s retention and erasure policies.

Do not implement unrestricted hard deletion.

Distinguish account deactivation, user-requested erasure, retention requirements, and legally required record preservation.

---

## 6. Plans & Subscriptions

### 6.1 Plans Management

Capabilities:

- View plans.
- Create plans.
- Edit plans.
- Activate plans.
- Disable new sales.
- Configure prices.
- Configure subscription duration.
- Configure included Credits.
- Configure brand limits.
- Configure supported features and usage limits.

Plan configuration must be flexible without introducing unsupported product capabilities.

### 6.2 Plan Change Protection

Changes to a plan must not automatically alter existing customer subscriptions.

Every plan modification must have an explicit effect and scope.

Historical subscription terms must remain traceable.

### 6.3 Subscription Management

Views:

- All subscriptions.
- Active subscriptions.
- Expiring subscriptions.
- Expired subscriptions.
- Payment-related exceptions.
- Cancelled subscriptions.

Actions:

- Upgrade.
- Downgrade.
- Extend.
- Cancel.
- Review.
- Resolve eligible exceptions.

### 6.4 Subscription Lifecycle

The interface must accurately represent:

- Pending payment.
- Active.
- Renewal pending.
- Payment failed.
- Past due, where supported.
- Expired.
- Cancelled.
- Suspended.

Do not invent states that conflict with the actual subscription backend.

### 6.5 Subscription Policies

Provide a centralized location for supported policies:

- Renewal behavior.
- Expiration handling.
- Upgrade and downgrade rules.
- Failed payment handling.
- Administrative exceptions.

Unapproved commercial rules must remain configurable but inactive or explicitly unresolved.

---

## 7. Payments & Finance

### Payment Management

- List all transactions.
- Search transactions.
- Filter by status and date.
- Link payments to users and subscriptions.
- Display provider transaction references.
- Display amount and currency.
- Display transaction timestamps.
- Review payment failures.

### Transaction Details

Show:

- Transaction identifier.
- Customer.
- Related subscription.
- Payment provider.
- Amount.
- Currency.
- Status.
- Provider reference.
- Relevant timestamps.

### Refund Management

- Review eligible transactions.
- Initiate supported refunds.
- Require confirmation.
- Require a reason.
- Record provider response.
- Record refund status.
- Maintain an audit trail.

A manual administrative status change must never be treated as a successful provider refund.

### Invoices and Financial Summary

- Invoice records.
- Invoice status.
- Refund records.
- Revenue summary.
- Pending amounts.
- Confirmed payments.
- Refund totals.

Financial metrics must have explicit definitions.

Do not invent accounting or tax rules.

---

## 8. Credits & Usage

### 8.1 Credits Overview

- Total granted Credits.
- Total consumed Credits.
- Current customer balances.
- Transaction volume.
- Relevant exceptions.

### 8.2 Credit Ledger

Display:

- Transaction ID.
- Account.
- Transaction type.
- Amount.
- Previous balance.
- Resulting balance.
- Related job or operation.
- Timestamp.
- Reason.

### 8.3 Administrative Adjustments

Authorized actions:

- Grant compensatory Credits.
- Correct eligible accounting discrepancies.
- Review disputed transactions.

Every adjustment must:

- Use the existing ledger service.
- Be recorded as a new transaction.
- Include a mandatory reason.
- Record the administrator.
- Record previous and resulting balances.
- Prevent unauthorized balance manipulation.

Never directly overwrite a user’s balance.

### 8.4 Usage and Cost

Separate:

- Customer Credits.
- Provider consumption.
- Actual provider cost.
- Estimated provider cost.
- Unconfirmed cost records.

Never present Credits as equivalent to actual provider costs.

---

## 9. AI & Operations

This module combines AI provider administration and operational monitoring.

### 9.1 AI Providers

Display:

- Provider name.
- Supported capabilities.
- Connection status.
- Service status.
- Usage.
- Cost information.
- Error indicators.

Actions:

- Configure supported provider settings.
- Enable or disable supported integrations.
- Review provider failures.
- Monitor usage limits.
- Review provider costs.

Secrets must never be displayed in plaintext.

### 9.2 Generation Jobs

Views:

- All jobs.
- Running.
- Completed.
- Failed.
- Delayed.
- Interrupted, where supported.

Job details:

- Job identifier.
- User.
- Generation type.
- Provider.
- Job status.
- Creation time.
- Completion time.
- Error details.
- Related Credit transactions.

Actions:

- Inspect.
- Retry when safe and supported.
- Review failure.
- Escalate operational issues.

Retry operations must be idempotent or protected against duplicate billing and duplicate execution.

### 9.3 System Health

Monitor available integrations and infrastructure:

- Application.
- Database.
- File storage.
- Background workers.
- AI providers.
- Payment integrations.
- Scheduled jobs.

Display actual health checks, last successful checks, and failure details.

### 9.4 Operational Logs

Provide filtered access to relevant application and integration events.

Do not expose passwords, API keys, tokens, or unnecessary personal information.

---

## 10. Analytics & Reports

### User Analytics

- Registration growth.
- Active users.
- Retention, when measurable.
- Subscription conversion, when measurable.

### Subscription Analytics

- Plan distribution.
- New subscriptions.
- Renewals.
- Cancellations.
- Expirations.

### Financial Analytics

- Confirmed revenue.
- Refunds.
- Payment failures.
- Provider costs.
- Contribution margin, only when reliable cost and revenue data exist.

### Usage Analytics

- Image generation volume.
- Video generation volume.
- Usage by generation type.
- Credits consumption.
- Average provider cost per operation.

### Reporting Capabilities

- Date-range filtering.
- Relevant grouping and breakdowns.
- CSV export.
- Permission checks.
- Clear data timestamps.
- Explicit distinction between actual and estimated metrics.

---

## 11. Support Center

Provide a lightweight administrative support workspace.

Capabilities:

- View support requests.
- Search requests.
- Filter by status and priority.
- Link requests to customer accounts.
- Add internal notes.
- Change request status.
- Record resolutions.
- Track recurring problems.

Do not build an unnecessarily complex customer service or project management system.

---

## 12. Platform Settings

### General Settings

- Platform identity.
- Logo and branding assets.
- Public platform information.

### Localization

- Arabic.
- English.
- Date and number formatting.
- Locale settings.

### Email

- Supported email configuration.
- Templates.
- Delivery status, where available.

### Notifications

- Platform notification settings.
- Administrative alert preferences.

### Integrations

- External integration settings.
- Connection configuration.
- Integration status.

### Storage

- Supported storage configuration.
- Storage health and usage information.

### Policies

- Terms.
- Privacy policy.
- Relevant platform policies.

### Feature Controls

Use feature flags only where supported by the existing architecture.

Changes affecting customer access must be explicit, validated, and logged.

---

## 13. Security & Administration

### 13.1 Authentication

- Secure administrative login.
- Multi-factor authentication (MFA).
- Strong session management.
- Secure logout.
- Session expiration.
- Reauthentication for sensitive actions.

### 13.2 Authorization

Implement backend-enforced role-based access control.

The Owner has full permissions.

Future administrators receive explicitly assigned permissions.

### 13.3 Audit Log

Record important administrative operations:

- Administrator identity.
- Action.
- Target entity.
- Timestamp.
- Previous value where appropriate.
- New value where appropriate.
- Reason.
- Outcome.

Audit records must be protected from unauthorized alteration or deletion.

### 13.4 Sensitive Operations

Require appropriate security confirmation for:

- Account deactivation.
- Subscription cancellation.
- Financial refunds.
- Credit adjustments.
- Provider configuration changes.
- Security setting changes.
- Administrator permission changes.
- Owner account changes.

Use MFA reauthentication or equivalent step-up authentication according to risk.

### 13.5 Secrets Management

- Never expose API secrets.
- Never return credentials in frontend responses.
- Use secure backend secret storage.
- Support safe secret rotation where infrastructure allows it.
- Never write secrets to logs.

---

## 14. Bilingual UX and Localization

The entire administrative interface must support Arabic and English.

### Arabic

- Full RTL layout.
- Correct navigation direction.
- Correct alignment.
- Appropriate typography.
- Proper table and form behavior.

### English

- Full LTR layout.
- Correct component behavior.

### Language Switching

- Easily accessible language switcher.
- Preserve the current page and relevant navigation state when possible.
- Persist the administrator’s preference.
- Translate every interface element, validation message, notification, and system status.

### Localization Details

- Locale-aware dates.
- Locale-aware number formatting.
- Currency formatting based on configured currency.
- Correct handling of mixed Arabic and English identifiers.
- Email addresses and technical identifiers must remain readable.
- Avoid hardcoded interface strings.

---

## 15. Responsive Design

Support:

- Desktop.
- Tablet.
- Mobile.

Desktop is the primary administrative workspace.

Mobile must support essential operational tasks, security notifications, account review, and responsive navigation.

Complex tables must adapt through responsive layouts rather than becoming unusable horizontally.

High-risk operations must retain their security confirmation requirements on every device.

---

## 16. Global UX Components and States

Every applicable screen must support:

- Loading.
- Empty state.
- Error state.
- Success feedback.
- Validation errors.
- Permission denied.
- Unavailable integration.
- Partial data.
- Confirmation of sensitive actions.

### Interaction Principles

- Keep actions close to their relevant records.
- Avoid unnecessary navigation.
- Avoid excessive modal dialogs.
- Use clear confirmation screens for destructive operations.
- Preserve search and filtering context.
- Provide clear success and failure outcomes.
- Avoid duplicate controls.
- Avoid unnecessary administrative screens.

### Data Integrity

Never display sample or mock data as real operational data.

When information is unavailable, show an explicit unavailable or not configured state.

---

## 17. Complete Administrative User Flows

The design must cover the following workflows:

1. Administrator login and MFA.
2. Dashboard review.
3. Search and inspect a user.
4. Suspend and restore an account.
5. Review account subscription.
6. Create and configure a plan.
7. Review a subscription exception.
8. Extend or cancel a subscription.
9. Inspect a failed payment.
10. Initiate and verify a refund.
11. Review a Credit transaction.
12. Grant compensatory Credits.
13. Inspect a failed generation job.
14. Retry an eligible job safely.
15. Review AI provider health.
16. Review operational costs.
17. Export a financial report.
18. Resolve a support request.
19. Change platform settings.
20. Review audit logs.
21. Configure future administrator permissions.
22. Review and secure the Owner account.

Each workflow must specify:

- Entry point.
- Required permissions.
- Required data.
- User actions.
- Validation.
- Confirmation.
- Backend operation.
- Success state.
- Failure state.
- Audit requirements.

---

## 18. Backend and Existing Architecture Integration

Before implementation, inspect the actual project architecture.

Verify:

- Authentication.
- User accounts.
- Brand relationships.
- Credit ledger.
- Generation jobs.
- AI provider integrations.
- File storage.
- Database models.
- Existing APIs.
- Existing frontend components.
- Localization.
- Security controls.

### Capability Classification

Classify each administrative capability as:

A. Existing and ready for integration.

B. Existing but requires completion.

C. Not implemented and requires development.

D. Depends on an external integration.

E. Requires an unresolved product or commercial decision.

### Mandatory Rules

- Reuse existing services.
- Do not duplicate business logic.
- Do not introduce parallel ledgers.
- Do not bypass authorization.
- Do not invent subscription prices or plan limits.
- Do not invent provider capabilities.
- Do not expose unavailable functionality as operational.
- Do not change customer-facing product scope.
- Do not perform opportunistic refactoring outside approved scope.

The administrative UI must reflect actual backend capabilities.

---

## 19. Acceptance Criteria

VARIOM Admin must not be considered complete merely because its frontend renders successfully.

### UX Acceptance

- All approved screens are implemented.
- All navigation works.
- Arabic and English are complete.
- RTL and LTR are correct.
- Responsive layouts work.
- Empty, loading, error, and success states are implemented.
- All buttons have real supported actions.

### Functional Acceptance

- User management works against real backend data.
- Subscription operations work according to approved policies.
- Financial operations are connected to supported payment integrations.
- Credit adjustments use the ledger.
- AI provider monitoring uses actual integration status.
- Job management reflects real job states.
- Reports use traceable data.
- Support operations work where the support backend exists.

### Security Acceptance

- Administrative access is isolated.
- MFA is enforced for the Owner.
- Backend authorization is tested.
- Sensitive operations require appropriate confirmation and reauthentication.
- Owner protections work.
- Audit records are created correctly.
- Secrets are not exposed.
- Unauthorized operations are rejected.

### Quality Acceptance

- TypeScript checks pass.
- Lint passes.
- Production build succeeds.
- Relevant automated tests pass.
- Critical administrative workflows are tested.
- Responsive browser testing is performed.
- No critical security or data-integrity defects remain.

### Final Delivery

Provide a clear implementation report identifying:

- Completed capabilities.
- Verified capabilities.
- Partially implemented capabilities.
- Blocked capabilities.
- External integration dependencies.
- Unresolved commercial decisions.
- Security limitations.
- Test evidence.

Do not claim full operational readiness when essential integrations or backend capabilities remain unavailable.

---

## 20. Final Design Philosophy

VARIOM Admin must provide complete platform control without unnecessary complexity.

The Owner should be able to understand the current platform condition, identify problems, inspect relevant records, and execute authorized actions with minimal navigation.

Security must be built into the architecture and workflows, not added as a visual layer.

Existing systems must be reused.

Unresolved commercial and technical requirements must be identified rather than guessed.

The final outcome must be a reliable, bilingual, secure, and genuinely operational administration center.
