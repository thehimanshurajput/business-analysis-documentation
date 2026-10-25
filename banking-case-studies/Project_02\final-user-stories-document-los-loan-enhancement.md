# Final User Stories LOS Loan Enhancement

> Independent portfolio case study. Requirements, targets, and test scenarios are proposed design artifacts; they do not represent client delivery, production implementation, or executed UAT. Names and test identifiers have been anonymized.

User Stories
Loan Enhancement (LOS System) � Co-Applicant Support

## US-101 - Add Co-Applicant to Loan Application

User Story Description: As a Loan Applicant, I want to add a co-applicant during loan application submission so that the bank can consider our combined financial strength while assessing loan eligibility.

## Business Rules

Maximum 2 co-applicants allowed per loan application.

Relationship type is mandatory.

Co-applicant PAN/SSN must be unique within the application.

Co-applicant must be at least 18 years old.

## Acceptance Criteria

AC-1: System should provide an Add Co-Applicant button on the Loan Application screen.

AC-2: System should capture Name, DOB, PAN/SSN, Mobile Number, Employment Type, Monthly Income and Relationship Type.

AC-3: System should validate all mandatory fields before saving the application.

AC-4: System should prevent duplicate PAN/SSN across applicants.

AC-5: System should not allow more than 2 co-applicants.

## WIREFRAME

## US-102 - Calculate Combined Income & Loan Eligibility

User Story Description: As an Underwriter, I want the system to calculate combined income and DTI ratio so that loan eligibility can be assessed consistently and accurately.

## Business Rules

Combined Income = Sum of income of all applicants.

Combined EMI = Sum of existing obligations of all applicants.

Maximum DTI threshold is 40%.

Eligibility assessment should execute automatically.

## Acceptance Criteria

AC-1: System should automatically calculate combined monthly income.

AC-2: System should calculate Debt-to-Income (DTI) ratio using combined income and EMI obligations.

AC-3: System should display eligibility status on the Eligibility Assessment screen.

AC-4: Applications exceeding DTI threshold (less than 50% and greater than 40%) should move to Manual Review.

AC-5: Eligibility calculations should refresh automatically whenever income or liabilities are modified.

## WIREFRAME

## US-103 - Retrieve Credit Bureau Reports for All Applicants

User Story Description: As an Underwriter, I want the system to retrieve bureau reports for all applicants so that creditworthiness can be evaluated without manual intervention.

## Business Rules

Credit bureau checks are mandatory for all applicants.

Bureau responses must be stored in LOS.

Failed bureau requests should be retried twice.

All bureau requests and responses must be audit logged.

## Acceptance Criteria

AC-1: System should initiate separate bureau requests for each applicant.

AC-2: System should display Credit Score, Existing Loans, Delinquencies and Bureau Status.

AC-3: Failure of one bureau request should not impact processing of other applicants.

AC-4: Failed bureau requests should automatically retry up to 2 times.

AC-5: Applications should move to Exception Queue if bureau requests continue to fail.

## WIREFRAME

## US-104 - Review Joint Application and Record Underwriter Decision

User Story Description: As an Underwriter, I want to view consolidated applicant information and eligibility results so that I can approve, reject, or manually review the loan application.

## Business Rules

Underwriter decision is mandatory.

Rejection comments are mandatory.

Applications failing AML checks cannot be approved.

All decisions must be audit logged.

## Acceptance Criteria

AC-1: System should display applicant details, bureau results, eligibility results, AML status and documents on a single review screen.

AC-2: Underwriter should be able to Approve, Reject or send the application for Manual Review.

AC-3: Approved applications should move to the next stage of the loan workflow.

AC-4: Rejected applications should require mandatory comments.

AC-5: Manual Review cases should be routed to the appropriate review queue.

## WIREFRAME
