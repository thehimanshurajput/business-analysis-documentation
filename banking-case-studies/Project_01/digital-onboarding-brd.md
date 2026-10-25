# Digital onboarding BRD

> Independent portfolio case study. Requirements, targets, and test scenarios are proposed design artifacts; they do not represent client delivery, production implementation, or executed UAT. Names and test identifiers have been anonymized.

## Digital Account Opening Project

## 1. Executive Summary

fictional US retail bank plans to modernize its retail banking onboarding process by implementing a fully digital savings account opening platform. The current onboarding process involves manual document verification, branch visits, delayed KYC processing, and manual account creation in the Core Banking System (CBS).

The Proposed solution includes:

Mobile & web-based onboarding

OCR/API-based customer data extraction

Digital KYC & AML verification

Real-time CBS account creation

Automated SMS & email notifications

## 2. Primary Objective

| Objective | Target |
| --- | --- |
| Reduce account opening time | < 10 minutes |
| Reduce branch dependency | 80% |
| Increase onboarding conversion | +35% |
| Straight through processing | >85% |
| Enable real-time KYC validation | Mandatory |

## 3. Needs Statement

Current Business Problems:

Manual KYC verification caused onboarding delays

Physical branch dependency impacts customer experience

Multiple manual handoffs increase operational effort

Manual CBS account setup increases processing time

## 4. Project Scope

| In Scope | Out of Scope |
| --- | --- |
| Savings account onboarding | Loan onboarding |
| Digital KYC verification | Corporate accounts |
| AML screening | Wealth management |
| CBS account creation | Credit card onboarding |
| SMS & email notification |  |

## 5. Business Requirements

| Requirement ID | Requirement |
| --- | --- |
| BR-1 | Customer should open account digitally without visiting branch. |
| BR-2 | Onboarding process should complete within 10 minutes. |
| BR-3 | System should validate identity, address, and tax ID before account creation |
| BR-4 | CBS should generate account number instantly after approval. |
| BR-5 | AML & sanctions screening must occur before account activation. |

## 6. Key Stakeholders

| Stakeholder | Role |
| --- | --- |
| Product Owner | Defines business priorities |
| Business Analyst | Requirement gathering & process analysis. |
| Compliance Team | KYC & AML policy validation |
| CBS Team | Core banking integration |
| QA Team | Testing & validation |

## 7. Project Constraints

Go-live timeline restricted to 6 months

Dependency on third-party OCR/KYC APIs

Fixed transformation budget

## 8. High-Level Digital Onboarding Flow

## 9. AS-IS Process

## 10. TO-BE Process
