# EasyRide Rental OS Architecture

EasyRide Rental OS is a motorcycle rental management platform.

The system consists of three main components:

1. Public Booking App  
2. Staff Console  
3. Automation Engine  

---

## Public Booking App

Used by hirers to:

- browse available vehicles
- create bookings
- make payments
- receive release tokens
- complete self-return

---

## Staff Console

Used by internal staff to manage:

- vehicle fleet
- hirer accounts
- bookings
- payments
- servicing
- collections

---

## Automation Engine

Handles automated workflows such as:

- overdue detection
- late fee calculation
- release token generation
- servicing reminders
- risk alerts

---

## System Modules

The repository will be structured as:

apps/
- public-booking
- staff-console

services/
- booking-engine
- payment-engine
- deposit-ledger
- automation-engine

core/
- auth
- rbac
- audit

data/
- prisma schema
- migrations

agents/
- collections-agent
- release-agent
- risk-agent
