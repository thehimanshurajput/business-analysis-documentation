# Regulatory Compliance Requirements Case Study

> Independent portfolio case study. Requirements, targets, and test scenarios are proposed design artifacts; they do not represent client delivery, production implementation, or executed UAT. Names and test identifiers have been anonymized.

Detailed User Storie, Business Rules and Acceptance Criteria

## Regulatory Background

This project focuses on enhancing existing compliance controls through Risk-Based Customer Due Diligence (CDD), Enhanced Due Diligence (EDD), Fraud Risk Monitoring, Audit Logging, and Regulatory Reporting. The objective is to improve compliance effectiveness, reduce operational risk, strengthen fraud controls, and provide complete auditability of compliance decisions.

## Key Regulatory Expectations

High-risk customers must undergo Enhanced Due Diligence before account creation.

Banks should apply risk-based customer due diligence rather than treating all customers equally.

Fraud monitoring should leverage multiple risk indicators and risk scoring.

Compliance decisions must be fully auditable and traceable.

Regulatory and compliance reporting should be accurate and readily available.

## User Story 1 � Customer Risk Classification

## Description

As a Compliance Officer, I want the system to classify customers into Low, Medium, or High Risk categories so that the appropriate level of due diligence can be applied during onboarding.

## Business Rules

Risk Classification must be completed before account creation.

Each customer must have only one active risk classification at a given time.

Risk classification must be calculated using predefined compliance rules.

Changes to customer risk level must be audit logged.

Risk classification must be available to downstream systems and reports.

## Acceptance Criteria

The system shall evaluate customer attributes such as customer type, country of residence, occupation, source of funds, and politically exposed person (PEP) status.

If a customer is identified as a PEP, the customer shall automatically be classified as High Risk.

If a customer belongs to a regulator-defined high-risk geography, the customer shall automatically be classified as High-Risk.

The calculated risk level shall be displayed on the customer profile screen.

The risk classification result shall be stored against the customer record.

The system shall prevent account creation if risk classification is incomplete.

Any change to the customer risk level shall record previous value, new value, date, time, and user who made the changes.

Risk classification  data shall be available for compliance dashboards and regulatory reporting.

## User Story 2 � Enhanced Due Diligence (EDD) Review

## Description

As a Compliance Officer, I want high-risk customers to undergo Enhanced Due Diligence review so that regulatory requirements are satisfied before account creation.

## Business Rules

Only customers classified as High Risk shall require EDD.

EDD review must be completed before onboarding approval.

Compliance reviewer comments are mandatory.

All supporting documents must be retained for audit purposes.

## Acceptance Criteria

High-risk customers shall automatically be routed to the EDD review queue.

The system shall notify compliance reviewers when a new EDD case is assigned.

The reviewer shall be able to approve, reject, or request additional information.

Reviewer comments shall be mandatory before a decision can be submitted.

The system shall capture source-of-funds documentation where required.

Account creation shall remain blocked until EDD review is completed.

The EDD decision, reviewer, date, and supporting evidence shall be stored permanently.

The EDD status shall be available for operational and regulatory reporting.

All EDD activities shall be audit logged.

## User Story 3 � Fraud Risk Scoring and Alert Generation

## Description

As a Fraud Operation Analyst, I want the system to generate fraud risk scores and alerts based on multiple risk indicators so that potentially fraudulent activities can be investigated before financial loss occurs.

## Business Rules

Fraud scores must be generated using configured indicators.

High-risk alerts must be reviewed by Fraud Operations.

Fraud alerts cannot be deleted.

Fraud outcomes must be retained for audit purposes.

## Acceptance Criteria

The system shall evaluate risk indicators such as transaction amount, new choice usage, customer behavior, high-risk country, and new beneficiary information.

A fraud risk score shall be generated for each eligible transaction.

When the fraud risk score exceeds the configured threshold, an alert shall be generated automatically.

The alert shall be assigned to the Fraud Operations queue.

The operations analyst shall be able to mark the alert as Genuine, Fraudulent, or Further Investigation Required.

The operations analyst decision shall include mandatory review notes.

The system shall store fraud alert history, operations analyst decisions, and timestamps.

Fraud alerts and outcomes shall be available in compliance dashboards and reports.

All fraud investigation shall be audit logged.

## User Story 4 � Audit Logging and Compliance Reporting

## Description

As a compliance Manager, I want all compliance decisions and fraud investigations to be tracked and reported so that audit and regulatory reporting requirements are satisfied.

## Business Rules

All compliance decisions must be traceable.

Audit records must be immutable after creation.

Only authorized users may access audit information.

Compliance dashboards must be generated from approved data sources.

## Acceptance Criteria

The system shall capture reviewer name, action performed, decision outcomes, timestamp, and decision reason.

The system shall capture all customer risk classification changes.

The system shall capture all EDD decision and fraud investigation outcomes.

Audit records shall not be editable after submission.

Authorized users shall be able to search audit history using customer ID, application ID, or alert ID.

The compliance dashboard shall display total application, high-risk customers, EDD cases, fraud alerts, fraud outcomes, and average review time.

Users shall be able to export dashboard data to Excel format.

The dashboard shall refresh automatically at the configure interval.

Audit history shall be available during internal audits and regulatory examinations.
