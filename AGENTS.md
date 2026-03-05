# EasyRide Rental OS – AI Agent Instructions

This repository contains the source code for EasyRide Rental OS.

The system consists of three major parts:

1. Public Booking App
2. Staff Console
3. Automation Engine

Core design principles:

- Booking lifecycle must follow a strict state machine.
- All financial transactions must use a ledger system.
- All important actions must write to the audit log.
- Role based access control must be enforced server-side.
- Release tokens must be hashed, single-use, and time-limited.

Tech stack:

Frontend
- Next.js
- Tailwind

Backend
- Node.js
- Express

Database
- PostgreSQL
- Prisma ORM

Important rule:

AI agents must always read documentation inside `/docs` before writing code.
