# Functional Requirement Document for KYC & AML Screening

> Independent portfolio case study. Requirements, targets, and test scenarios are proposed design artifacts; they do not represent client delivery, production implementation, or executed UAT. Names and test identifiers have been anonymized.

## Functional Requirement Document (FRD)

## Digital KYC & AML Screening

## 1. Functional Overview

Objective: Enable automated customer identity verification and AML screening during digital account onboarding using KYC, sanctions, and AML verification integrations.

2. Document Information

| Field | Value |
| --- | --- |
| Project | Digital Account Opening |
| Module | Digital KYC & AML Screening |
| Prepared By | Portfolio author |
| Version | 1.0 |
| Status | Draft |

## 3. Key Stakeholders

| Stakeholder | Responsibility |
| --- | --- |
| Compliance Team | Defines KYC & AML policies |
| Business Analyst | Requirement gathering & FRD preparation |
| AML Operations Team | Handles manual review cases |
| KYC Vendor Team | Provides KYC verification APIs |
| Technology Team | System integration & workflow implementation |

## 4. High-Level Screening Flow

## 5. Functional Requirements

| FR ID | Requirements | Priority |
| --- | --- | --- |
| FR-201 | System shall validate SSN details using external KYC verification APIs. | High |
| FR-202 | System shall screen customers against sanctions and PEP watchlists. | High |
| FR-203 | AML risk score shall be calculated before onboarding approval. | High |
| FR-204 | Applications with AML risk score above threshold shall move to Manual Review Queue. | High |
| FR-205 | System shall notify customer if KYC verification fails. | Medium |
| FR-206 | System shall retry failed KYC/AML API calls up to 2 times | Medium |

## 6. Business Rules

Customers found in sanctions list shall be automatically rejected.

Applications with AML risk score>80 shall require manual review.

KYC verifications must complete successfully before account creation.

Customers below 18 years cannot onboard digitally.

## 7. Exception Handling

| Scenario | System Action |
| --- | --- |
| KYC API Timeout | Retry API request twice before failure |
| AML Screening Failure | Move application to Manual Review Queue |
| Invalid SSN | Reject onboarding application |
| Duplicate Customer Match | Trigger Operations Review Workflow |

## 8. Non-Functional Requirements

KYC API response time should be under 10 seconds.

All customer data must be encrypted during storage and transmission.

System availability should be 99.9%.

AML screening should support real-time processing.

## 9. Audit & Compliance Requirements

All KYC and AML actions must be audit logged with timestamps.

Customer onboarding records should be retained for minimum 7 years.

Role-based access controls must restrict sensitive customer data access.

Customer consent capture is mandatory before onboarding submission.
