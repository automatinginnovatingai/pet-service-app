# Pet Service Manager — Unified Desktop Edition
## Initial GitHub Release — Version 1.0.0

This release introduces the fully unified version of the Pet Service Manager App,
combining all grooming, training, behavior, appointment, service history, marketing,
staff, reminders, and reporting features into a single Windows `.exe` application.
The app uses a unified SQL Server–ready architecture, allowing pet‑service businesses
of any size to deploy the system without maintaining multiple builds.

All subscription tiers (Basic, Pro, Enterprise) are included in one unified application,
with access determined by the user’s plan and role permissions.

---

## Included in This Release
- Basic Plan  
- Pro Plan  
- Enterprise Plan  
- Staff Add‑on  
- Unified SQL Server–ready architecture  
- One installer, one app, one onboarding flow  

---

## Role‑Based Access Control (RBAC)

The Pet Service Manager includes a secure, centralized RBAC system designed for
multi‑staff grooming and training environments.

### Global Admin
Full system access. Can configure company‑wide settings, manage staff accounts,
control subscription settings, and access all modules.

### Manager
Operational access to appointments, pets, owners, grooming notes, training progress,
behavior notes, service history, reminders, marketing kits, and reports depending
on plan level.

### Staff
Limited operational access. Can manage appointments, grooming notes, training progress,
behavior notes, and reminders, but cannot modify staff settings or subscription details.

### Admin‑Only Registration
Only Global Admins can register new staff accounts. No self‑registration is allowed.

### Dynamic UI Permissions
Each screen automatically adapts to the user’s role and plan. Restricted modules are
hidden or blocked with clear access messages.

### Centralized Permission Enforcement
All role and feature checks are handled through a unified RBAC engine to ensure
consistent, professional‑grade security across every module.

### Multi‑Staff Support
Global Admins can add unlimited staff users with the Staff Add‑on. Each user receives
their own secure login and role‑based access.

This RBAC system ensures secure, scalable, and compliant access control across the
entire Pet Service Manager platform.

---

## Plan Descriptions

### Basic Plan
Provides essential management features for small grooming or training operations.  
Includes core tools for pets, owners, appointments, reminders, and basic service history.  
Ideal for businesses needing a reliable, cost‑effective foundation.

---

### Pro Plan
Expands on the Basic plan with advanced operational tools.  
Designed for growing facilities that manage higher pet volume or require deeper tracking.  
Includes grooming notes, training progress, behavior notes, and staff management.

---

### Enterprise Plan
Unlocks the full capabilities of the system, including everything in Pro plus advanced
features and enterprise‑grade controls.

Enterprise includes:
- Advanced reporting and analytics  
- Marketing kit templates  
- Priority support  
- Enhanced service history exports  
- Expanded staff management tools  

---

### Staff Add‑on
Allows Global Admins to add additional staff users.  
Each staff member receives their own secure login and operational access.  
Cannot function alone — requires an active Basic, Pro, or Enterprise plan.

---

## License Activation
This application requires a valid Stripe subscription to unlock full functionality.

- On first launch, the app verifies your subscription securely through Stripe.  
- If the subscription is active, the app unlocks full access.  
- If the subscription is canceled, expired, or unpaid, access is restricted.  
- Internet access is required only for subscription verification and plan changes.

After activation, the app operates fully offline.

---

## Database
The Pet Service Manager supports two database modes:

### SQL Express (Local Database — Recommended for 1–5 users)
- Automatically installed and configured by the installer  
- Ideal for individuals, small teams, and single‑machine setups  
- Fully offline and self‑contained  

### SQL Server (Remote or On‑Prem Server)
- Connect to an existing SQL Server instance  
- Supports multi‑user environments and IT‑managed deployments  
- Ideal for medium‑to‑large facilities with dedicated servers  

Both modes use the same unified application and feature set.

---

## Stability
This version is the current stable build and serves as the foundation for all future updates.
All modules have been tested for reliability, data integrity, and multi‑user consistency.
