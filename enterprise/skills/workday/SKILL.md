---
name: workday
description: Workday HCM - lets an agent retrieve employee records, leave balances, onboarding task status, job history, and compensation data in read-only mode to support HR and onboarding workflows.
metadata: {"openclaw":{"requires":{"env":["WORKDAY_BASE_URL","WORKDAY_USERNAME","WORKDAY_PASSWORD","WORKDAY_TENANT"]}},"primaryEnv":"WORKDAY_BASE_URL"}
---

# Workday

## What it is
Workday is the leading cloud Human Capital Management (HCM) suite, used by large enterprises to manage the full employee lifecycle from recruiting through offboarding. In this segment, HR and onboarding agents use Workday as the authoritative source for employee records, leave balances, job history, and onboarding checklist status. All agent access is read-only and scoped to the information needed to answer employee questions or validate provisioning prerequisites.

## When to use this skill
- Looking up an employee's leave balance before answering a time-off question
- Retrieving a new hire's start date, department, and manager for onboarding coordination
- Checking the status of onboarding tasks assigned to a new employee
- Confirming job title, cost center, or reporting structure for an access provisioning request
- Retrieving job history for an employee to answer a compensation or tenure question

## Credentials
This skill authenticates using variables from `~/.openclaw/.env` (template: `.env.example` at the config root). Required variables:
- `WORKDAY_BASE_URL` - tenant base URL (e.g. `https://wd3-impl-services1.workday.com/ccx/service/mycompany`)
- `WORKDAY_USERNAME` - integration system user (ISU) username
- `WORKDAY_PASSWORD` - integration system user password
- `WORKDAY_TENANT` - Workday tenant ID

## Key operations
- `GET /Human_Resources/v43.0/workers/{worker_id}` - retrieve worker profile
- `GET /Human_Resources/v43.0/workers?Search_Text=...` - search workers by name or email
- `GET /Absence_Management/v43.0/leave_requests_for_worker` - fetch leave balances
- `GET /Talent/v43.0/job_history/{worker_id}` - retrieve job change history
- `GET /Staffing/v43.0/workers/{worker_id}/worker_status` - get employment status

## Notes
- Workday uses SOAP/XML as the primary API protocol (WWS); a REST-based API (Workday REST) is available for select domains.
- Always use an Integration System User (ISU) account with minimum necessary domain security permissions.
- PII fields (SSN, date of birth, bank details) must be excluded from agent-accessible security segments.
- Workday sandboxes (Implementation, Sandbox Preview) have separate tenant URLs; test against a non-production tenant.
- API versioning is date-based (v43.0); pin the version and update during Workday's bi-annual release window.
