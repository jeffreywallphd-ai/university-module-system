# University Module System — Data Architecture

## 1. Purpose

The University Module System requires a consistent approach to organizing, accessing, and protecting information across multiple product modules.

The proposed data architecture supports the modular monolith by maintaining clear data ownership, controlled access, and appropriate separation between product-specific and shared information.

The data architecture should:
- Protect institutional information according to its sensitivity and authorized use.
- Maintain data accuracy, consistency, integrity, and availability.
- Prevent unauthorized access or modification across product modules.
- Support approved integration with existing University systems.
- Minimize unnecessary duplication, storage, and maintenance costs.

For the overall system design, see the [Architecture Overview](overview.md). Related requirements are established in the [Key Architecture Principles](principles.md) and [Shared Capabilities](shared-capabilities.md).

## 2. Data Architecture Overview

The proposed modular monolith may use shared database infrastructure while maintaining logical separation between product domains.

### Proposed Database Approach

- Consider a single database infrastructure where appropriate to reduce operational complexity and costs.
- Organize product-specific information into logically separated domains.
- Establish distinct responsibilities and permissions for accessing or modifying information.
- Use appropriate database schemas, access controls, and application interfaces to enforce boundaries.
- Avoid unrestricted access to unrelated product data or protected institutional information.
- Reevaluate the physical database structure as requirements and technical constraints become clearer.

A shared physical database does not imply that all modules or development teams should have unrestricted access to its contents.

### Existing University Systems

- Identify authoritative University systems that already maintain required information.
- Access existing systems of record through approved interfaces and integration methods.
- Avoid creating duplicate authoritative records or independently replacing established University databases.
- Obtain appropriate authorization before integrating protected institutional information.

The University Module System may reference or retrieve information from existing systems without necessarily storing its own copy.

## 3. Data Classification

University information must be handled according to applicable Michigan Tech data classification and protection requirements.

### Tier I — Confidential

- Includes highly sensitive institutional information requiring strong protection.
- May include official student grades, financial aid information, and other designated confidential records.
- Requires appropriate authorization and safeguards for collection, access, storage, and transmission.
- Must not be introduced into prototypes without explicit approval and appropriate controls.

### Tier II — Internal / Private

- Includes information intended for authorized University use rather than unrestricted public disclosure.
- Requires appropriate access restrictions and information protection.
- Should only be shared with users or services that have legitimate responsibilities.

### Tier III — Public

- Includes information approved for public access or distribution.
- May support publicly accessible features without user authentication.
- Still requires appropriate safeguards against unauthorized modification, misuse, or disruption.

### Classification Considerations

- Classify data according to its content and institutional requirements, not solely the product in which it appears.
- Apply additional protections where datasets contain information with different sensitivity levels.
- Distinguish data classification from user roles and access permissions.
- Consult the appropriate University data owner when classification or authorization is uncertain.

## 4. Data Organization and Ownership

### Product Data Domains

**Parking Module**
- May use approved parking locations, availability information, restrictions, and operational data.
- Distinguish public parking information from protected permit, vehicle, or personal records.
- Identify authoritative sources and appropriate access requirements.

**Faculty AI Center of Excellence Module**
- May use approved AI resources, user preferences, activity records, and other validated information.
- Protect faculty-related or institutional information according to classification and intended use.
- Restrict AI integrations to approved information sources and authorized operations.

**Scholarship Discovery Module**
- May use public scholarship listings, eligibility criteria, and approved institutional information.
- Distinguish general scholarship discovery from personalized student information.
- Protect student-specific records and other sensitive information where applicable.

These data requirements are preliminary and subject to validation by the product teams.

### Data Ownership

- Identify responsible data owners for major institutional information sources.
- Obtain appropriate data-owner authorization before accessing protected University records.
- Maintain clear responsibility for data quality, appropriate use, and access decisions.
- Distinguish institutional data ownership from technical administration and database maintenance.

### Shared Data

- Use consistent identifiers and definitions for entities referenced across multiple modules.
- Maintain authoritative sources to prevent conflicting or duplicated records.
- Share information through controlled interfaces rather than unrestricted cross-module database access.
- Avoid introducing shared data structures unless there is a validated cross-module need.

## 5. Data Access and Integration

### Access Control

