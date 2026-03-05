# EasyRide Rental OS – Build Tasks

This file defines the development roadmap.

---

## P0 – Core System (Must exist first)

TASK-001  
Create authentication module.

Requirements:
- Hirer login
- Staff login
- Password hashing
- Session management

---

TASK-002  
Implement Role Based Access Control (RBAC).

Roles:
- HIRER
- OPS
- COLLECTIONS
- FINANCE
- MECHANIC
- ADMIN

RBAC must be enforced server-side.

---

TASK-003  
Create Audit Log system.

Requirements:
- append-only audit log
- track state changes
- track financial transactions

---

TASK-004  
Create Vehicle Registry.

Requirements:
- vehicle database table
- vehicle status
- staff CRUD interface

---

TASK-005  
Create Booking State Machine.

Booking states:

- DRAFT
- PENDING_PAYMENT
- CONFIRMED
- RELEASE_READY
- ACTIVE_RENTAL
- RETURN_PENDING
- COMPLETED
- OVERDUE
- DEFAULTED

Transitions must be validated.

---

TASK-006  
Create Deposit Ledger.

Requirements:
- DepositTransaction table
- support HOLD / DEDUCTION / REFUND
- compute balance dynamically

---

TASK-007  
Create Payment Records.

Requirements:
- booking payments
- payment method tracking
- payment status
