# 📄 Testing Documentation – ERP System  
**Prepared By:** *Vinay Shah (SQC Candidate)*  
**Branch:** `VinayShah_Testing_SQC`  
**PR Number:** #26  
**Assignment:** SQC Evaluation – Test & Find Everything Wrong With the System  

---
## 🔰 1. Introduction  
This document contains all testing work performed on the ERP-System as part of the SQC evaluation.  
It includes test scenarios, test cases, bug reports, observations, and improvement suggestions.  
All updates are committed daily to the **same branch and PR** as per instructions.
# Bug Report and Test Cases
--------------------------------------------------------------------------------------------------------------------
Bug Report 1: Login & Logout Feature Not Working

Title: Login and Logout functionality not working / possibly not implemented
Severity: High
Priority: High

Description:
The application does not perform login or logout actions. When valid credentials are entered, no navigation or authentication occurs. Logout button also does not respond, indicating the functionality may be missing or incomplete.

Steps to Reproduce:

Open the application

Enter valid username and password

Click on Login

Observe behavior

After login (if login works), click on Logout

Expected Result:

Login should validate credentials and redirect user to dashboard/home page

Logout should end the session and redirect user to the login page

Actual Result:

Login button does nothin

Logout function not implemented / no response

Evidence:

No UI movement or request triggered on logout click

Logout button non-functional




# Bug Report and Test Cases


| Bug ID | Description | Location | Severity | Test Case |
| :--- | :--- | :--- | :--- | :--- |
| BUG-001 | Hardcoded API Key in `initialiseFeedback` and `initialiseHelpbot` | `gtvl-management-portal/app.js` (Lines 884, 911) | High | 1. Open `app.js`.<br>2. Search for "apiKey".<br>3. Verify that the key is hardcoded in the source. |
| BUG-002 | Sensitive User Data Stored in Local Storage | `gtvl-management-portal/app_data.js` & `management_dashboard.html` | High | 1. Open the application in a browser.<br>2. Open Developer Tools (F12).<br>3. Go to Application > Local Storage.<br>4. Verify that "users" key contains plain text user data including emails and phone numbers. |
| BUG-003 | Logic Error: Unassigned Supervisor Calculation | `gtvl-management-portal/management_dashboard.html` (Line 788) | Medium | 1. Set up data with 1 supervisor assigned to 2 stores.<br>2. Check "Unassigned Supervisors" count.<br>3. Expected: Count should decrease by 1.<br>4. Actual: Count might be incorrect if it assumes 1:1 mapping. |
| BUG-004 | Logic Error: Store Coverage Calculation | `gtvl-management-portal/management_dashboard.html` (Line 800) | Medium | 1. Assign 2 supervisors to the same store.<br>2. Check "Stores with Supervisors" count.<br>3. Expected: Count should be 1 (unique store).<br>4. Actual: Count will be 2 (based on allocation count). |
| BUG-005 | Missing Error Handling for JSON Parsing | `gtvl-management-portal/management_dashboard.html` (Line 775) | Medium | 1. Open Developer Tools.<br>2. Run `localStorage.setItem('users', 'invalid-json')`.<br>3. Reload the page.<br>4. Verify if the dashboard crashes or shows empty data without user feedback. |
| BUG-006 | External Script Dependency without Fallback | `gtvl-management-portal/app.js` (Lines 875, 906, 938) | Medium | 1. Block network requests to `*.tiram.app` using DevTools Network blocking.<br>2. Reload the page.<br>3. Verify if the application handles the missing scripts gracefully or throws errors. |
| BUG-007 | Potential XSS via innerHTML | `gtvl-management-portal/app.js` (Line 725) | Low | 1. Review `app.js`.<br>2. Identify usage of `innerHTML` to inject modal content.<br>3. Although currently static, verify if any dynamic variables are ever interpolated into this string. |
| BUG-008 | Hardcoded Prototype Data Initialization | `gtvl-management-portal/app_data.js` | Low | 1. Clear Local Storage.<br>2. Reload the page.<br>3. Verify that `app_data.js` re-initializes with hardcoded mock data, potentially overwriting any real state if logic changes. |
| BUG-009 | Potential CSV Injection in Transaction Export | `gtvl-sales-analytics-dashboard/transaction_history.html` | Medium | 1. Modify a transaction record in Local Storage to start with `=cmd|' /C calc'!A0`.<br>2. Export transactions to CSV.<br>3. Open CSV in Excel and check if it attempts to execute the formula. |
| BUG-010 | Timezone Inconsistency in Date Filters | `gtvl-sales-analytics-dashboard/dashboard.html` | Low | 1. Set system time to a timezone significantly different from UTC.<br>2. Filter transactions for "Today".<br>3. Verify if transactions from late previous day (UTC) are included/excluded correctly. |
