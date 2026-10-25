# Requirement Gathering For KYC & AML Screening

> Independent portfolio case study. Requirements, targets, and test scenarios are proposed design artifacts; they do not represent client delivery, production implementation, or executed UAT. Names and test identifiers have been anonymized.

## Questionnaire

Which third-party systems/APIs will be used for KYC and AML verification?

What conditions should trigger rejection, manual review, or approval?

How should exception handling retry workflows operate?

How audit, compliance, and data retention requirements must be followed?

## Answers

External KYC verification APIs will validate customer identity details. OCR APIs will extract:

Name

## DOB

Address

Document number from uploaded documents.

AML Screening vendors will perform:

Sanctions screening

PEP checks

Risk scoring

Auto Approval Conditions

Successful KYC verification

Low AML risk score

Valid government documents

No duplicate customer record found

Manual Review Conditions

High AML risk score

Low OCR confidence score

Possible duplicate customer match

Partial KYC validation failure

Rejection Conditions

Invalid or expired ID documents

Failed identity verification

Customer found in sanctions list

Underage customer (<18 years)

Exceptional handling and retry workflows are:

Customers should receive clear error messages for failed onboarding scenarios.

System should allow Maximum 3 document re-upload attempts.

If KYC/AML API fails: System should retry request 2 times automatically.

Failed applications should move to Operations Review Queue for manual investigation.

Customer should receive: SMS/email notifications & Corrective action guidance.

Audit Logging Requirements

System should audit log:

Document uploads

KYC validation results

AML screening outcomes

Approval/rejection actions

User timestamps

Compliance Requirements
Customer documents must be encrypted during:

Transmission

Storage

Role-based access control should restrict document access.

Customer consent capture is mandatory before onboarding submission.\

Data Retention Requirements

KYC and AML records should be retained for: Maximum 7 years as per regulatory compliance requirements.
