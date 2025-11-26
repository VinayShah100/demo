📄 Testing Documentation – Promodizer Module

Prepared By: Vinay Shah (SQC Candidate)
Branch: VinayShah_Testing_SQC
PR Number: TBD
Assignment: SQC Evaluation – Test & Identify All Issues in Promodizer Module

🔰 1. Introduction

This document contains all testing work completed on the Promodizer Management Module as part of the SQC evaluation.
It includes:

Test scenarios

Detailed bug reports

UI/UX issues

Functional breakdowns

Security findings

Data validation issues

Workflow defects

Additional observations

All findings are structured in a GitHub-friendly format with clear severity, reproduction steps, and evidence references.
All updates will be pushed to the same branch and PR, following standard QA submission guidelines.

🐞 Bug Report & Test Cases

Below is the full list of validated defects, documented in professional QA format.

🔥 Major Bug Report 1: Form Allows Invalid Input & “Create Promodizer” Still Enables

Title: Validation Not Working for Create Promodizer Form
Severity: High
Priority: High

Description

The Create Promodizer form accepts invalid data (special characters, wrong formats, incorrect phone/email) and still enables the Create Promodizer button. No field-level validation appears.

Steps to Reproduce

Open promodizer_create.html

Enter invalid values:

First Name: @#$%

Last Name: %%%

Employee ID: PRO

Phone: 000-000-0000

Email: hhh@gamil.com

Observe Create button

Submit form

Expected Result

Form should block submission until all fields are valid

Field-level red error indicators must appear

Actual Result

Button activates

Form allows invalid entries

No errors displayed

Evidence

Invalid entries saved & visible in Promodizer list.

🐞 Consolidated Bug Summary Table
Bug ID	Description	Location	Severity	Test Case
BUG-001	Create Form accepts invalid characters & enables button	promodizer_create.html	High	Enter invalid data → Create button becomes active
BUG-002	System saves invalid Promodizer data	Promodizer List	Critical	Create invalid Promodizer → List displays it
BUG-003	Long names break table layout	Promodizer List	High	Add long string → Table overflows
BUG-004	Employee ID accepts wrong formats	Create & List	High	Enter 98998 → Saved & displayed
BUG-005	Invalid email values accepted	Create Screen	Medium	Enter malformed email → Form accepts
BUG-006	Incorrect phone numbers accepted	Create Screen	Medium	Enter 999-999-9999 → Accepted
BUG-007	Table allows special characters (XSS risk)	Promodizer List	High	Enter <script> or special chars
BUG-008	Horizontal scroll breaks alignment	Promodizer List	Medium	Scroll horizontally
BUG-009	Action icons shift out of alignment	Table Rows	Medium	Long text pushes icons
BUG-010	Action icons become unclickable	Table Rows	High	UI layer block
BUG-011	“View Promodizer” does not work	View Icon	High	Click → no response
BUG-012	“Edit Promodizer” not functioning	Edit Icon	High	Click → nothing happens
BUG-013	Delete action extremely slow	Delete Icon	Medium–High	Click → delay
BUG-014	Logout does not clear session (Security Bug)	Header Logout	High	Logout → Back → Dashboard accessible
BUG-015	UI overlaps on small screens	Table Area	Medium	Feedback/chat icon blocks icons
BUG-016	Chatbot icon overlaps action icons	Lower-right widget	Medium–High	Hard to click Edit/Delete
BUG-017	Search bar returns incorrect results	Search Input	High	Search “kml” → Unrelated result shown
BUG-018	Status dropdown slow & unresponsive	Filters	Medium	Requires multiple clicks
BUG-019	Status dropdown arrow misaligned	Filters	Low	UI cosmetic issue
BUG-020	Sorting functionality missing	Column Headers	Medium	Click headers → nothing
BUG-021	Breadcrumb navigation not working	Page Header	Medium–High	Click Dashboard → nothing
BUG-022	Browser back button behaves incorrectly	All pages	Medium	Back → wrong/partial navigation
BUG-023	Pagination missing for long lists	List Page	Medium	Long table → scroll only
BUG-024	Search + Filter combination returns wrong results	Filters	High	Search + status → incorrect
BUG-025	“Clear Filters” does not fully reset table	Filters	Medium	Search stays or table not refreshed
BUG-026	Table header shifts while horizontal scrolling	List Page	Medium	Header misalignment
🧪 Additional Notes

Most issues stem from missing validation, poor UI layout handling, and non-functional buttons.

Security concerns exist due to session persistence after logout.

Data integrity is heavily affected due to unrestricted input.

Search, filter, sort, pagination → all require implementation or fixes.

📌 Summary

✔ Major functional issues found
✔ Validation rules missing across system
✔ UI breaks easily with long text
✔ Core features (View, Edit, Delete) not functional
✔ Search/Filter/Pagination incomplete
✔ Logout insecure
✔ Table rendering unstable
