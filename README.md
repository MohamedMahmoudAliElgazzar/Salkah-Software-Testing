# Salkah — Software Testing Portfolio

End-to-end **software testing** for a real-world Flutter mobile app: manual & exploratory testing, **API testing** with Postman, **JWT-secured** endpoints, and **Railway–MySQL** environment setup & monitoring. Includes defect log, reproducible steps, and before/after evidence.

## Table of Contents
- [Scope](#scope)
- [Stack](#stack)
- [Environment Setup & Monitoring](#environment-setup--monitoring)
- [Test Strategy](#test-strategy)
- [Key Test Scenarios](#key-test-scenarios)
- [API Testing](#api-testing)
- [Security Validation](#security-validation)
- [Defect Log (Samples)](#defect-log-samples)
- [Before / After Evidence](#before--after-evidence)
- [Regression & Version Control](#regression--version-control)
- [Repository Structure](#repository-structure)
- [Contact](#contact)

---

## Scope
- Functional & usability testing for core flows (auth, tracking, requests).
- API testing for data retrieval/update (Railway + MySQL backend).
- Basic performance sanity (response times, error handling).
- Security validation for auth/session (**JWT**).

## Stack
- **App:** Flutter (Android Studio)
- **APIs:** Node.js (Railway), **MySQL**
- **Testing:** Manual/Exploratory, **Postman**
- **VC:** GitHub

## Environment Setup & Monitoring
- Connected GitHub repo to **Railway** and linked **MySQL** instance.
- Monitored deployments & logs during test runs (failures, timeouts, DB connectivity).
- Validated env readiness before test execution.

## Test Strategy
- **Manual & Exploratory:** walk-through of primary user journeys.
- **Functional:** verify expected outputs & edge cases.
- **API Testing:** Postman collections for endpoints, negative tests, error codes.
- **Regression:** re-run critical paths after each fix/merge.

## Key Test Scenarios
- Authentication: signup/signin, invalid creds, token expiry/refresh.
- Requests/Tracking: create/read/update flows, permissions, state transitions.
- Input validation: client/server-side errors, SQL/XSS characters rejected.
- Network conditions: offline/slow responses (basic checks).

## API Testing
- Tool: **Postman**  
- Coverage: status codes, payload schemas, pagination/filters, error messages.
- Collections & env files:  
  `postman/collection.json` • `postman/env.sandbox.json`

## Security Validation
- **JWT** on protected endpoints (missing/invalid/expired).
- Rate-limit & CORS sanity checks.
- Documented vulnerabilities + recommended fixes in:  
  `docs/security/penetration-testing-report.pdf`

---

## Defect Log (Samples)
Use this template inside `docs/defects/`:

```
ID: ISS-001
Title: Login accepts expired JWT on app relaunch
Severity: High
Area: Auth
Build: v1.0.3
Steps to Reproduce:
  1) Login and obtain JWT
  2) Wait past expiry, relaunch app
  3) Access /me endpoint
Expected:
  401 Unauthorized
Actual:
  200 OK
Evidence:
  assets/before-after/issue-001-before.png
Fix Summary:
  Validate exp on app start; force re-auth
Verification:
  assets/before-after/issue-001-after.png
Status: Closed
```

---

## Before / After Evidence

**ISS-001 — Logo and the Name of the Application**  
Before:  
![ISS-001 Before](assets/before-after/ISS-001%20Before.jpg))  
After:  
![ISS-001 After]([assets/before-after/ISS-001%20After.jpg))

**ISS-002 — button issue**  
Before:  
![ISS-002 Before](assets/before-after/ISS-002%20Before.jpg))  
After:  
![ISS-002 After](assets/before-after/ISS-002%20After.jpg))

---

## Regression & Version Control
- Opened issues/PRs for each fix, re-executed critical paths post-merge.
- Tagged releases: `v1.0.3`, `v1.0.4`… with notes in `CHANGELOG.md`.

## Repository Structure
```
.
├─ postman/
│  ├─ collection.json
│  └─ env.sandbox.json
├─ docs/
│  ├─ defects/
│  │  ├─ ISS-001.md
│  │  └─ ISS-002.md
│  └─ security/
│     └─ penetration-testing-report.pdf
├─ assets/
│  ├─ before-after/
│  │  ├─ issue-001-before.png
│  │  ├─ issue-001-after.png
│  │  └─ ...
│  └─ demo/
│     └─ flow-001.gif
└─ README.md
```

## Contact
**Mohamed Mahmoud Elgazzar**  
mohamed.mahmoud.elgazzar@gmail.com • +971-509650093  
LinkedIn: linkedin.com/in/mohamed-mahmoud-680040235
