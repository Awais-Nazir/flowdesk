# Discovery Notes

**Project:** FlowDesk
**Client:** Zenith Retail Group
**Primary Contact:** Farhan Malik (Operations Director)
**Prepared By:** Development Team
**Status:** Discovery Completed
**Last Updated:** 2026-08-02

---

# Purpose

This document contains raw findings gathered during client discovery meetings.

It serves as the primary source of truth for business understanding before requirements engineering begins. Unlike the Product Discovery Document (PDD), this document intentionally preserves meeting observations, client statements, inferred insights, and outstanding questions.

---

# Discovery Timeline

| ID | Topic | Status |
|----|-------|--------|
| DM-01 | Business Overview & Current Challenges | ✅ Completed |
| DM-02 | Attendance & Leave Workflow | ✅ Completed |
| DM-03 | Assets, Roles & Reporting | ✅ Completed |
| DM-04 | Solution Validation | ✅ Completed |

---

# DM-01 — Business Overview

## Objective

Understand the client's business, organizational structure, operational challenges, and overall goals before discussing software.

---

## Business Overview

### Company

- Zenith Retail Group
- Six retail branches
- Small Head Office

### Business Type

Retail chain selling:

- Home appliances
- Electronics
- Furniture

---

## Organization Structure

```
Operations Director

├── HR Coordinator
├── Finance
│
├── Branch Manager
│      ├── Assistant Manager
│      └── Employees
```

---

## Stakeholders

| Stakeholder | Role |
|------------|------|
| Operations Director | Overall operational oversight |
| HR Coordinator | Attendance, payroll preparation, HR |
| Finance | Payroll & finance |
| Branch Manager | Daily branch operations |
| Assistant Manager | Supports branch operations |
| Employee | End user |

---

## Validated Business Problems

- Paper-based attendance
- Paper-based leave requests
- Manual approval processes
- Asset tracking through notebooks
- Attendance disputes
- Payroll delays
- Lost records
- Limited visibility across branches
- Heavy reliance on WhatsApp
- Multiple manual data-entry steps

---

## Client Goals

The client wants FlowDesk to:

- Reduce manual administration
- Increase transparency
- Improve accountability
- Reduce operational disputes
- Improve visibility across branches
- Replace scattered paper-based processes

---

## Internal Observations (Team)

> These are observations made by the development team and **not confirmed client requirements**.

- Biggest business issue is accountability rather than missing features.
- Most operational problems originate from paper-based workflows.
- Client prioritizes operational efficiency over advanced reporting.
- Client values trust and traceability.

---

# DM-02 — Attendance & Leave

## Attendance Workflow (Current)

Employee signs paper register

↓

Assistant Manager (rarely validates)

↓

Branch Manager manually calculates weekly attendance

↓

Attendance summary created (paper or Excel)

↓

Sent to HR through WhatsApp

↓

HR manually re-enters attendance

↓

Payroll preparation

---

## Attendance Pain Points

- Handwriting errors
- Missing signatures
- Manual hour calculation
- Duplicate data entry
- Poor auditability
- Payroll disputes
- Time-consuming reconciliation

---

## Leave Workflow (Current)

Employee requests leave verbally or via paper

↓

Branch Manager reviews

↓

If leave ≥ 3 days

↓

Head Office approval required

↓

Manager records approval (inconsistently)

↓

Employee informed verbally

---

## Leave Pain Points

- Verbal approvals
- Lost paperwork
- No approval history
- No request status
- Difficult dispute resolution

---

## Business Rules Identified

Validated:

- Leave of 1–2 days generally approved by Branch Manager.
- Leave of 3+ days requires Head Office approval.
- Three late arrivals should result in a warning (currently inconsistently enforced).
- Emergency leave is usually handled verbally.
- Shift swaps occur informally.
- Attendance directly impacts payroll.

Needs Clarification Later:

- Leave categories
- Overtime calculation
- Half-day policy
- Holiday handling

---

## Key Incident

### Model Town Leave Dispute

Employee claimed leave had been submitted.

Paper request was misplaced.

Manager never processed it.

Payroll deducted salary.

HR spent approximately two weeks resolving the issue.

Outcome:

This incident validated the need for:

- Digital requests
- Status tracking
- Approval history
- Audit trail

---

## Internal Observations

Attendance itself is not the primary issue.

The core issue is:

**The same information is manually transformed multiple times before reaching payroll.**

---

# DM-03 — Assets, Roles & Reporting

## Asset Types

- Barcode scanners
- Company phones
- Delivery bikes
- POS terminals
- Uniforms
- Safety equipment

---

## Current Asset Workflow

Manager assigns asset

↓

Sometimes recorded in notebook

↓

Employee uses asset

↓

Asset returned (sometimes)

↓

No standardized verification

---

## Asset Problems

- Lost equipment
- Missing ownership records
- No return checklist
- No condition tracking
- No accountability
- No inventory visibility

---

## Roles & Responsibilities

### Branch Manager

Can:

- Approve short leave
- Assign existing assets
- Schedule staff
- Handle minor disciplinary actions

---

### Head Office

Responsible for:

- Long leave approvals
- Hiring
- Termination
- Asset purchasing
- Serious disputes

---

### Assistant Manager

Current situation:

Responsibilities are informal and not officially defined.

---

## Visibility Needs

Operations Director wants visibility into:

- Today's absences
- Pending approvals
- Understaffed branches

Regular reports currently requested:

- Weekly attendance
- Monthly asset reconciliation

---

## Internal Observations

Client values operational visibility more than analytics.

Dashboard should prioritize actionable information instead of charts.

---

# DM-04 — Solution Validation

## Client Expectations

The client validated the following desired behaviors.

### Leave

- Employee should track request status.
- Managers should receive notifications.
- Requests should escalate if ignored.
- Longer leave should require multiple approvals.

---

### Attendance

- Corrections must record:
  - Who changed it
  - Why
  - When

---

### Assets

Asset handover should include:

- Timestamp
- Employee confirmation
- Manager confirmation
- Condition at assignment

---

## Cross-Cutting Principles

The client repeatedly emphasized:

- Accountability
- Transparency
- Traceability

Any action affecting:

- Payroll
- Approvals
- Assets

should leave an auditable history.

---

# Project Constraints

Validated during discovery.

- Budget is limited.
- MVP should focus on Attendance and Leave.
- Asset Management should follow if time permits.
- Client prefers phased delivery over an oversized first release.
- Business value is more important than feature count.

---

# Risks

- Existing business policies are not always standardized.
- Some approval rules are informal.
- Assistant Manager permissions are undefined.
- Future payroll integration requirements are unknown.

---

# Discovery Summary

Discovery objectives have been achieved.

The team now has sufficient understanding of:

- Business context
- Organizational structure
- Current operational workflows
- Business pain points
- Initial business rules
- Desired system behavior
- MVP priorities

Remaining unknowns are implementation-level details and can be clarified during requirements engineering if needed.