# Enterprise-IT-Helpdesk-Lab
Containerized osTicket ticketing system deployed using Docker and Docker Compose. Features secure Cloudflare Tunnel endpoint exposure, SLA policies, RBAC access controls, custom ticket queues, and ITIL-aligned incident management workflows.


# osTicket Helpdesk Deployment & Configuration Lab

## Overview
This repository documents the end-to-end installation, enterprise configuration, and workflow testing of **osTicket** hosted inside a local virtualized Linux environment (`grimeslab.local`). The goal of this lab is to demonstrate practical IT service management (ITSM) practices, custom department routing, SLA policy enforcement, and ticket lifecycle resolution.

## Environment & Prerequisites
* **OS:** Ubuntu 24.04 LTS (Docker Container Stack)
* **Client Endpoint:** Windows 11 Enterprise (`WIN11-CLI`)
* **Core Application:** osTicket v1.17+ / PHP / MySQL
* **Domain Context:** `grimeslab.local`

---

## Deployment & Configuration Steps

### 1. Helpdesk Portal Setup
Provisioned and stabilized the containerized osTicket web application and database backend, verifying access via the local gateway endpoint.

![osTicket Login / Portal](01-osticket-login.png)

### 2. Enterprise Routing & SLA Configuration
Streamlined system administration by stripping default template data and configuring production-aligned departments and routing rules:
* **Tier 1 Helpdesk:** Assigned high-volume identity and access issues (e.g., *Password Reset / Account Lockout* - High Priority).
* **System Administration:** Dedicated escalation path for critical infrastructure outages (e.g., *Network Connectivity Issue* - Emergency Priority).

![osTicket Admin Configuration](02-osticket-admin.png)

### 3. Ticket Lifecycle & Resolution Testing
Executed end-to-end ticket testing simulating real-world client requests:
1. **Ingress:** Client (`John Doe`) submitted an Emergency access failure ticket via the web portal.
2. **Triaging:** Auto-routed to the `Tier 1 Helpdesk` queue and claimed by Administrator (`Jaiden Grimes`).
3. **Remediation:** Executed Active Directory account unlock and password reset on `DC-01`, verified client workstation authentication, and documented the resolution thread before closing.

![osTicket Ticket Resolution](03-ticket-resolution.png)

---

## Key Takeaways
* Designed and enforced structured incident management aligned with standard IT service frameworks.
* Standardized intake categorization to minimize mean time to resolution (MTTR) for critical lockouts and system disruptions.
* Verified multi-tier access controls, custom agent permissions, and audit-ready ticket documentation.
