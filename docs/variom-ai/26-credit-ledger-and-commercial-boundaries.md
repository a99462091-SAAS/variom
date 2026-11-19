# VARIOM — Credit Ledger & Commercial Boundaries

**Version:** 1.0 | **Status:** NORMATIVE DRAFT — accounting semantics only | **Authority:** Documents 19–25; VAR-OD-001 and VAR-OD-007.

## 1. Purpose and exclusions
Defines safe credit accounting for a future authorized implementation. It does not approve prices, packages, subscriptions, payment rails, top-ups, taxes, currencies, refunds to cash or enforceable brand entitlements. Starter / Pro / Agency = 1 / 3 / up to 8 brands remains presentation-only.

## 2. Core principles
1. The ledger is the source of truth. Balance is derived from immutable ledger facts.
2. No client or UI action can directly change a balance.
3. A billable operation requires a current server-derived quote and explicit confirmation.
4. Reserve before dispatch; never dispatch if reservation fails.
5. Settle actual verified usage once; release unused reservation.
6. Every mutation is idempotent and traceable to an operation.
7. Unknown provider outcomes remain unresolved until reconciled; do not charge twice or release a hold while external usage may have occurred.
8. Preview/mock/idea-only operations do not mutate the real ledger unless an independently approved, explicitly priced rule says otherwise.
9. No hardcoded illustrative cost may be displayed as live cost.

## 3. Logical records
- **Credit Account:** one logical account per VARIOM account.
- **Credit Quote:** operation-specific amount, unit, quantity, cost basis/version, creation/expiry and status.
- **Reservation:** accepted hold linked to quote and operation.
- **Ledger Entry:** append-only signed accounting fact; correction uses a compensating entry, never rewriting history.
- **Settlement:** actual verified usage, released remainder, evidence and terminal reconciliation.
- **Pricing/Cost Basis Evidence:** source/version, effective period, provider/model, unit conversion and approval state. No unsupported cost basis is usable for a live quote.

## 4. Operation lifecycle
1. **Quote:** validate inputs/capability and compute quote on server using an approved current cost basis. If no trustworthy basis exists, billable operation is unavailable; do not guess.
2. **Present:** show amount/unit and material assumptions before confirmation.
3. **Confirm:** verify quote is unexpired and unchanged; require explicit user confirmation.
4. **Reserve:** append reservation/hold ledger fact atomically with operation confirmation.
5. **Dispatch:** only after durable reservation and idempotency record.
6. **Settle:** use verified actual usage; append settlement debit and release unused hold.
7. **Failure before usage:** release full hold.
8. **Partial usage/failure:** debit verified usage, release unused portion; retain evidence.
9. **Unknown usage:** keep reservation in reconciliation state; no blind retry, final debit or release until resolved.
10. **Correction:** append compensating ledger facts with reason and audit reference.

## 5. Balance semantics
Available balance = posted credits/debits minus active reservations, using one explicitly defined credit unit. Reserved balance and available balance must be distinguishable internally and wherever shown. The UI may show only the real available balance if the backend can calculate it consistently. No client-calculated balance is authoritative.

A negative available balance is prohibited unless a later explicit owner-approved commercial policy defines otherwise. No overdraft is inferred.

## 6. Idempotency and concurrency
- Every quote confirmation, reservation, settlement, release and compensation has a unique idempotency key and operation reference.
- Concurrent confirmations against the same available balance must serialize or use an equivalent atomic invariant.
- Duplicate provider callbacks cannot create duplicate settlements.
- Reservation expiry is not automatic release if provider work may have started or outcome is unknown.
- Reconciliation records preserve provider usage evidence and ledger references.

## 7. Failure matrix
| Situation | Required outcome |
|---|---|
| Quote unavailable/stale | No hold, no dispatch; request a fresh quote |
| Insufficient balance | No hold, no dispatch; clear user message |
| User cancels before dispatch | Release full reservation |
| Provider fails before billable usage | Release full reservation after verified no-usage outcome |
| Provider partially consumes | Settle verified usage; release remainder |
| Provider timeout/unknown outcome | Reconcile; retain hold; prevent duplicate dispatch/charge |
| Output persistence fails after provider success | Preserve operation for recovery; settle only according to verified usage; do not claim completed output |
| Duplicate confirmation/callback | Return existing outcome; no duplicate ledger mutation |
| Pricing evidence expires | Disable quote/dispatch until refreshed |

## 8. Idea and preview boundary
Idea suggestions, template previews and illustrative reference imagery are not media generation. They do not consume generation credits by assumption. A future explicit owner-approved pricing rule is required before charging for such operations.

## 9. Commercial deferrals
- Package names/counts do not imply a commercial entitlement.
- Exact launch market, currency, prices, taxes, payment provider, subscription, top-up and enforceable plan limits remain deferred under VAR-OD-007.
- The system must not display a checkout or claim a payment was received until a verified payment integration and separate owner authorization exist.
- Production ledger funding/payment reconciliation is a separate commercial/legal gate.

## 10. Acceptance criteria
- No generation before quote, confirmation and reservation.
- No double charge or duplicate settlement under retries/concurrency.
- Actual usage and unused reservation reconcile exactly once.
- Unknown provider outcome cannot silently release or charge.
- Preview/mock/idea flows cannot mutate real credits.
- No unsupported price, currency, subscription or payment assumption.
