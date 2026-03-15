# Threat Model - Template

---

## Threat Model Metadata

| Field             | Value                     |
| ----------------- | ------------------------- |
| Threat Model ID   | TM-XXX                    |
| System / Platform |                           |
| Architecture Type |                           |
| Author            |                           |
| Last Updated      |                           |
| Status            | Draft / Review / Approved |

---

# 1. Architecture Overview

**System Description**

Provide a short description of the system or platform being modeled.

Example:

> A cloud-based API platform exposing services to external clients through an API gateway and backend microservices.

---

# 2. System Components

List the major components of the architecture.

| Component              | Description                     |
| ---------------------- | ------------------------------- |
| API Gateway            | Entry point for client requests |
| Authentication Service | Handles identity verification   |
| Authorization Service  | Evaluates access permissions    |
| Application Services   | Business logic services         |
| Database               | Stores system data              |
| Secrets Manager        | Manages credentials and secrets |
| Telemetry Pipeline     | Logging and monitoring system   |

---

# 3. Trust Boundaries

Identify boundaries where security assumptions change.

| Boundary                   | Description                               |
| -------------------------- | ----------------------------------------- |
| Internet → API Gateway     | External clients accessing system         |
| API Gateway → Services     | Gateway forwarding authenticated requests |
| Services → Database        | Application accessing stored data         |
| Services → Secrets Manager | Service retrieving credentials            |

---

# 4. Data Flow

Describe how requests move through the system.

Example request flow:

```
Client → API Gateway → Authentication Service → Application Service → Database
```

Optional: include a **data flow diagram**.

---

# 5. Attack Surface

List exposed interfaces attackers may interact with.

| Interface               | Description                    |
| ----------------------- | ------------------------------ |
| Public APIs             | External client access         |
| Authentication Endpoint | Login / token issuance         |
| Admin Interface         | Operational management access  |
| Service APIs            | Internal service communication |
| Integration Endpoints   | Third-party integrations       |

---

# 6. Threat Scenarios

Document realistic threats affecting the architecture.

| Threat ID | Threat                | Description                          |
| --------- | --------------------- | ------------------------------------ |
| T-01      | Authentication Bypass | Attacker bypasses login mechanism    |
| T-02      | Token Replay          | Captured tokens reused               |
| T-03      | Authorization Failure | User accesses unauthorized resources |
| T-04      | Injection Attack      | Malicious input manipulates queries  |
| T-05      | Privilege Escalation  | User gains elevated permissions      |

---

# 7. Security Controls

Document controls that mitigate the threats.

| Control                   | Description                    |
| ------------------------- | ------------------------------ |
| Strong Authentication     | Identity verification enforced |
| Authorization Enforcement | Access checks on resources     |
| Input Validation          | Validate request payloads      |
| Rate Limiting             | Prevent API abuse              |
| Secrets Management        | Secure credential storage      |
| Encryption                | Protect data in transit        |

---

# 8. Telemetry and Detection

Define telemetry required to detect suspicious activity.

| Event                   | Purpose                     |
| ----------------------- | --------------------------- |
| Authentication Failures | Detect credential attacks   |
| Authorization Denials   | Detect privilege escalation |
| API Rate Anomalies      | Detect abuse                |
| Admin Activity          | Monitor privileged actions  |
| Data Access Logs        | Track sensitive data usage  |

---

# 9. Residual Risks

Document risks that remain after controls are implemented.

| Risk                              | Description                           | Mitigation                   |
| --------------------------------- | ------------------------------------- | ---------------------------- |
| Third-party dependency compromise | External services trusted by platform | Monitor integration activity |
| Insider misuse                    | Privileged users abusing access       | Logging and monitoring       |

---

# 10. Related Architecture Artifacts

Link to other architecture documentation.

**Related Security Architecture Patterns**

* SAP-001 Secure API Boundary
* SAP-002 Authorization Enforcement Point

**Related Architecture Decisions**

* SAD-001 Centralized Authentication Strategy

**Related Telemetry Architecture**

* Security telemetry blueprint

---

# Review Notes

| Reviewer | Comments |
| -------- | -------- |
|          |          |

---

# Approval

| Role               | Name | Date |
| ------------------ | ---- | ---- |
| Security Architect |      |      |
| Platform Architect |      |      |
