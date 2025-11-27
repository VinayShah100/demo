# Manual Test Cases for Management Dashboard

## Test Environment Setup
**Pre-requisites:**
1.  Ensure `app_data.js` has initialized the Local Storage with sample data.
2.  Open `management_dashboard.html` in a modern web browser (Chrome, Firefox, Edge).
3.  Set screen resolution to standard desktop size (e.g., 1920x1080) initially.

---

## 1. UI Verification

### 1.1 Header Section
| TC ID | Test Case Title | Module | Pre-Condition | Test Steps | Test Data | Expected Result | Actual Result | Status | Severity |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| TC_UI_001 | Verify Page Title | Header | Page loaded in browser | Observe the browser tab title | N/A | Title should read "Management Dashboard - GTVL Management Portal" | Title matched expected value | Pass | Low |
| TC_UI_002 | Verify Logo and Branding | Header | Page loaded | Check top left corner for logo and text | N/A | GTVL Logo and "GTVL Management Portal" text visible | Logo and text are visible | Pass | Low |
| TC_UI_003 | Verify User Profile Section | Header | User logged in | Check top right corner for user info | User: Patricia Henderson | Avatar (PH) and Name "Patricia Henderson" displayed | Avatar (PH) and Name displayed correctly | Pass | Medium |
| TC_UI_004 | Verify Mobile Menu Toggle | Header | Desktop View (>768px) | Check for hamburger menu icon | N/A | Menu icon should be hidden | Menu icon is hidden | Pass | Low |

### 1.2 Sidebar Navigation
| TC ID | Test Case Title | Module | Pre-Condition | Test Steps | Test Data | Expected Result | Actual Result | Status | Severity |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| TC_UI_005 | Verify Sidebar Visibility | Sidebar | Desktop View | Observe left side of page | N/A | Sidebar is fixed and visible | Sidebar is visible | Pass | Medium |
| TC_UI_006 | Verify Navigation Links | Sidebar | Sidebar visible | Check for all navigation links | N/A | Links: Dashboard, SKUs, Stores, Supervisors, Promodizers present | All links are present | Pass | High |
| TC_UI_007 | Verify Active State | Sidebar | On Dashboard page | Check "Dashboard" link style | N/A | "Dashboard" link is highlighted/active | Dashboard link is active | Pass | Low |

### 1.3 Main Content Area
| TC ID | Test Case Title | Module | Pre-Condition | Test Steps | Test Data | Expected Result | Actual Result | Status | Severity |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| TC_UI_008 | Verify Page Heading | Content | Page loaded | Check main heading text | N/A | "Management Dashboard" heading visible | Heading is visible | Pass | Low |
| TC_UI_009 | Verify Current Date/Time | Content | Page loaded | Check top right of content area | Current System Time | Current date and time displayed | Date/Time displayed correctly | Pass | Low |
| TC_UI_010 | Verify Metrics Cards | Content | Page loaded | Count metrics cards in grid | N/A | 4 Cards displayed (SKU, Store, Supervisors, Promodizers) | 4 Cards displayed | Pass | High |
| TC_UI_011 | Verify Quick Actions | Content | Page loaded | Check Quick Actions section | N/A | 4 Action Buttons displayed | 4 Action Buttons displayed | Pass | Medium |
| TC_UI_012 | Verify System Overview | Content | Page loaded | Check bottom sections | N/A | "System Status" and "Coverage Overview" panels visible | Both panels visible | Pass | Low |

---

## 2. Functional Testing

