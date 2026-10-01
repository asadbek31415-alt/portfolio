# Prepnik Records

## Problem

Course purchase records need to distinguish a sale from a payment. Deferred payments, unknown prices, and refunds make a simple spreadsheet total misleading.

## Implementation

The application uses a SQLite database as the authoritative record, with an Express dashboard and an owner-only Telegram bot. Records include purchase dates, payment events, access status, refunds, and audit history.

The reporting logic assigns a payment to its payment date and a refund to its refund date. Unknown amounts stay unknown. Currency is stored in integer UZS and displayed in thousands of UZS. Repeated confirmation requests do not create duplicate purchases.

The application also provides due-date reminders, Excel and JSON exports, and database backups. Import tools retain unclear historical records for review instead of silently guessing values.

## Engineering decisions

- Separate purchase and payment events to support meaningful reporting.
- Preserve history when recording refunds and corrections.
- Require confirmation for repeated purchases and make confirmation idempotent.
- Restrict Telegram administration to the configured owner in a private chat.

## Verification and limits

The project includes unit/integration tests for cash timing, refunds, unknown prices, idempotency, authentication, imports, and mock Telegram flows, plus browser UI tests using isolated data. Those tests were not rerun as part of preparing this portfolio. Live Telegram delivery and deployed recovery require separate verification.

## Relevance to a payments hackathon

This project demonstrates payment-record modeling, explicit confirmation flows, and understandable financial reporting. It does not implement Bitcoin transactions, self-custodial wallets, or local AI.

Source code and real records remain private.
