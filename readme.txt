INTEGRATION MOCK PLATFORM
=========================

A lightweight integration mock server designed for QA Engineers to test and
automate third-party integrations (issue trackers, ALM tools, ITSM, security
platforms) without maintaining real external environments.

Ideal for:
- UI automation (Playwright, Cypress, etc.)
- API automation
- Integration & contract testing
- Local development and demos


WHY THIS PROJECT EXISTS
-----------------------

In real-world QA environments, testing integrations with systems like Jira,
Azure Boards, GitHub, ServiceNow, DefectDojo, etc. is often:

- Costly to maintain
- Hard to stabilize
- Dependent on external teams or credentials
- Risky for test data

This mock platform:
- Simulates real integration APIs
- Provides predictable and controllable behavior
- Enables end-to-end flow testing
- Eliminates dependency on real tools
- Is easy to extend with new integrations


TECH STACK & RATIONALE
---------------------

Node.js
- Lightweight and fast
- Perfect for API mocking

Express
- Minimal and flexible HTTP server
- Easy routing per integration

TypeScript
- Type safety
- Scales well for large mock platforms
- Enterprise-ready

ts-node-dev
- Fast local development
- Automatic reload on changes

REST APIs
- Matches real integration contracts

Modular Router Design
- Each integration isolated
- Easy to add/remove tools


PROJECT STRUCTURE
-----------------

integration-mock-platform/
│
├── src/
│   ├── app.ts               # Express app configuration
│   ├── server.ts            # Server bootstrap
│   ├── routes/
│   │   ├── index.ts         # Central router
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
│   │
│   └── types/               # Optional shared interfaces
│
├── package.json
├── tsconfig.json
└── README.txt


GETTING STARTED
---------------

1. Clone the repository

   git clone https://github.com/your-username/integration-mock-platform.git
   cd integration-mock-platform

2. Install dependencies

   npm install

3. Start the server

   npm run dev

Server runs on:
http://localhost:4000


AVAILABLE INTEGRATIONS & EXAMPLE REQUESTS
-----------------------------------------

NOTE: Responses are mocked. Only example requests are shown.


JIRA
----

POST /jira/issue

{
  "summary": "Login button not working",
  "description": "Clicking login does nothing",
  "priority": "High"
}


AZURE BOARDS
------------

POST /azureboards/workitem

{
  "title": "Checkout fails",
  "type": "Bug",
  "assignedTo": "qa@company.com"
}


GITHUB ISSUES
-------------

POST /github/issues

{
  "title": "Broken build",
  "body": "Pipeline fails on main branch",
  "labels": ["bug"]
}


GITLAB ISSUES
-------------

POST /gitlab/issues

{
  "title": "Registration error",
  "description": "500 error on submit"
}


BUGZILLA
--------

POST /bugzilla/bug

{
  "summary": "Search returns empty results",
  "severity": "major"
}


FOGBUGZ
-------

POST /fogbugz/case

{
  "title": "Checkout page crashes",
  "description": "Null reference exception",
  "priority": "High"
}


BITBUCKET
---------

POST /bitbucket/issues

{
  "title": "Merge conflict",
  "content": "Conflicts in payment module"
}


PAGERDUTY
---------

POST /pagerDuty/incidents

{
  "title": "Production outage",
  "urgency": "high"
}


REDMINE
-------

POST /redmine/issues

{
  "subject": "Email service down",
  "priority": "Urgent"
}


UNFUDDLE
--------

POST /unfuddle/tickets

{
  "title": "Broken API endpoint",
  "description": "500 error"
}


SHORTCUT
--------

POST /shortcut/stories

{
  "name": "Improve login performance",
  "story_type": "feature"
}


YOUTRACK
--------

POST /youtrack/issues

{
  "summary": "UI alignment issue",
  "priority": "Medium"
}


FRESHSERVICE
------------

POST /freshService/tickets

{
  "subject": "VPN access issue",
  "category": "IT Support"
}


KENNA SECURITY
--------------

POST /kenna/vulnerabilities

{
  "title": "SQL Injection",
  "severity": "Critical"
}


PIVOTAL TRACKER
---------------

POST /pivotalTracker/story

{
  "title": "Login fails on Safari",
  "storyType": "bug",
  "estimate": 2,
  "owner": "qa@company.com"
}


DEFECTDOJO (NETSPARKER SCAN IMPORT)
----------------------------------

POST /defectDojo/import-scan

{
  "scan_type": "Netsparker Scan",
  "engagement": 12,
  "verified": true,
  "active": true,
  "scan_date": "2025-01-10",
  "minimum_severity": "Low"
}


EXTENDING THE PLATFORM
---------------------

1. Create a new router under src/routes
2. Define mock endpoints
3. Register the router in routes/index.ts

No credentials, no real environments, no external dependencies.


FINAL NOTES
-----------

This platform is intentionally:
- Simple
- Predictable
- Easy to extend

It is not a full replacement for real integrations, but a powerful tool for:
- QA automation
- Integration testing
- Demos and local development