- Apply least privilege to user, application, and database permissions.
- Restrict access according to data classification, module responsibilities, and authorized business needs.
- Enforce business-specific and record-level authorization within the responsible product modules.
- Prevent unauthorized modification or retrieval of unrelated module data.
- Protect administrative and database-management privileges through appropriate controls.

### Controlled Data Access

- Keep data-access responsibilities within defined module boundaries.
- Use approved internal interfaces for cross-module communication.
- Use shared Data Access and Integration capabilities where common integration functionality is needed.
- Prevent front-end interfaces from directly accessing protected database resources.
- Validate requests and information exchanged between components.

### External Integrations

- Identify required University and external data sources during product validation.
- Confirm authorization, technical feasibility, and appropriate data-use permissions.
- Apply secure communication and data-handling practices.
- Document significant integration dependencies, limitations, and risks.
- Avoid unnecessary external transfer of protected University information.

### Auditing and Traceability

- Record significant access to sensitive information and relevant data modifications.
- Support traceability of administrative and security-related operations.
- Protect audit records from unauthorized changes.
- Avoid storing unnecessary confidential information in logs.

## 6. Data Quality and Lifecycle Management

### Data Quality

- Maintain accurate, complete, consistent, and reliable information.
- Apply appropriate validation when collecting, updating, or exchanging data.
- Identify authoritative sources and processes for correcting inaccurate records.
- Document significant assumptions and limitations affecting data reliability.

### Data Minimization

- Collect and store only information needed for validated product functionality.
- Avoid unnecessary duplication of sensitive records.
- Limit the disclosure of personal information through reports, interfaces, and integrations.
- Prefer aggregated or de-identified information when appropriate for the intended purpose.

### Storage and Protection

- Apply appropriate encryption and access controls based on information sensitivity.
- Use approved storage locations and technical safeguards for protected institutional information.
- Maintain logical separation between public and protected data.
- Protect backups and other copies according to the sensitivity of the underlying information.

### Retention and Disposal

- Establish retention requirements based on applicable University policies and operational needs.
- Avoid retaining information longer than necessary or authorized.
- Apply appropriate data sanitization and disposal procedures.
- Consider recovery requirements and secure backup management where appropriate.

## 7. Prototype Data Requirements

Product teams should demonstrate proposed functionality without unnecessarily handling protected University information.

- Use synthetic or approved public datasets during initial development.
- Do not use real confidential student, faculty, or financial information without explicit authorization.
- Identify expected data sources, classifications, and access restrictions during design.
- Document assumptions where actual University data or integrations are unavailable.
- Evaluate data protection and authorization requirements before expanding prototype functionality.

Prototype data structures may demonstrate anticipated relationships without representing approved access to production University systems.

## 8. Architectural Responsibilities

### CTO/CIO

- Coordinates portfolio-level data architecture and cross-module dependencies.
- Supports consistent architectural boundaries, reuse, and cost-efficient design.
- Reviews proposed changes affecting shared data structures or integrations.

### Security/AI Architect

- Evaluates data classification, access control, privacy, and security requirements.
- Advises on appropriate safeguards and integration risks.
- Supports assessment of sensitive data usage and AI-related information handling.

### Product IT/AI Leads and Development Teams

- Identify product-specific information requirements and data sources.
- Document proposed data models, interfaces, and dependencies.
- Enforce appropriate module-specific data access and business rules.
- Report unresolved data ownership, quality, or security concerns.

### University Data Owners

- Retain authority over access to institutional information within their responsibilities.
- Provide required approvals for protected data access and use.
- Support clarification of data ownership, classification, and applicable restrictions.

## 9. Current Status and Next Steps

**Status:** Proposed data architecture — subject to validation.

**Current Priorities:**
- Identify data requirements and potential sources for each product module.
- Establish appropriate classification and access expectations.
- Define module ownership and controlled integration boundaries.
- Evaluate opportunities to reuse shared information and infrastructure.
- Support secure prototype development using synthetic or approved public data.

**Pending Decisions:**
- Final data models and required relationships.
- Physical database structure and implementation technologies.
- Approved integrations with existing University systems.
- Data ownership and authorization for specific institutional records.
- Retention, backup, recovery, and operational requirements.
- Testing and validation of access controls and data quality.

The data architecture will be refined as product requirements, technical feasibility, and University authorization requirements become clearer.
