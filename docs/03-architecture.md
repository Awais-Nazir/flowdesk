# Architecture Overview

**Project:** FlowDesk

**Status:** Draft v1.0

**Input:** Requirements Specification v1.0

---

# 1. Architecture Goals

The architecture should support the business goals identified during discovery while remaining simple enough for an MVP and flexible enough to evolve over time.

Primary goals:

- Modular design
- Maintainability
- Auditability
- Scalability (to additional modules)
- Clear separation of business domains

---

# 2. Guiding Principles

The following principles will guide architectural decisions throughout the project.

## Business First

Technology exists to support business workflows rather than dictate them.

---

## Modular by Design

Each business domain should be implemented as an independent module with well-defined responsibilities.

---

## Audit by Default

Any operation affecting approvals, attendance, assets, or payroll-related information must produce an audit record.

---

## Single Source of Truth

Operational data should exist in one authoritative location.

Avoid duplicate manual data entry.

---

## Configurable Business Rules

Policies such as approval chains or role permissions should be configurable where practical rather than hard-coded.

---

# 3. System Context

FlowDesk is an internal web application used by employees, managers, HR, and Head Office staff.

The system replaces paper-based operational processes while becoming the primary source of operational information across all branches.

External systems are intentionally minimized in the MVP.

Payroll remains outside the system during Phase 1.

---

# 4. Core Modules

The system is organized around business capabilities rather than technical layers.

## Identity & Access

Responsible for:

- Authentication
- User management
- Roles
- Permissions

---

## Attendance

Responsible for:

- Daily attendance
- Corrections
- Attendance history
- Attendance reporting

---

## Leave Management

Responsible for:

- Leave requests
- Approval workflow
- Status tracking

---

## Asset Management

Responsible for:

- Asset inventory
- Assignment
- Returns
- Condition history

---

## Notifications

Responsible for:

- Approval reminders
- Escalations
- Operational alerts

---

## Dashboard

Responsible for presenting operational information relevant to each user role.

---

## Audit

Responsible for maintaining immutable records of significant business actions.

---

# 5. Conceptual Domain Model

The primary business concepts identified during discovery are:

- User
- Branch
- Employee
- Role
- Attendance Record
- Leave Request
- Approval
- Asset
- Asset Assignment
- Notification
- Audit Log

These represent business entities only.

Database design will be completed separately.

---

# 6. Cross-Cutting Concerns

## Authorization

Access to system functionality shall be role-based.

---

## Auditing

Critical operations must be traceable.

Audit records should include:

- Actor
- Action
- Timestamp
- Previous value (where applicable)
- New value
- Reason (where applicable)

---

## Notifications

Operational workflows should notify relevant users without requiring manual follow-up.

---

## Validation

Business rules should be enforced centrally.

---

## Logging

System events and failures should be logged for operational troubleshooting.

---

## Technology Decisions

Technology selection will be completed after the architecture and domain model are finalized.

Selection criteria will include:
- Team expertise
- Maintainability
- Learning value
- Deployment simplicity
- Project requirements

---
<!-- 
# 7. High-Level Technical Stack

Technology choices will be finalized before implementation.

Current architectural direction:

Backend

- Spring Boot
- REST APIs

Frontend

- React

Database

- PostgreSQL

Authentication

- JWT-based authentication

Deployment

- Containerized using Docker

Specific technologies may change if project requirements evolve.

--- -->

# 8. Architecture Decisions

## Monolithic Modular Architecture

The MVP will be implemented as a modular monolith.

Reason:

- Simpler deployment
- Faster development
- Easier debugging
- Appropriate for project size

The architecture should allow future extraction into services if required.

---

## API-First Communication

Frontend and backend communicate exclusively through REST APIs.

---

## Stateless Backend

Application servers remain stateless.

Persistent state is stored within the database.

---

## Domain Ownership

Each module owns its own business logic.

Business logic should not be duplicated across modules.

---

# 9. Future Evolution

Potential future modules include:

- Payroll
- Recruitment
- Performance Reviews
- Inventory
- Procurement

The chosen architecture should allow these modules to be integrated without major restructuring.

# 10. Architectural Constraints

The architecture should support phased delivery.

Attendance and Leave must be deliverable independently.

Asset Management should integrate naturally without requiring major redesign.

The system should prioritize operational simplicity over architectural complexity.

Infrastructure requirements should remain affordable for a small business deployment.