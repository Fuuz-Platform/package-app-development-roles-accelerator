# package-app-development-roles-accelerator

**Version:** 0.0.1
**Platform:** Fuuz ≥ 2024.8.0
**Spec Version:** 2.0.0

---

## Overview

This package delivers the standard Fuuz platform access control configuration for application development teams. It seeds `Role`, `AccessControlPolicy`, and `AccessControlPolicyGroup` records that define the permission boundaries for developers, administrators, and read-only users — enabling teams to onboard new environments with consistent, pre-tested role structures rather than configuring permissions from scratch.

This is a data-only package (no flows, screens, or custom models). It imports directly into the Fuuz platform's built-in access control system.

---

## Package Contents

```
app-development-roles/
├── manifest.json
├── definition.json
├── package-data.json
└── data/                        10 seed data files
```

---

## Included Roles

| Role ID | Name | Purpose |
|---------|------|---------|
| `applicationAdministrator` | Application Administrator | Full admin access to the Fuuz platform, including deployments and configuration |
| `applicationDevelopment` | Application Development | Development access with flow execution and screen access; restricted from deployments |

---

## Included Access Control Policy Groups

| Group | Purpose |
|-------|---------|
| App Deployment | Policies for users who need to deploy packages and publish changes |
| App Development | Policies for active developers building and testing flows and screens |
| Read-only Access | Policies for stakeholders who need visibility without write access |
| Soft Administrator | Elevated access for admins who manage users and configuration without full platform control |

---

## Included Access Control Policies

| Policy | Description |
|--------|-------------|
| Access All Screens | Grants access to all UI screens in the platform |
| Application API Full Access | Full read/write access to the Application GraphQL API |
| Application API Limited Access | Scoped write access to the Application API (create/update, no delete) |
| Application API Read Only Access | Read-only access to all Application API queries |
| Execute All Connectors | Allows executing all registered connector flows (external integrations) |
| Execute All Flows | Allows triggering any data flow in the environment |
| No Deployments | Prevents package deployment operations; applied to development roles to separate dev from deploy |

---

## Role → Policy Group Assignments

| Role | Policy Group |
|------|-------------|
| Application Administrator | App Deployment + Soft Administrator |
| Application Development | App Development |

---

## Installation

1. Import via Fuuz Package Manager — no pre-configuration required
2. Seed data applies immediately on import; roles and policies are created if they do not already exist
3. Assign roles to users via the Fuuz user management interface

---

## Dependencies

- **Fuuz Platform** ≥ 2024.8.0
- No custom data models or external dependencies

---

*Built on the [Fuuz Industrial Operations Platform](https://fuuz.com)*
