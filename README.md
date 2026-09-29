# Enterprise-IT-Helpdesk-Lab
Containerized osTicket ticketing system deployed using Docker and Docker Compose. Features secure Cloudflare Tunnel endpoint exposure, SLA policies, RBAC access controls, custom ticket queues, and ITIL-aligned incident management workflows.


# osTicket Helpdesk Deployment & Configuration Lab

**Live Interactive Demo:** [Jaiden Grimes’ Enterprise IT Helpdesk Lab](https://bit.ly/jaidens-enterprise-it-helpdesk-lab)  *(Note: The live environment requires the background host VM and Cloudflare Tunnel process to be active.)*

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

**_osTicket Login / Portal_** <img width="1919" height="976" alt="01-osticket-login" src="https://github.com/user-attachments/assets/f6c8fe6e-473b-4f81-8c73-275a9ebc1ff4" />

### 2. Enterprise Routing & SLA Configuration
Streamlined system administration by stripping default template data and configuring production-aligned departments and routing rules:
* **Tier 1 Helpdesk:** Assigned high-volume identity and access issues (e.g., *Password Reset / Account Lockout* - High Priority).
* **System Administration:** Dedicated escalation path for critical infrastructure outages (e.g., *Network Connectivity Issue* - Emergency Priority).

**_osTicket Admin Configuration_** <img width="1919" height="978" alt="02-osticket-admin" src="https://github.com/user-attachments/assets/b5a0f76e-ebe5-4d7e-a8d3-a5f7d2955f6f" />

### 3. Ticket Lifecycle & Resolution Testing
Executed end-to-end ticket testing simulating real-world client requests:
1. **Ingress:** Client (`John Doe`) submitted an Emergency access failure ticket via the web portal.
2. **Triaging:** Auto-routed to the `Tier 1 Helpdesk` queue and claimed by Administrator (`Jaiden Grimes`).
3. **Remediation:** Executed Active Directory account unlock and password reset on `DC-01`, verified client workstation authentication, and documented the resolution thread before closing.

**_osTicket Ticket Resolution_** <img width="1919" height="976" alt="03-ticket-resolution" src="https://github.com/user-attachments/assets/c638e6f1-9e45-4c67-8859-705ca73ecc55" />

---

## Key Takeaways
* Designed and enforced structured incident management aligned with standard IT service frameworks.
* Standardized intake categorization to minimize mean time to resolution (MTTR) for critical lockouts and system disruptions.
* Verified multi-tier access controls, custom agent permissions, and audit-ready ticket documentation.
