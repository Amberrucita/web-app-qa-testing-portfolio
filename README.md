# Web Application QA Testing & Marketing Validation

## 📌 Project Overview
This repository contains the comprehensive Quality Assurance (QA) documentation and test assets for a web application registration and email delivery system. It showcases my ability to create structured test plans, author detailed test cases, and execute manual functional and regression testing.

## 🛠️ Tools & Technologies Used
*   **Test Management & Bug Tracking:** Jira / Trello
*   **API Testing (Basic):** Postman
*   **Environment Validation:** Chrome DevTools (Cross-browser and mobile responsiveness testing)
*   **Documentation:** Markdown / Google Sheets

## 📂 Deliverables Included in this Repository
*   `Test_Plan_Registration_System.pdf` (or copy text below) - High-level strategy for the testing cycle.
*   `Test_Cases_Suite.xlsx` - A collection of 30+ detailed manual test cases covering functional, negative, and edge-case scenarios.
*   `Bug_Reports.md` - Structured logs of identified defects with steps to reproduce and severity ratings.

## 📝 Sample Test Case Structure

| Test Case ID | Description | Pre-conditions | Test Steps | Expected Result | Status |
|---|---|---|---|---|---|
| TC-001 | Verify successful user registration with valid data | User is on signup page | 1. Enter valid email<br>2. Enter strong password<br>3. Click Submit | Account created & Welcome Email received | PASSED |
| TC-002 | Verify signup fails with an invalid email format | User is on signup page | 1. Enter "amber@invalid"<br>2. Enter valid password<br>3. Click Submit | Error message displays: "Invalid email format" | PASSED |
### 3. Customer Support Workflow & Helpdesk Integration Validation (Simulation)
*   **Trigger Mapping:** Verified that user interactions (e.g., failed payments, refund requests) successfully fire correct API webhooks to create automated, high-priority support tickets inside the CRM.
*   **SLA & Routing Automation:** Tested conditional routing logic ensuring ticket dispatches match specific category tags (e.g., routing technical issues to Tier 2 Support, and billing queries to Finance).
*   **Macros & Saved Replies Validation:** Conducted QA audits on pre-formatted templates to ensure zero formatting bugs and correct dynamic token rendering before customer-facing deployment.
## 🔍 Testing Types Executed
*   **Functional Testing:** Validated core features like user signup, login, and form validations.
*   **Regression Testing:** Re-tested simulated bug fixes to ensure existing workflows remained unbroken.
*   **UI/UX & Responsiveness Testing:** Verified that all email notifications and web forms render 100% correctly across mobile, tablet, and desktop viewports.

---
*Created by [Amber Rucita Rahma](https://linkedin.com)*
