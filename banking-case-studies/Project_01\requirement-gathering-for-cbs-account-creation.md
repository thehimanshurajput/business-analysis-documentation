# Requirement Gathering For CBS Account Creation

> Independent portfolio case study. Requirements, targets, and test scenarios are proposed design artifacts; they do not represent client delivery, production implementation, or executed UAT. Names and test identifiers have been anonymized.

## Requirement Gathering For CBS Account Creation & Product Setup

## Questionnaire

How should customer and account creation happen in CBS?

Which customer and product fields are mandatory for CBS account creation?

How will product setup and account type mapping work?

What notifications, audit logs, and downstream actions are required after account creation?

Answers

Customers profile should be created first in CBS using verified KYC details, followed by savings account creation in real time. Account number generation should happen instantly after successful customer creation. If account creation fails, application status should move to Operations Review Queue for manual handling.

Mandatory customer fields include:

Full Name

## DOB

Address

## SSN

Mobile Number

Nationality

Mandatory product fields include:

Product code

Account type

Currency

Branch code

Selected onboarding account type should map automatically to predefined CBS product codes. Product eligibility rules such as minimum balance, currency type, and customer segment should be validated before account creation. Savings account products will be configured and maintained centrally within CBS product setup.

After successful account creation, system should trigger:

Welcome SMS/email

Debit card request

Customer profile sync to CRM

All onboarding and account creation activities must be audit logged with timestamps, user details, and API response information for compliance tracking.
