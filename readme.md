# Integration Mock Platform

A lightweight **integration mock server** designed for QA Engineers to test and automate  
**third-party integrations** (issue trackers, ALM tools, ITSM platforms, security tools)  
without maintaining real external environments.

This project supports:
- UI automation (Playwright, Cypress)
- API automation
- Integration & contract testing
- Local development and demos

---

## Why This Project Exists

In real QA environments, testing integrations with systems like **Jira, Azure Boards,
GitHub, ServiceNow, DefectDojo**, etc. is often:

- Costly to maintain
- Dependent on credentials and external teams
- Unstable for automation
- Risky for test data

This platform:
- Mocks real-world integration APIs
- Provides predictable behavior
- Enables end-to-end testing
- Eliminates external dependencies
- Is easy to extend with new integrations

---

## Tech Stack & Rationale

| Technology | Purpose |
|-----------|--------|
| Node.js | Fast, lightweight runtime |
| Express | Minimal HTTP server |
| TypeScript | Type safety and scalability |
| ts-node-dev | Fast local development |
| REST APIs | Matches real integration contracts |
| Modular Routers | One router per integration |

---

## Getting Started

```bash
npm install
npm run dev
```

Server runs on:
```
http://localhost:4000
```
