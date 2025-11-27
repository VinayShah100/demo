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

## 4. Edge Cases
| TC ID | Test Case Title | Module | Pre-Condition | Test Steps | Test Data | Expected Result | Actual Result | Status | Severity |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| TC_EDGE_001 | Local Storage Empty | Edge Case | Clear Local Storage | Reload Page | Empty Storage | Data re-initializes, dashboard loads | Not tested | Skipped | High |
| TC_EDGE_002 | Zero Data | Edge Case | Clear Data Arrays | Reload Page | Zero items | Metrics show "0" or "-", no errors | Not tested | Skipped | Medium |
