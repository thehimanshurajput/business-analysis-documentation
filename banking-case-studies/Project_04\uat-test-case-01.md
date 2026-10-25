# Regulatory Compliance UAT Test Cases

> Independent portfolio case study. Requirements, targets, and test scenarios are proposed design artifacts; they do not represent client delivery, production implementation, or executed UAT. Names and test identifiers have been anonymized.

## Requirement Compliance UAT Case Design

## TC-RC-001 (Customer Risk Classification)

Test Case Description: Verify that a Politically Exposed Person (PEP) is automatically classified as High Risk.

## Test Steps

1. Login to Customer Onboarding Portal

2. Create a new customer application

3. Enter customer information

4. Select PEP Status = Yes

5. Submit application

6. View risk classification

## Test Data

Customer Name � Sample Applicant A

PEP Status � Yes

Country � United States

Occupation � Government Official

## Expected Result

Customer classified as High Risk

Risk stored in Profile

Customer routed for EDD

## TC-RC-002

Test Case Description: Verify account creation is blocked if risk classification is incomplete.

## Test Steps

1. Create application
2. Skip risk classification
3. Attempt account creation

## Test Data

Customer Name: Sample Applicant B

Risk Classification: Null

## Expected Result

Account creation blocked

Validation message displayed

Audit log created

## TC-EDD-001 (Enhanced Due Diligence Review)

Test Case Description: Verify High Risk Customers are routed to EDD review.

## Test Steps

1. Create High Risk Customer

2. Submit application

3. Check EDD queue

## Test Data

Customer Name: Sample Applicant C

Risk Level: High

## Expected Result

EDD case created.

Customer appears in EDD queue

Reviewer notified

## TC-EDD-002

Test Case Description: Verify account creation cannot proceed if EDD is pending

## Test Steps

Open High Risk customer

Keep EDD status pending

Attempt account creation

## Test Data

Customer Name: Sample Applicant C

EDD Status: Pending

## Expected Result

Account creation blocked

Validation message displayed

No account created

## TC-FRD-001 (Fraud Risk Scoring and Alert Generation)

Test Case Description: Verify fraud alert generation

## Test Steps

Login as customer

Initiate transaction

Submit transaction

System calculated fraud score

## Test Data

Amount: $15,000

New Device: Yes

High Risk Country: Yes

New Beneficiary: Yes

## Expected Result

Fraud score exceeds threshold

Alert generated

Transaction moved to review

## TC-FRD-002

Test Case Description: Verify operations analyst can close alert as genuine

## Test Steps

Login as analyst

Open alert

Review details

Mark as Genuine

Enter notes

Submit

## Test Data

Alert ID: [REDACTED SAMPLE ALERT ID]

## Expected Result

Alert closed

Outcome stored

Audit record created

## TC-AUD-001 (Audit Logging and Compliance Reporting)

Test Case Description: Verify compliance approval activity is audit logged

## Test Steps

Login as Compliance Officer

Approve EDD case

Open Audit History

## Test Data

Customer ID: [REDACTED SAMPLE CUSTOMER ID]

Reviewer: [REDACTED SAMPLE REVIEWER ID]

## Expected Result

Audit record contains reviewer, decision, timestamp and reason.

## TC-AUD-002

Test Case Description: Verify compliance dashboard displays correct KPIs

## Test Steps

Login as Compliance Manager

Open dashboard

Select reporting period

Verify KPIs

## Test Data

Applications Submitted: 100

High Risk Customer: 15

EDD Cases: 10

## Expected Result

Dashboard loads

KPIs match source data

Export available
