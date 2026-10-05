# Comprehensive Bug Reports & Defect Logs

This document contains the structured bug reports identified during the execution of the test suite for the Web Application Registration and Email Delivery System. Each report is documented using standard industry formatting to ensure clear communication with the development team.

---

## 🐛 Bug Log Overview

| Bug ID | Component | Defect Description | Severity | Status |
| :--- | :--- | :--- | :--- | :--- |
| **BUG-001** | User Registration | System accepts invalid email format "amber@invalid" without validation | **High** | Open |
| **BUG-002** | Email Automation | Welcome Email personalization token fails to render, showing raw placeholder | **Medium** | Open |

---

## Detailed Defect Documentation

### 🔴 BUG-001: Missing Email Format Validation on Sign-Up Form

*   **Bug ID:** BUG-001
*   **Component:** User Registration / Frontend Form
*   **Severity:** High (Functional defect breaking standard validation rules)
*   **Status:** Open

#### Description:
The registration form fails to validate the structure of the email address field during submission. The system allows users to create accounts using incomplete formats (e.g., missing top-level domains like `.com` or `.co.id`), which breaks data integrity and downstream email marketing syncs.

#### Environment:
*   **Environment:** Staging / Mock QA Environment
*   **Browsers Tested:** Google Chrome (v144.0), Apple Safari (v19.2)

#### Steps to Reproduce:
1. Navigate to the application sign-up page.
2. Enter any username and type `amber@invalid` in the Email field.
3. Enter a valid strong password (e.g., `SecurePass2026!`).
4. Click the **"Sign Up"** button.

#### Expected Result:
The form submission should be blocked, and an inline error message should display: `"Please enter a valid email address."` (As mapped in **TC-003**).

#### Actual Result:
The system bypasses validation, submits the form, creates a database entry with the invalid email, and redirects the user to the active dashboard.

#### Suggested Fix:
Implement a robust frontend regex validation check on the email input field before firing the submit API request. Ensure the backend database also triggers a `400 Bad Request` validation error if unsafe or malformed email strings bypass the UI.

---

### 🟡 BUG-002: Welcome Email Renders Raw Personalization Token Placeholder

*   **Bug ID:** BUG-002
*   **Component:** Marketing Automation / Email Template Rendering
*   **Severity:** Medium (UX issue that degrades brand presentation)
*   **Status:** Open

#### Description:
When a new user completes registration, the automated Welcome Email triggered via webhook fails to dynamically pull the user's first name. Instead of rendering the actual name, the email body displays the raw fallback code placeholder.

#### Environment:
*   **Integration Platform:** ActiveCampaign Workflow API Integration
*   **Recipient Client:** Gmail Web App & iOS Mail

#### Steps to Reproduce:
1. Complete a successful registration using the first name `Amber`.
2. Wait for the instant **"Welcome Email"** webhook to fire (As mapped in **TC-010**).
3. Access the recipient's Gmail inbox and open the received campaign email.
4. Read the greeting line at the top of the body copy.

#### Expected Result:
The dynamic text greeting token should render cleanly as: `"Hi Amber,"` (As mapped in **TC-012**).

#### Actual Result:
The greeting line displays the raw system script parameter: `"Hi {{ contact.first_name }},"`.

#### Suggested Fix:
Verify the data payload properties inside the registration webhook payload (`user.signup`). Ensure that the field name mapped on the web platform matches the database custom field identifier configured within the ActiveCampaign/HubSpot contact matrix.

---
*Maintained and documented by [Amber Rucita Rahma](https://linkedin.com)*
