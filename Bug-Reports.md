# API Sample Defect Reports

> These are portfolio-style sample defects/validation observations. They should be verified against the current API contract before being described as actual defects.

## BUG-API-001 — Missing required-field validation
**Severity:** Medium | **Priority:** Medium  
**Scenario:** POST /posts without a title.  
**Expected:** Contract validation rejects incomplete payload.  
**Observed in a mock test scenario:** Request may be accepted because JSONPlaceholder is a practice/mock API.  
**QA Note:** This is a contract-validation observation, not necessarily a defect in the service.

## BUG-API-002 — DELETE behavior requires contract verification
**Severity:** Low | **Priority:** Low  
**Scenario:** DELETE /posts/1 followed by GET /posts/1.  
**Expected:** A persistent API should document whether deletion is durable.  
**Observed/Question:** JSONPlaceholder simulates responses and does not behave like a persistent production database.  
**QA Note:** Verify requirements before logging this as a production defect.

## BUG-API-003 — No authentication layer in practice API
**Severity:** Informational  
**Scenario:** Access endpoints without credentials.  
**Expected:** Depends entirely on the API's security requirements.  
**Observed:** Practice endpoint is publicly accessible.  
**QA Note:** Not a defect for a deliberately public demo API.
