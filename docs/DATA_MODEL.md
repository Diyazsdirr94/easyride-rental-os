# EasyRide Rental OS – Data Model

This document defines the core database entities for EasyRide Rental OS.

---

## Hirer

Represents a customer renting a motorcycle.

Fields:

- id
- name
- phone
- license_number
- status
- created_at

---

## Vehicle

Represents a motorcycle in the fleet.

Fields:

- id
- plate_number
- make
- model
- year
- status
- gps_tracker_id
- created_at

Vehicle status examples:

- AVAILABLE
- RESERVED
- RENTED
- MAINTENANCE

---

## Booking

Represents a rental contract.

Fields:

- id
- hirer_id
- vehicle_id
- start_time
- end_time
- status
- created_at

Booking statuses follow a state machine.

Example states:

- DRAFT
- PENDING_PAYMENT
- CONFIRMED
- RELEASE_READY
- ACTIVE_RENTAL
- RETURN_PENDING
- COMPLETED
- OVERDUE
- DEFAULTED

---

## PaymentRecord

Tracks rental payments.

Fields:

- id
- booking_id
- amount
- method
- status
- created_at

---

## DepositTransaction

Tracks deposit ledger entries.

Fields:

- id
- hirer_id
- booking_id
- type
- amount
- reference
- created_at

Transaction types:

- HOLD
- DEDUCTION
- REFUND

---

## AuditLog

Tracks important system actions.

Fields:

- id
- entity_type
- entity_id
- action
- performed_by
- previous_value
- new_value
- created_at