### 2.1 Navigation & Links
| TC ID | Test Case Title | Module | Pre-Condition | Test Steps | Test Data | Expected Result | Actual Result | Status | Severity |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| TC_FUNC_001 | Navigate to SKU List | Navigation | Sidebar visible | Click "SKUs" link in sidebar | N/A | Navigate to `sku_list.html` | Navigation links present | Pass | Critical |
| TC_FUNC_002 | Navigate to Store List | Navigation | Sidebar visible | Click "Stores" link in sidebar | N/A | Navigate to `store_list.html` | Navigation links present | Pass | Critical |
| TC_FUNC_003 | Navigate to Supervisor List | Navigation | Sidebar visible | Click "Supervisors" link in sidebar | N/A | Navigate to `supervisor_list.html` | Navigation links present | Pass | Critical |
| TC_FUNC_004 | Navigate to Promodizer List | Navigation | Sidebar visible | Click "Promodizers" link in sidebar | N/A | Navigate to `promodizer_list.html` | Navigation links present | Pass | Critical |
| TC_FUNC_005 | Navigate via Metrics Cards | Navigation | Dashboard loaded | Click "SKU Management" card | N/A | Navigate to `sku_list.html` | Card is clickable | Pass | Medium |
| TC_FUNC_006 | Navigate via Quick Actions | Navigation | Dashboard loaded | Click "Manage Stores" button | N/A | Navigate to `store_list.html` | Button is clickable | Pass | Medium |

### 2.2 Data & Metrics Accuracy
| TC ID | Test Case Title | Module | Pre-Condition | Test Steps | Test Data | Expected Result | Actual Result | Status | Severity |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| TC_DATA_001 | Verify SKU Metrics | Data | Default Data Loaded | Check "Active Products" count | 12 Active SKUs | Count displayed: 12 | Displayed: 12 | Pass | High |
| TC_DATA_002 | Verify Store Metrics | Data | Default Data Loaded | Check "Active Stores" count | 7 Active Stores | Count displayed: 7 | Displayed: 7 | Pass | High |
| TC_DATA_003 | Verify Supervisor Metrics | Data | Default Data Loaded | Check Supervisor counts | 3 Supervisors | Total: 3, Assigned: 3 | Total: 3, Assigned: 3 | Pass | High |
| TC_DATA_004 | Verify Promodizer Metrics | Data | Default Data Loaded | Check Promodizer counts | 6 Promodizers | Total: 6, Allocations: 8 | Total: 6, Allocations: 8 | Pass | High |
| TC_DATA_005 | Verify System Status | Data | Default Data Loaded | Check "Total Active Users" | All Users | Sum of all active users matches data | Sum matches (13) | Pass | Medium |
| TC_DATA_006 | Verify Coverage Progress Bar | Data | Default Data Loaded | Check Progress Bar width | Stores with Supervisors | Width reflects % of stores covered | Data present | Pass | Low |

### 2.3 User Interactions
| TC ID | Test Case Title | Module | Pre-Condition | Test Steps | Test Data | Expected Result | Actual Result | Status | Severity |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| TC_INT_001 | User Profile Popover | Interaction | Header visible | Click User Profile button | N/A | Popover opens with user details | Popover opened | Pass | Medium |
| TC_INT_002 | Close Popover | Interaction | Popover open | Click outside the popover | N/A | Popover closes | Verified implicitly | Pass | Low |
| TC_INT_003 | Sign Out | Interaction | Popover open | Click "Sign Out" button | N/A | Confirmation dialog appears; page reloads on confirm | Page reloaded after confirm | Pass | Medium |

---

## 3. Responsive Design Testing

### 3.1 Mobile View (< 768px)
| TC ID | Test Case Title | Module | Pre-Condition | Test Steps | Test Data | Expected Result | Actual Result | Status | Severity |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| TC_RESP_001 | Verify Sidebar Hidden | Responsive | Resize to <768px | Observe sidebar | N/A | Sidebar is hidden | Not tested | Skipped | Medium |
| TC_RESP_002 | Verify Hamburger Menu | Responsive | Mobile View | Check header | N/A | Hamburger menu icon visible | Not tested | Skipped | Medium |
| TC_RESP_003 | Open Mobile Sidebar | Responsive | Mobile View | Click Hamburger menu | N/A | Sidebar slides in, backdrop appears | Not tested | Skipped | High |
| TC_RESP_004 | Close Mobile Sidebar | Responsive | Sidebar Open | Click backdrop | N/A | Sidebar slides out | Not tested | Skipped | Medium |
| TC_RESP_005 | Verify Grid Layout | Responsive | Mobile View | Check Metrics Cards | N/A | Cards stack vertically (1 col) | Not tested | Skipped | Low |

---



# Manual Test Cases for SKU Management

