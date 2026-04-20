# Acme Web Banking

Acme Web Banking is the browser-based banking experience for customers who prefer to manage their accounts from a desktop or laptop browser.

## Overview

The application focuses on everyday banking tasks with a responsive interface, strong accessibility standards, and integration with the broader Acme account and authentication services.

## Key Features

- Secure sign-in and session management
- Dashboard view for balances and recent activity
- Internal transfers and payment workflows
- Transaction history and account search
- Card and profile management
- Support and contact entry points

## Suggested Stack

- Modern frontend framework such as React or Vue
- TypeScript
- Design system components and accessibility checks
- API integration with Acme backend services
- Browser-based test automation

## Repository Layout

- `.github/workflows/` - CI and automation workflows
- `src/` - application source code
- `public/` - static assets
- `tests/` - unit, component, and end-to-end tests
- `docs/` - UX notes, release guidance, and service references

## Local Development

Typical local setup includes:

1. Install dependencies.
2. Start the frontend development server.
3. Run tests and linting before creating a pull request.
4. Validate the app in at least one modern desktop browser.

## Environment Notes

The frontend is expected to use environment-specific API endpoints for local, staging, and production. No secrets should be stored in the repository.

## Automation

This repository includes a DevXP analysis workflow that runs on pushes to `main` and publishes repository metrics for internal reporting.

## Contributors
@peter-gregory
@erlich-bachman