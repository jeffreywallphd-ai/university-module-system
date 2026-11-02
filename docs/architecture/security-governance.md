# University Module System — Security & Governance

## 1. Purpose

This document establishes security, privacy, accessibility, and responsible AI governance expectations for the University Module System.

These expectations apply across the proposed modular monolith, including its user interfaces, business modules, shared capabilities, integrations, and data layer.

The objectives are to:
- Protect University information and system functionality from unauthorized access, modification, or disclosure.
- Establish consistent security and governance expectations across product teams.
- Identify, evaluate, and address architectural risks throughout development.
- Support compliance with applicable University policies and external requirements.
- Balance appropriate safeguards with usability, maintainability, and cost efficiency.

Related documentation:
- [Architecture Overview](overview.md)
- [Key Architecture Principles](principles.md)
- [Shared Capabilities](shared-capabilities.md)
- [Data Architecture](data-architecture.md)

## 2. Security Governance Framework

### Security by Design
- Consider security and privacy requirements throughout planning, development, testing, and deployment.
- Apply safeguards according to system functionality, data sensitivity, and potential risks.
- Identify security requirements before introducing protected information or external integrations.
- Document unresolved security risks and proposed mitigation strategies.

### Defense in Depth
- Apply complementary safeguards across the application, business modules, shared capabilities, and data layer.
- Use authentication, authorization, secure communications, monitoring, and other appropriate protections.
- Avoid relying on any single security control to protect sensitive functionality or information.

### Security Boundaries
- Distinguish publicly accessible functionality from protected and administrative operations.
- Enforce least privilege and appropriate separation of responsibilities.
- Maintain boundaries between product modules and shared components.
- Restrict access to sensitive information according to institutional authorization and legitimate responsibilities.

Public and protected areas represent logical access and protection boundaries, not necessarily separate physical environments. Faculty, students, staff, and administrators represent user roles rather than data classifications.

## 3. Security Controls and Operational Expectations

### Identity and Access Management
- Use approved authentication mechanisms for protected functionality.
- Apply authorization at the application and business-service levels.
- Verify permissions for sensitive operations and individual records where appropriate.
- Restrict administrative privileges and periodically review access requirements.

### Application and Infrastructure Security
- Protect sensitive communications and stored information through appropriate technical safeguards.
- Validate input and apply secure development practices.
- Manage credentials, secrets, and system configurations securely.
- Evaluate relevant software dependencies and vulnerabilities.
- Avoid storing credentials, confidential records, or other sensitive operational information in the GitHub repository.

### Logging and Monitoring
- Record significant security events, sensitive operations, and administrative changes.
- Restrict access to audit information and protect logs against unauthorized modification.
- Avoid unnecessarily including protected information in logs.
- Establish appropriate procedures for identifying and escalating potential security incidents.

### Availability and Recovery
- Consider system reliability, backups, and recovery needs based on the importance of each function.
- Evaluate risks arising from shared infrastructure or dependencies.
- Document operational limitations and recovery requirements before production deployment.

Detailed shared-service responsibilities are documented in [Shared Capabilities](shared-capabilities.md).

## 4. Privacy and Data Protection Governance

- Follow applicable University requirements for data classification, access, storage, retention, and disposal.
- Collect and disclose only information necessary for authorized product functionality.
- Obtain appropriate institutional authorization before accessing protected University records.
- Evaluate privacy risks associated with external systems, analytics, AI tools, and integrations.
- Use synthetic or approved public data during prototype development unless protected data access has been explicitly authorized.

Specific data classifications, ownership responsibilities, and access patterns are addressed in [Data Architecture](data-architecture.md).

## 5. Responsible AI Governance

AI-related functionality must be evaluated for technical risks, appropriate data use, and potential impacts on users.

### AI Usage and Data Protection
- Use approved AI tools and integrations consistent with applicable University policies.
- Restrict AI access to information and operations the requesting user or service is authorized to use.
- Avoid submitting protected University information to unapproved AI services.
- Document relevant AI data flows, external dependencies, and potential disclosure risks.

### Human Oversight and Accountability
- Require appropriate human review of AI-generated content used for consequential purposes.
- Maintain human approval for sensitive decisions or actions where required.
- Communicate relevant AI limitations, uncertainty, and usage expectations.
- Establish responsibility for reviewing AI-related errors and resolving concerns.

### AI-Specific Risk Management
- Evaluate risks involving inaccurate outputs, prompt injection, inappropriate data disclosure, and unauthorized tool use.
- Apply appropriate restrictions to AI tools capable of accessing systems or performing actions.
- Consider output evaluation, logging, monitoring, and escalation procedures.
- Reuse AI governance controls across modules when practical.

The Faculty AI Center of Excellence may require additional AI-specific controls as its product scope becomes clearer.

## 6. Accessibility Governance

Accessibility requirements apply to all user-facing product modules.

- Incorporate accessibility considerations throughout interface design, implementation, and testing.
- Follow applicable University accessibility requirements and relevant accessibility standards.
- Support keyboard navigation, readable content, appropriate labels, and compatibility with assistive technologies.
- Evaluate accessibility of interactive components, forms, visualizations, and AI-assisted experiences.
- Document identified accessibility barriers and planned remediation.
- Provide appropriate alternative access when required.

