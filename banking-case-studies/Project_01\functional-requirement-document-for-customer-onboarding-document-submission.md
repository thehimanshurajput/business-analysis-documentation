# Functional Requirement Document For Customer Onboarding & Document Submission

> Independent portfolio case study. Requirements, targets, and test scenarios are proposed design artifacts; they do not represent client delivery, production implementation, or executed UAT. Names and test identifiers have been anonymized.

## Functional Requirement Document (FRD)

## Customer Onboarding & Document Submission

## 1. Functional Overview

Enable customer to digitally onboard through mobile/web channels by capturing personal details, uploading identify documents, validating information using OCR/KYC APIs, and initiating onboarding workflows.

## 2. Document Information

| Field | Value |
| --- | --- |
| Project | Digital Account Opening |
| Module | Customer Onboarding & Document Submission |
| Prepared By | Business Analyst Team |
| Version | 1.0 |
| Status | Draft |

## 3. Key Stakeholders

| Stakeholder | Responsibility |
| --- | --- |
| Product Owner | Defines onboarding vision and priorities |
| Business Analyst | Requirement gathering & FRD preparation |
| Compliance/KYC Team | KYC rules and validations |
| OCR Integration Team | OCR extraction & API integration |
| CBS Team | Customer/account creation integration |

## 4. High Level Process Flow

## 5. Functional Requirements

| FR ID | Requirement | Priority |
| --- | --- | --- |
| FR-101 | System shall allow upload of Passport, Driver�s License, and Utility Bill in JPG, PNG, or PDF format. | High |
| FR-102 | OCR engine shall extract customer name, DOB, address, and document number from uploaded documents. | High |
| FR-103 | System shall validate mandatory customer details before onboarding submission. | High |
| FR-104 | System shall allow customer to edit OCR extracted data before submission. | Medium |
| FR-105 | Duplicate customer validation shall occur before onboarding approval. | High |

## 6. Business Rules

Customers below 18 years cannot onboard digitally.

Maximum document upload size allowed is 10 MB.

Customers can retry failed document upload up to 3 times.

KYC verification must complete successfully before onboarding approval.

## 7. Exception Handling

| Scenario | System Action |
| --- | --- |
| OCR Failure | Prompt customer to re-upload document |
| Invalid SSN | Reject application |
| Duplicate Customer | Move application to manual review queue |
| KYC API Timeout | Retry API call twice before failure |

## 8. Non-Functional Requirements

Response time should be under 3 seconds for onboarding screens.

All uploaded documents must be encrypted during transmission and storage.

Platform should support 10,000 onboarding requests daily.

System availability should be 99.9%.