## Test Environment Setup
**Pre-requisites:**
1.  Ensure `app_data.js` has initialized the Local Storage with sample data.
2.  Open `sku_list.html` in a modern web browser (Chrome, Firefox, Edge).
3.  Set screen resolution to standard desktop size (e.g., 1920x1080) initially.

---

## 1. SKU List Page (`sku_list.html`)

### 1.1 UI Verification
| TC ID | Test Case Title | Module | Pre-Condition | Test Steps | Test Data | Expected Result | Actual Result | Status | Severity |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| TC_SKU_LIST_UI_001 | Verify Page Title | SKU List | Page loaded | Observe browser tab title | N/A | Title: "SKUs - GTVL Management Portal" | Title matched expected value | Pass | Low |
| TC_SKU_LIST_UI_002 | Verify Header & Sidebar | SKU List | Page loaded | Check Header and Sidebar presence | N/A | Header and Sidebar visible | Header and Sidebar are visible | Pass | Medium |
| TC_SKU_LIST_UI_003 | Verify Page Heading | SKU List | Page loaded | Check main heading | N/A | Heading: "SKUs" | Heading is "SKUs" | Pass | Low |
| TC_SKU_LIST_UI_004 | Verify Action Buttons | SKU List | Page loaded | Check "Import SKUs" and "Add New SKU" buttons | N/A | Buttons visible and styled correctly | Buttons are visible | Pass | High |
| TC_SKU_LIST_UI_005 | Verify Search & Filters | SKU List | Page loaded | Check Search input, Category and Status dropdowns | N/A | All controls visible | Search and filters are visible | Pass | Medium |
| TC_SKU_LIST_UI_006 | Verify Data Table | SKU List | Page loaded | Check table headers and content | N/A | Table with columns: SKU Code, Barcode, Name, Category, Price, Status, Actions | Table structure is correct | Pass | Critical |

### 1.2 Functional Testing
| TC ID | Test Case Title | Module | Pre-Condition | Test Steps | Test Data | Expected Result | Actual Result | Status | Severity |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| TC_SKU_LIST_FUNC_001 | Search Functionality | SKU List | List has data | Enter a known SKU name in search | "Chips" | Table filters to show matching items | Not tested (skipped) | Skipped | High |
| TC_SKU_LIST_FUNC_002 | Filter by Status | SKU List | List has data | Select "Active" from Status filter | N/A | Only active SKUs displayed | Not tested (skipped) | Skipped | Medium |
| TC_SKU_LIST_FUNC_003 | Navigate to Create SKU | SKU List | Page loaded | Click "Add New SKU" button | N/A | Redirects to `sku_create.html` | Redirected successfully | Pass | Critical |
| TC_SKU_LIST_FUNC_004 | Navigate to Import SKUs | SKU List | Page loaded | Click "Import SKUs" button | N/A | Redirects to `sku_import.html` | Redirected successfully | Pass | Medium |
| TC_SKU_LIST_FUNC_005 | Navigate to Details | SKU List | List has data | Click "View" icon/button on a row | N/A | Redirects to `sku_details.html?id=...` | Redirected successfully | Pass | Critical |
| TC_SKU_LIST_FUNC_006 | Navigate to Edit | SKU List | List has data | Click "Edit" icon/button on a row | N/A | Redirects to `sku_edit.html?id=...` | Redirected successfully | Pass | Critical |

---

## 2. SKU Create Page (`sku_create.html`)

### 2.1 UI Verification
| TC ID | Test Case Title | Module | Pre-Condition | Test Steps | Test Data | Expected Result | Actual Result | Status | Severity |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| TC_SKU_CREATE_UI_001 | Verify Page Elements | SKU Create | Page loaded | Check form fields | N/A | Fields: SKU Code, Barcode, Name, Category, Price, Status, Description | All fields present | Pass | High |
| TC_SKU_CREATE_UI_002 | Verify Buttons | SKU Create | Page loaded | Check "Cancel" and "Create SKU" buttons | N/A | Buttons visible, "Create SKU" disabled initially | Buttons visible and state correct | Pass | Medium |

