# Requirement Gathering For Customer Onboarding And Document Submission

> Independent portfolio case study. Requirements, targets, and test scenarios are proposed design artifacts; they do not represent client delivery, production implementation, or executed UAT. Names and test identifiers have been anonymized.

## Questionnaire

What customer information and documents are mandatory for onboarding?

How should OCR and document verification work?

What validations and check must happen before onboarding submission?

What should happen when onboarding fails or documents are invalid?

Which system and teams are involved in onboarding processing?

Answers

For onboarding the customer information needed are

Full Name

## DOB

Address

SSN Number

Phone Number

Email address

The documents that are mandatory for onboarding

Passport

Driving license or utility bill for address proof

OCR would extract the information such as full name, DOB, document ID from the document. Customer will be allowed to review and edit the extracted details from the document.

If OCR confidence score is low or image quality is poor then the system would ask to reupload the documents.

The validation before onboarding process would be

Duplicate customer profile

SSN validation

Customer age eligibility

AML & sanction screening must also be validated before onboarding process.

If the documents are expired, blurred or invalid, then the system will allow customer to upload the documents up to max 3 attempts.

Upon failed KYC/AML screening, the profile would be reviewed manually by the appropriate team. Customer would be notified immediately via sms/email upon the document failing.

The team/system involved in onboarding process are

OCR engine

Mobile/web application

KYC API�s

AML Screening

Notification services

Core Banking System
