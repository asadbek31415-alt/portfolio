# Algorithm & Programming I Mini App

## Problem

Students need a single place to access course material and practice C programming, while course administrators need to control access through Telegram.

## Implementation

The application combines a Next.js / React interface with a Telegraf bot. Course content is organized into theory, practice, code, and installation sections. Production course routes require a verified Telegram Mini App session.

A server API proxies C execution to Judge0 so students can receive real compiler errors and execution output. Bot commands support granting and removing access, user lookup, announcements, and administration.

## Engineering decisions

- Verify the Telegram session before serving protected learning content.
- Use a server endpoint for compiler integration.
- Persist access records with SQLite via sql.js.
- Keep the variables study panel's scope explicit: it is a learning helper, not a full runtime debugger.

## Status and limits

This write-up is based on the project's local README and package manifest. It does not assert a live deployment or independently verified production behavior.

Source code and protected learning material remain private.
