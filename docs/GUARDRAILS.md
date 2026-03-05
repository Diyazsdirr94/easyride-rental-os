# EasyRide Rental OS – System Guardrails

These rules must always be enforced in the system.

---

## Booking State Machine

Bookings must follow the allowed lifecycle transitions.

Allowed transitions:

DRAFT → PENDING_PAYMENT  
PENDING_PAYMENT → CONFIRMED  
CONFIRMED → RELEASE_READY  
RELEASE_READY → ACTIVE_RENTAL  
ACTIVE_RENTAL → RETURN_PENDING  
RETURN_PENDING → COMPLETED  
ACTIVE_RENTAL → OVERDUE  
OVERDUE → DEFAULTED

State transitions must be validated in the service layer.

---

## Financial Integrity

All financial movements must be recorded in ledger tables.

Deposit balances must never be stored as a simple field.

Instead, balances must be derived from DepositTransaction records.

---

## Audit Logging

All important actions must generate an audit log entry.

Examples:

- booking status changes
- payment creation
- deposit deductions
- vehicle status updates

Audit logs must be append-only.

---

## Role Based Access Control

Sensitive actions must require specific roles.

Examples:

- Only FINANCE may process refunds
- Only OPS may create release tokens
- Only ADMIN may override booking states

RBAC must be enforced server-side.

---

## Release Tokens

Release tokens must follow these rules:

- token must be single-use
- token must expire
- token must be stored as a hash
- plaintext tokens must never be stored
