# Integration Mock Platform
No credentials, no real environments, no external dependencies.

A lightweight **integration mock server** designed for QA Engineers to test and automate  
**third-party integrations** (issue trackers, ALM tools, ITSM platforms, and security tools)  
without maintaining real external environments.

This project is suitable for:
- UI automation (Playwright, Cypress, etc.)
- API automation
- Integration & contract testing
- Local development and demos

---

## Why This Project Exists

In real-world QA environments, testing integrations with tools such as **Jira, Azure Boards, GitHub,
ServiceNow, DefectDojo**, and similar systems is often:

- Costly to maintain
- Dependent on credentials and external teams
- Unstable for automation
- Risky for test data

This platform solves these problems by:
- Mocking real-world integration APIs
- Providing predictable and controllable behavior
- Enabling end-to-end testing without external dependencies
- Allowing easy extension with new integrations

---

## Tech Stack & Rationale

| Technology | Why It Is Used |
|----------|----------------|
| Node.js | Lightweight, fast, and widely adopted |
| Express | Minimal and flexible HTTP server |
| TypeScript | Type safety and scalability |
| ts-node-dev | Fast development with auto-reload |
| REST APIs | Matches real integration contracts |
| Modular Routers | One router per integration for easy extensibility |

---

## Project Structure

```
integration-mock-platform/
├── src/
│   ├── app.ts
│   ├── server.ts
│   ├── routes/
│   │   ├── index.ts
│   │   ├── jira.ts
│   │   ├── azureBoards.ts
│   │   ├── github.ts
│   │   ├── gitlab.ts
│   │   ├── bugzilla.ts
│   │   ├── fogbugz.ts
│   │   ├── bitbucket.ts
│   │   ├── pagerDuty.ts
│   │   ├── redmine.ts
│   │   ├── unfuddle.ts
│   │   ├── shortcut.ts
│   │   ├── youtrack.ts
│   │   ├── freshService.ts
│   │   ├── kenna.ts
│   │   ├── pivotalTracker.ts
│   │   └── defectDojo.ts
│   └── types/
├── package.json
├── tsconfig.json
└── README.md
```

---

## Getting Started (From Scratch)

### 1. Clone the repository
```bash
git clone https://github.com/your-username/integration-mock-platform.git
cd integration-mock-platform
```

### 2. Install dependencies
```bash
npm install
```

### 3. Start the server
```bash
npm run dev
```

Server runs on:
```
http://localhost:4000
```

---

## Available Integrations & Example Requests

---

### Jira – Create Issue
```http
POST /jira/issue
Content-Type: application/json

{
  "fields": {
    "summary": "Login button not working",
    "description": "Clicking login does nothing",
    "issuetype": {
      "name": "Bug"
    },
    "priority": {
      "name": "High"
    }
  }
}

```

---

### Azure Boards – Create Work Item
```http
POST /azureboards/workitems
Content-Type: application/json

{
  "title": "Checkout fails",
  "type": "Bug",
  "assignedTo": "qa@company.com"
}
```

---

### GitHub – Create Issue
```http
POST /github/issues
Content-Type: application/json

{
  "title": "Broken build",
  "body": "Pipeline fails on main branch",
  "labels": ["bug"]
}
```

---

### GitLab – Create Issue
```http
POST /gitlab/issue
Content-Type: application/json

{
  "title": "Registration error",
  "description": "500 error on submit"
}
```

---

### Bugzilla – Create Bug
```http
POST /bugzilla/bug
Content-Type: application/json

{
  "summary": "Search returns empty results",
  "product": "WebApp",
  "component": "Search",
  "severity": "major"
}

```

---

### FogBugz – Create Case
```http
POST /fogbugz/case
Content-Type: application/json

{
  "title": "Checkout page crashes",
  "description": "Null reference exception",
  "priority": "High"
}
```

---

### Bitbucket – Create Issue
```http
POST /bitbucket/issue
Content-Type: application/json

{
  "title": "Merge conflict",
  "content": "Conflicts in payment module"
}
```

---

### PagerDuty – Create Incident
```http
POST /pagerDuty/incident
Content-Type: application/json

{
  "title": "Production outage",
  "urgency": "high"
}
```

---

### Redmine – Create Issue
```http
POST /redmine/issue
Content-Type: application/json

{
  "subject": "Email service down",
  "priority": "Urgent"
}
```

---

### Unfuddle – Create Ticket
```http
POST /unfuddle/ticket
Content-Type: application/json

{
  "title": "Broken API endpoint",
  "description": "500 error"
}
```

---

### Shortcut – Create Story
```http
POST /shortcut/story
Content-Type: application/json

{
  "name": "Improve login performance",
  "story_type": "feature"
}
```

---

### YouTrack – Create Issue
```http
POST /youtrack/issues
Content-Type: application/json

{
  "summary": "UI alignment issue",
  "priority": "Medium"
}
```

---

### FreshService – Create Ticket
```http
POST /freshService/ticket
Content-Type: application/json

{
  "subject": "VPN access issue",
  "category": "IT Support"
}
```

---

### Kenna – Create Vulnerability
```http
POST /kenna/vulnerability
Content-Type: application/json

{
  "title": "SQL Injection",
  "severity": "Critical"
}
```

---

### Pivotal Tracker – Create Story
```http
POST /pivotalTracker/story
Content-Type: application/json

{
  "title": "Login fails on Safari",
  "storyType": "bug",
  "estimate": 2,
  "owner": "qa@company.com"
}
```

---

### DefectDojo – Import Netsparker Scan
```http
POST /defectDojo/import-scan
Content-Type: application/json

{
  "scan_type": "Netsparker Scan",
  "engagement": 12,
  "verified": true,
  "active": true,
  "scan_date": "2025-01-10",
  "minimum_severity": "Low"
}
```

---

## Extending the Platform

1. Create a new router under `src/routes`
2. Define mock endpoints
3. Register the router in `src/routes/index.ts`

---

## Final Notes


It is not meant to fully replicate real APIs, but to support QA automation, Integration testing and Local development
