# Functional Requirement Documen For Notification & Exception Handling

> Independent portfolio case study. Requirements, targets, and test scenarios are proposed design artifacts; they do not represent client delivery, production implementation, or executed UAT. Names and test identifiers have been anonymized.

## Functional Requirement Document (FRD)

## Notifications & Exceptional Handling

## 1. Functional Overview

Objective: Enable customer notifications, onboarding retry workflows, operational exception handling, and escalation management during digital account onboarding.

## 2. Document Information

| Field | Value |
| --- | --- |
| Project | Digital Account Opening |
| Module | Notifications & Exception Handling |
| Prepared By | Portfolio author |
| Version | 1.0 |
| Status | Draft |

## 3. Key Stakeholders

| Stakeholder | Responsibility |
| --- | --- |
| Operations Team | Handles onboarding exception cases |
| Business Analyst | Requirement gathering & FRD preparation |
| Notification Team | SMS/email integration and notification templates |
| Compliance Team | Exception review and escalation workflows |
| Technology Team | Retry logic and queue management implementation |

## 4. High-Level Process Flow

## 5. Functional Requirements

| FR ID | Requirement | Priority |
| --- | --- | --- |
| FR-401 | System shall trigger SMS/email notification after successful onboarding. | High |
| FR-402 | System shall notify customer for failed KYC, AML, or CBS processing. | High |
| FR-403 | Failed API requests shall retry  automatically up to 2 times. | High |
| FR-404 | Applications failing after retries shall move to Operations Review Queue. | High |
| FR-405 | All notification and exception handling activities shall be audit logged. | High |
| FR-406 | System shall allow up to 3 document re-upload attempts. | Medium |
| FR-407 | Operations team shall receive exception queue notification within 2 minutes. | Medium |

## 6. Business Rules

Customers shall receive onboarding notifications through SMS and email.

Maximum retry attempts allowed for failed API calls shall be 2

Applications pending beyond 4 business hours shall escalate automatically.

Rejected onboarding applications shall include failure reason notifications.

## 7. Exception Handling Scenarios

| Scenario | System Action |
| --- | --- |
| KYC Validation Failure | Notify customer and allow document re-upload |
| CBS API Failure | Retry API request twice before moving to Operations Queue |
| AML High Risk Match | Move application to Compliance Review Queue |
| Notification Service Failure | Retry notification delivery automatically |

## 8. Notification Events

Successful onboarding completion

KYC validation Failure

Document rejection

Account creation success

Manual review initiation

## 9. Audit Logging & SLA Requirements

All onboarding exception activities must be audit logged with timestamps.

Operations team should resolve high-priority cases within 4 business hours.

Escalation workflow should trigger automatically for SLA breaches.

Notification delivery status should be tracked and stored.

## 10. Non-Functional Requirements

Notification delivery should complete within 30 seconds.

System should support 100,000 notifications per day.

All notification data must be encrypted during transmission.

System availability should be 99.9%.
