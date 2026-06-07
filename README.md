# Loan Servicing Loss Mitigation Suite

Loan servicing workflows, delinquency management, loss mitigation, borrower communication, compliance, and investor reporting.

**Buyer:** Mortgage servicers, banks, credit unions, fintech lenders

## Run

```bash
cd /Users/erolakarsu/external/projects/loan-servicing-loss-mitigation-suite
./start.sh
```

Open:

```text
http://127.0.0.1:5611
```

## Demo Logins

```text
admin@loan-servicing-loss-mitigation-suite.local / admin123
manager@loan-servicing-loss-mitigation-suite.local / manager123
analyst@loan-servicing-loss-mitigation-suite.local / analyst123
```

## Implemented Features

- Sidebar dashboard and module navigation
- Domain-specific workspaces: Servicing Portfolio, Delinquency Queue, Loss Mitigation, Borrower Communications, Foreclosure Referral, Servicing Compliance, Payment Processing, Investor Reporting
- Seeded persistent data with 15 records per domain module
- Login, roles, local persistent JSON store
- Create, edit, delete records
- Document metadata upload workflow
- Tasks, notifications, audit logs
- CSV exports for every table
- AI Center with OpenRouter-ready endpoint and local fallback
- Reports and print-ready summaries
- Smoke test for health, login, CRUD, and export

## Test

```bash
npm test
```

For production, replace demo auth with an identity provider, replace local JSON with a database, add durable file storage, and validate AI workflows against your compliance requirements.


## Production-Style Feature Upgrade

Added across the full 20-app batch:

- API-enforced RBAC sessions for Admin, Manager, and Analyst roles
- Authorization checks for write, delete, export, AI, admin, and job endpoints
- Optimistic record versioning with conflict protection
- Server-side validation for required operational fields
- Rules-based risk scoring per record and module-level domain analysis
- Integrations, automations, approvals, tasks, notifications, documents, and audit logs
- Due-notification scheduled job endpoint plus hourly runtime scheduler
- Backup, restore, and reset endpoints
- Readiness endpoint with deployment checks
- Security response headers for API/static responses
- Expanded smoke tests covering RBAC, versioned CRUD, backup, jobs, domain analysis, and export
