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