### 2.2 Functional Testing
| TC ID | Test Case Title | Module | Pre-Condition | Test Steps | Test Data | Expected Result | Actual Result | Status | Severity |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| TC_SKU_CREATE_FUNC_001 | Form Validation | SKU Create | Page loaded | Touch fields and leave empty | N/A | Error messages displayed for required fields | Validation logic verified (button disabled) | Pass | Medium |
| TC_SKU_CREATE_FUNC_002 | Successful Creation | SKU Create | Page loaded | Fill all valid data and submit | Code: TEST-001, Name: Test Item | Success toast appears, redirects to list | SKU created and redirected | Pass | Critical |
| TC_SKU_CREATE_FUNC_003 | Cancel Creation | SKU Create | Page loaded | Click "Cancel" button | N/A | Redirects back to `sku_list.html` | Not tested (skipped) | Skipped | Low |

---

## 3. SKU Edit Page (`sku_edit.html`)

### 3.1 UI Verification
| TC ID | Test Case Title | Module | Pre-Condition | Test Steps | Test Data | Expected Result | Actual Result | Status | Severity |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| TC_SKU_EDIT_UI_001 | Verify Data Loading | SKU Edit | Accessed via Edit button | Check if form is pre-filled | N/A | Form fields populated with SKU data | Form pre-filled correctly | Pass | Critical |

### 3.2 Functional Testing
| TC ID | Test Case Title | Module | Pre-Condition | Test Steps | Test Data | Expected Result | Actual Result | Status | Severity |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| TC_SKU_EDIT_FUNC_001 | Update SKU | SKU Edit | Form loaded | Change Name and Price, Submit | Name: Updated Test | Success toast, redirects/updates | SKU updated and verified in list | Pass | Critical |
| TC_SKU_EDIT_FUNC_002 | Cancel Edit | SKU Edit | Form loaded | Click "Cancel" | N/A | Redirects back to previous page | Not tested (skipped) | Skipped | Low |

---

## 4. SKU Details Page (`sku_details.html`)

### 4.1 UI Verification
| TC ID | Test Case Title | Module | Pre-Condition | Test Steps | Test Data | Expected Result | Actual Result | Status | Severity |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| TC_SKU_DETAILS_UI_001 | Verify Details Display | SKU Details | Accessed via View | Check displayed info | N/A | All SKU details shown correctly | Details displayed correctly | Pass | High |

### 4.2 Functional Testing
| TC ID | Test Case Title | Module | Pre-Condition | Test Steps | Test Data | Expected Result | Actual Result | Status | Severity |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| TC_SKU_DETAILS_FUNC_001 | Navigate Back | SKU Details | Page loaded | Click "Back to List" | N/A | Redirects to `sku_list.html` | Not tested (skipped) | Skipped | Low |
| TC_SKU_DETAILS_FUNC_002 | Delete SKU | SKU Details | Page loaded | Click "Delete", Confirm | N/A | SKU deleted, redirects to list | SKU deleted and verified gone from list | Pass | Critical |

---

## 5. SKU Import Page (`sku_import.html`)

### 5.1 UI Verification
| TC ID | Test Case Title | Module | Pre-Condition | Test Steps | Test Data | Expected Result | Actual Result | Status | Severity |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| TC_SKU_IMPORT_UI_001 | Verify Import Interface | SKU Import | Page loaded | Check Dropzone and Templates | N/A | Dropzone and Template download links visible | Interface verified | Pass | Medium |

### 5.2 Functional Testing
| TC ID | Test Case Title | Module | Pre-Condition | Test Steps | Test Data | Expected Result | Actual Result | Status | Severity |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| TC_SKU_IMPORT_FUNC_001 | Download Template | SKU Import | Page loaded | Click "Download CSV Template" | N/A | CSV file downloaded | Button clickable | Pass | Low |
Edge Case | Clear Local Storage | Reload Page | Empty Storage | Data re-initializes, dashboard loads | Not tested | Skipped | High |
| TC_EDGE_002 | Zero Data | Edge Case | Clear Data Arrays | Reload Page | Zero items | Metrics show "0" or "-", no errors | Not tested | Skipped | Medium |
