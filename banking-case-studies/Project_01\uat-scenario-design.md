# UAT Scenario Design

> Independent portfolio case study. Requirements, targets, and test scenarios are proposed design artifacts; they do not represent client delivery, production implementation, or executed UAT. Names and test identifiers have been anonymized.

## UAT Scenario Design
Digital Account Opening Project

Customer Onboarding & Document Submission
Test Scenario ID: TS-ONB-001
Test Scenario Title: Successful Customer Onboarding
Objective: Validate successful onboarding with valid customer details and document.

| Test Case ID | Test Case Description | Test Steps | Expected Result | Test Data | Priority | UAT Status | Defect ID |
| --- | --- | --- | --- | --- | --- | --- | --- |
| TC-ONB-001 | Verify successful onboarding submission | 1. Launch onboarding application<br>2. Select Savings Account<br>3. Enter valid personal details<br>4. Upload valid passport<br>5. Review OCR data<br>6. Submit application | Application created successfully and reference number generated | Sample Applicant A, passport<br>[REDACTED TEST DOCUMENT ID] | High |  |  |
| TC-ONB-002 | Verify OCR extraction accuracy | 1. Upload passport<br>2. Wait for OCR processing<br>3. Review extracted data<br>4. Compare extracted values with document<br>5. Confirm details | Name, DOB and document number correctly extracted | Passport [REDACTED TEST DOCUMENT ID] | High |  |  |

Test Scenario ID: TS-ONB-002
Test Scenario Title: Document Validation
Objective: Validate invalid and missing document scenarios

| Test Case ID | Test Case Description | Test Steps | Expected Result | Test Data |
| --- | --- | --- | --- | --- |
| TC-ONB-003 | Verify blurred document rejection | 1. Start onboarding<br>2. Upload blurred passport image<br>3. Submit document<br>4. Trigger OCR validation<br>5. Review response | System rejects document and prompts re-upload | Blurred passport image |
| TC-ONB-004 | Verify mandatory field validation | 1. Enter customer details<br>2. Leave mobile number blank<br>3. Upload document<br>4. Submit application<br>5. Review validation messages | System prevents submission and displays validation error | Mobile Number Blank |

Digital KYC & AML Screening	
Test Scenario ID: TS-KYC-001
Test Scenario Title: KYC Verification
Objective: Validate successful and failed KYC verification

| Test Case ID | Test Case Description | Test Steps | Expected Result | Test Data |
| --- | --- | --- | --- | --- |
| TC-KYC-001 | Verify successful SSN verification | 1. Submit onboarding application<br>2. Invoke KYC API<br>3. Validate SSN<br>4. Receive successful response<br>5. Continue onboarding | Customer passes KYC verification | SSN [REDACTED TEST ID] |
| TC-KYC-002 | Verify invalid SSN handling | 1. Submit invalid SSN<br>2. Trigger KYC verification<br>3. Receive validation response<br>4. Process failure<br>5. Review application status | Application rejected due to invalid SSN | SSN [REDACTED INVALID TEST VALUE] |

Test Scenario ID: TS-KYC-002
Test Scenario Title: AML Screening
Objective: Validate AML risk and sanctions checks

| Test Case ID | Test Case Description | Test Steps | Expected Result | Test Data |
| --- | --- | --- | --- | --- |
| TC-KYC-003 | Verify low-risk customer approval | 1. Complete KYC<br>2. Run AML screening<br>3. Calculate risk score<br>4. Review result<br>5. Approve onboarding | Application approved | Risk Score 20 |
| TC-KYC-004 | Verify sanctions match rejection | 1. Submit customer data<br>2. Run sanctions screening<br>3. Match against watchlist<br>4. Review AML result<br>5. Process application | Application rejected and audit log created | OFAC Match |

CBS Account Creation & Product Setup
Test Scenario ID: TS-CBS-001
Test Scenario Title: Customer & Account Creation
Objective: Validate CBS customer profile and account creation

| Test Case ID | Test Case Description | Test Steps | Expected Result | Test Data |
| --- | --- | --- | --- | --- |
| TC-CBS-001 | Verify customer profile creation in CBS | 1. Complete KYC and AML<br>2. Send customer data to CBS<br>3. Create customer profile<br>4. Receive customer ID<br>5. Store response | Customer profile created successfully | Verified customer record |
| TC-CBS-002 | Verify savings account | 1. Create CBS customer<br>2. Select Product<br>3. Invoke account creation API<br>4. Generate account number<br>5. Confirm account setup | Savings account created successfully | Product SAV001 |

Test Scenario ID: TS-CBS-002
Test Scenario Title: Product Mapping
Objective: Validate product setup and eligibility rules

| Test Case ID | Test Case Description | Test Steps | Expected Result | Test Data |
| --- | --- | --- | --- | --- |
| TC-CBS-003 | Verify valid product mapping | 1. Select savings account<br>2. Retrieve product code<br>3. Validate configuration<br>4. Create account<br>5. Review response | Correct product mapped and account created` | SAV001 |
| TC-CBS-004 | Verify invalid product code handling | 1. Select invalid product<br>2. Trigger validation<br>3. Attempt account creation<br>4. Review error response<br>5. Log Failure | Account creation blocked | INVALID001 |

Notification & Exception Handling
Test Scenario ID: TS-NOT-001
Test Scenario Title: Customer Notification
Objective: Validate onboarding notifications

| Test Case ID | Test Case Description | Test Steps | Expected Result | Test Data |
| --- | --- | --- | --- | --- |
| TC-NOT-001 | Verify onboarding success notification | 1. Complete onboarding<br>2. Create account<br>3. Trigger notification service<br>4. Send SMS/email<br>5. Verify delivery | Customer receives success notification | Registered email/mobile |
| TC-NOT-002 | Verify KYC failure notification | 1. Trigger KYC failure<br>2. Generate notification event<br>3. Send SMS/email<br>4. Verify content<br>5. Confirm delivery | Customer receives failure notification with reason | Invalid SSN |

Test Scenario ID: TS-NOT-002
Test Scenario Title: Exception Handling & Retry Login
Objective: Validate retry and operations queue workflow

| Test Case ID | Test Case Description | Test Steps | Expected Result | Test Data |
| --- | --- | --- | --- | --- |
| TC-NOT-003 | Verify KYC API retry mechanism | 1. Trigger API timeout<br>2. Execute first retry<br>3. Execute second retry<br>4. Evaluate response<br>5. Update application status | System retries twice before failure | API unavailable |
| TC-NOT-004 | Verify operations queue assignment | 1. Exceed retry limit<br>2. Create exception case<br>3. Assign operations queue<br>4. Notify operations team<br>5. Track SLA | Case moved to Operations Review Queue | Repeated API failure |