Accessibility should be treated as a shared architectural expectation while remaining an implementation responsibility of each product team.

## 7. Applicable Policies and Standards

The following references inform security and governance decisions, subject to their applicability and current institutional requirements.

### Michigan Tech Policies and Standards
- Policy 1.05 — University Web Policy.
- Policy 1.06 — Acceptable Use of Information Technology Resources.
- Policy 1.11 — FERPA / Student Records.
- Policy 1.15 — Accessible Information and Communication Technology.
- Policy 1.20 — Generative Artificial Intelligence.
- Information Security Plan.
- Data Classification and Protection Standard.
- Identity and Access Management Policy.
- Applicable confidentiality and data sanitization requirements.

### External Requirements and Reference Frameworks
- FERPA, where student education records are involved.
- ADA and Section 504 accessibility requirements, as applicable.
- GLBA safeguards requirements, where applicable to covered institutional activities and information.
- Relevant Michigan privacy and information security laws.
- NIST Cybersecurity Framework and selected NIST SP 800-53 controls as risk-management and security-design references.

Applicability must be assessed according to actual product functionality, information use, and institutional requirements. Referencing a framework does not establish formal compliance or certification.

## 8. Governance Roles and Responsibilities

### CTO/CIO
- Coordinates portfolio-level architectural governance and technical direction.
- Reviews significant cross-module dependencies and proposed architectural changes.
- Supports prioritization of risks, shared controls, and cost-efficient solutions.
- Coordinates unresolved issues with the Security/AI Architect and product teams.

### Security/AI Architect
- Guides security, privacy, and responsible AI architecture considerations.
- Reviews proposed safeguards, access boundaries, integrations, and significant risks.
- Recommends mitigation strategies and identifies concerns requiring further review.
- Supports consistent security and AI governance practices across modules.

### Product IT/AI Leads and Development Teams
- Identify product-specific security, accessibility, and data-use requirements.
- Implement and test appropriate safeguards within their modules.
- Document known risks, technical limitations, and unresolved dependencies.
- Coordinate changes that affect shared components or other product modules.

### University Data Owners and Authorized Institutional Personnel
- Determine appropriate authorization for access to protected institutional information.
- Provide institutional approvals where required.
- Retain applicable policy, compliance, and operational decision authority.

Course-level architectural review does not replace required University approval for production systems or protected data use.

## 9. Risk Management and Change Review

### Risk Identification
- Identify security, privacy, accessibility, operational, and AI-related risks.
- Consider potential impacts on users, institutional information, and other product modules.
- Assess risks based on likelihood, severity, data sensitivity, and relevant dependencies.

### Risk Documentation
- Record significant risks, assumptions, proposed safeguards, and unresolved questions.
- Identify a responsible owner for addressing each significant concern.
- Prioritize mitigation according to potential impact and implementation feasibility.
- Escalate concerns that exceed a product team's authority or available resources.

### Architectural Change Review
- Evaluate changes affecting shared capabilities, interfaces, data access, or security boundaries.
- Consider potential impacts on other modules before implementing significant changes.
- Use version control, technical review, and appropriate testing.
- Document material architectural decisions and changes within GitHub.

## 10. Prototype Security and Accessibility Checklist

The following checklist supports product teams during solution validation and prototype development.

### Security and Privacy
- [ ] Identify intended users, roles, and sensitive operations.
- [ ] Identify relevant data sources and potential privacy concerns.
- [ ] Use synthetic or approved public data unless protected access is authorized.
- [ ] Define appropriate authentication and authorization requirements.
- [ ] Identify significant risks involving module boundaries, integrations, and unauthorized access.

### Accessibility
- [ ] Identify accessibility requirements for major user workflows.
- [ ] Evaluate keyboard navigation, content readability, and interface labeling.
- [ ] Document known barriers and planned improvements.

### Responsible AI (Where Applicable)
- [ ] Identify AI tools, data inputs, outputs, and external integrations.
- [ ] Evaluate data disclosure, inaccurate outputs, and unauthorized actions.
- [ ] Establish appropriate human review and approval expectations.

### Review and Documentation
- [ ] Document significant technical risks and unresolved security concerns.
- [ ] Identify required safeguards and responsible team members.
- [ ] Review major cross-module dependencies with the CTO/CIO and Security/AI Architect.
- [ ] Record limitations and requirements that must be addressed before using real institutional data or moving toward production.

For early prototypes, teams may document planned controls when full implementation or validation is not yet feasible.

## 11. Current Status and Next Steps

**Status:** Proposed security and governance guidance — subject to validation and review.

**Current Priorities:**
- Establish consistent security and accessibility expectations across product teams.
- Identify product-specific risks and necessary safeguards.
- Define access boundaries and shared governance responsibilities.
- Evaluate proposed AI integrations and relevant data-use restrictions.
- Support security and architecture reviews during solution validation.

**Pending Decisions:**
- Final product-specific security requirements and access permissions.
- Approved authentication mechanisms and external integrations.
- Operational logging, monitoring, recovery, and incident response arrangements.
- Required institutional reviews and approvals.
- Security testing and accessibility validation requirements for later development stages.

This document provides architectural planning guidance and does not constitute institutional security approval or verification of production compliance.
