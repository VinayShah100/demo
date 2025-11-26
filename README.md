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

---

# Bug Reporting Form Implementation

Here is the code to implement the Bug Reporting Form.

## 1. Update `gtvl-management-portal/app_data.js`

Add the `bugs` collection to the `AppData.init` function.

```javascript
// Inside AppData.init(), add this after the users collection:






# 📄 Testing Documentation – Promodizer Module  
**Prepared By:** *Vinay Shah (SQC Candidate)*  
**Branch:** `VinayShah_Testing_SQC`  
**PR Number:** TBD  
**Assignment:** SQC Evaluation – Test & Identify All Issues in Promodizer Module  

---

## 🔰 1. Introduction  
This README contains all testing work completed on the **Promodizer Management Module** for the SQC evaluation.  
It includes:

- Test scenarios  
- Detailed bug reports  
- UI/UX issues  
- Functional defects  
- Security findings  
- Validation errors  
- Workflow issues  
- Additional observations  

All findings follow professional QA documentation standards.  
All updates are committed to the **same branch and same PR**, as per instructions.

---

# 🐞 Bug Report & Test Cases  
Below is the **full list of validated defects**, written in a clean GitHub-supported format.

---

# 🔥 Major Bug Report 1: Form Allows Invalid Input but “Create Promodizer” Button Activates  
**Title:** Validation Not Working on Create Promodizer Form  
**Severity:** High  
**Priority:** High  

### **Description**  
The form accepts invalid characters and incorrect formats, but the **Create Promodizer** button still becomes active. No error messages are shown.

### **Steps to Reproduce**
1. Open `promodizer_create.html`
2. Enter invalid values:  
   - First Name: `@#$%`  
   - Last Name: `%%%`  
   - Employee ID: `PRO`  
   - Phone: `000-000-0000`  
   - Email: `hhh@gamil.com`
3. Observe button state  
4. Submit form  

### **Expected Result**
- Form should prevent submission  
- Field-level validation errors must appear  

### **Actual Result**
- Button activates  
- Invalid data is accepted  
- No validation displayed  

### **Evidence**
Invalid entries appear in the Promodizer list.

---

# 🐞 Consolidated Bug Summary Table

| Bug ID | Description | Location | Severity | Test Case |
|--------|-------------|----------|----------|-----------|
| **BUG-001** | Create form accepts invalid characters & enables button | promodizer_create.html | High | Enter invalid data → Button becomes active |
| **BUG-002** | System saves invalid Promodizer data | Promodizer List | Critical | Submit invalid form → Data appears in list |
| **BUG-003** | Long names break table layout | List Table | High | Add long text → Table overflows |
| **BUG-004** | Employee ID accepts incorrect formats | Create + List | High | Enter `98998` → Accepted |
| **BUG-005** | Invalid email accepted | Create Form | Medium | Enter malformed email → Accepted |
| **BUG-006** | Invalid phone numbers accepted | Create Form | Medium | Enter `999-999-9999` → Accepted |
| **BUG-007** | Table accepts special characters (XSS risk) | Promodizer List | High | Enter `<script>` or symbols |
| **BUG-008** | Horizontal scroll breaks alignment | Table Layout | Medium | Scroll → Header & content misaligned |
| **BUG-009** | Action icons shift out of alignment | Table Rows | Medium | Long text pushes icons |
| **BUG-010** | Action icons become unclickable | Table Rows | High | UI overlaps icons |
| **BUG-011** | View Promodizer does not work | View Icon | High | Click → No response |
| **BUG-012** | Edit Promodizer does nothing | Edit Icon | High | Click → No action |
| **BUG-013** | Delete action delayed | Table Operations | Medium–High | Click → Long delay |
| **BUG-014** | Logout does not clear session (Security Bug) | Logout Button | High | Logout → Back → Dashboard accessible |
| **BUG-015** | UI overlaps on smaller screens | Table Layout | Medium | Chat/Feedback buttons block actions |
| **BUG-016** | Chatbot icon overlaps table action icons | Bottom-right widget | Medium–High | Clicks blocked |
| **BUG-017** | Search bar returns incorrect results | Search Input | High | Search “kml” → Still shows invalid entries |
| **BUG-018** | Status dropdown slow/unresponsive | Filters | Medium | Multiple clicks required |
| **BUG-019** | Status dropdown arrow misaligned | Filters | Low | Cosmetic UI issue |
| **BUG-020** | Sorting not implemented | Column Headers | Medium | Click → No sorting |
| **BUG-021** | Breadcrumb navigation non-functional | Page Header | Medium–High | Click Dashboard → No action |
| **BUG-022** | Browser back button behaves incorrectly | All Pages | Medium | Back → Wrong/partial navigation |
| **BUG-023** | Pagination missing for long tables | List Table | Medium | Many entries → No pagination |
| **BUG-024** | Search + Filter combo gives wrong results | Filters | High | Both applied → Incorrect list output |
| **BUG-025** | Clear Filters does not fully reset state | Filters | Medium | Search remains or table doesn’t refresh |
| **BUG-026** | Table header shifts during horizontal scroll | List Table | Medium | Header misaligned with columns |

---

## 📌 Summary of Findings  
✔ Critical validation and data integrity issues  
✔ Multiple UI/UX layout failures  
✔ Key functionality (View/Edit/Delete) non-working  
✔ Search, filter, sorting, pagination all require fixes  
✔ Logout security vulnerability  
✔ Table layout unstable with long text  
✔ System is not production-ready  

---

## ✅ Additional Work Available  
If needed, I can generate:

- ✔ Full **Test Case Document**  
- ✔ Full **Bug Report Document**  
- ✔ **PR Description** for your GitHub pull request  
- ✔ **Screenshots Section**  
- ✔ **Recommendations for Developers**  

Just say: **“Write PR Description”**, **“Generate Test Cases”**, or **“Create Suggestions Section”**.
