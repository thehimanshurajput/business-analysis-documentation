# Requirement Gathering For Notification & Exceptional Handling

> Independent portfolio case study. Requirements, targets, and test scenarios are proposed design artifacts; they do not represent client delivery, production implementation, or executed UAT. Names and test identifiers have been anonymized.

## Requirement Gathering For Notification &

## Exceptional Handling

## Questionnaire

Which onboarding failure scenarios should trigger automatic notifications, manual review, or application rejection?

How should retry handling work when KYC, AML, OCR, or CBS integration fails?

What operational SLAs, audit logs, and escalation workflows are required for exception cases?

## Answers

Applications should move to manual review for scenarios such as

Low OCR confidence

Duplicate customer detection

High AML risk score

Applications should be automatically rejected for

Invalid government IDs

Sanctions list matches

Failed identity verification

Customers should receive SMS/email notifications with failure reason and corrective action guidance.

System should automatically retry failed API requests up to 2 times before marking onboarding re-upload attempts for failed OCR or KYC validations. If retries continue to fail, the application should move to Operations Review Queue for manual investigation.

All exception cases included KYC failures, AML alerts, and CBS integration failures must be audit logged with timestamps and API response details. Operations team should resolve high- priority onboarding exceptions within 4 business hours. Cases pending beyond SLA timelines should automatically escalate to Operations Manager or Compliance Team.
