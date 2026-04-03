# Dashboard Module
The Dashboard is a **vertically scrolling page** containing multiple widget sections. Each section has a **section title** with a total count and a **timestamp** (format: DD/MM/YY, H:MM AM) on the right.

---

## 1. System Overview — {total_count}
**Figma Component: `List Card`**

Timestamp displayed. Contains a vertical list of status rows:

| Count | Label | Color Indicator | Tappable |
|-------|-------|-----------------|----------|
| {n} | Highly Vulnerable Systems | Gray circle, small red dot | Yes (chevron >) |
| {n} | Vulnerable Systems | Gray circle, orange dot | Yes (chevron >) |
| {n} | Healthy Systems | Gray circle, green dot | Yes (chevron >) |
| {n} | Not Available | Gray circle | Yes (chevron >) |

Each row is a card with rounded corners. The count appears inside a circular badge on the left.

---

## 2. Patch Scan — {total_count}
**Figma Component: `Swipe Card (v1)`**

Timestamp displayed. Shows **3 circular progress indicators** in a horizontal row:

| Metric | Color | Description |
|--------|-------|-------------|
| Success | Green arc | Successfully scanned systems |
| Failed | Red arc | Failed scan attempts |
| Yet To Scan | Orange/Yellow arc | Systems pending scan |

Each circle shows a large number in the center with a label below.

---

## 3. Patch Overview — {total_count}
**Figma Component: `Summary Card`**

Timestamp displayed. Contains:
- **Donut chart** (left side): Red/Green segments showing installed vs missing ratio, total count in center
- **Right side details**:
  - Missing Patches: {count} (red label, tappable with chevron >)
  - Installed Patches: {count} (green label, tappable with chevron >)

---

## 4. Inventory Scan — {total_count}
**Figma Component: `Swipe Card (v1)`**

Same layout as Patch Scan — 3 circular progress indicators:
- Success (green)
- Failed (gray)
- Yet To Scan (orange)

---

## 5. Compliance Status
**Figma Component: `List Card`**

Vertical list of status rows (same card style as System Overview):

| Count | Label | Indicator Color | Tappable |
|-------|-------|-----------------|----------|
| {n} | License In Compliance | Gray | No chevron if 0 |
| {n} | Over Licensed | Blue ring | Yes (chevron >) |
| {n} | Under Licensed | Gray | No chevron if 0 |
| {n} | Expired License | Orange ring | Yes (chevron >) |

---

## 6. Software — {total_count}
**Figma Component: `Swipe Card (v1)`**

3 circular progress indicators in horizontal row:

| Metric | Color |
|--------|-------|
| Commercial | Blue dot |
| Non Commercial | Green arc |
| Prohibited | Red arc |

Labels may truncate with "..." (e.g., "Non Comme...").

---

## 7. Agent Installation Status — {total_count}
**Figma Component: `List Card`**

Vertical list of status rows:

| Count | Label | Indicator |
|-------|-------|-----------|
| {n} | Installation Succeeded | Green ring |
| {n} | Installation Failed | Red dot |
| {n} | Yet To Install | Gray |
| {n} | Uninstallation Succeeded | Gray |
| {n} | Uninstallation Failed | Red dot |

---

## 8. Operating Systems — {total_count}
**Figma Component: `List Card`**

Vertical list of OS rows with counts. Each row shows: count badge | OS name | colored dot indicator | chevron >

Known OS types: Windows Server 2016, Mac OS X, Suse, Redhat, Windows 10, Ubuntu, Debian, Windows Server 2022

---

## 9. Warranty — {total_count}
**Figma Component: `Swipe Card (v1)`**

3 circular progress indicators:

| Metric | Color |
|--------|-------|
| In Compliance | Gray |
| Expired | Red arc |
| Unidentified | Orange arc |

---


## Dashboard Widget → Component Quick Reference

| Widget | Component |
|--------|-----------|
| System Overview | `List Card` |
| Patch Scan | `Swipe Card` |
| Patch Overview | `Summary Card` |
| Inventory Scan | `Swipe Card` |
| Compliance Status | `List Card` |
| Software | `Swipe Card` |
| Agent Installation Status | `List Card` |
| Operating Systems | `List Card` |
| Warranty | `Swipe Card` |
| Automatic Patch Deployment | `Detail page Card` |
| Vulnerability DB | `Detail page Card` |


# DEVICES MODULE

Defines the Devices title with search, segment controller (Computers / Mobiles), view swticher, device list, footer navigation screen including layout.

---

## 1. HEADER

**Component:** `Title` (List Page Header)

- Title: `Devices ({count})`
- Right Icon: Notification Bell (tappable)
- Placeholder: `Search Devices`
- Full-width below header

---

## 2. SEGMENT CONTROL

**Component:** `Segmented Control`

Options:
- Computers (default selected)
- Mobiles

**Behavior:**
- Switching updates device list
- Maintains filter state

---

## 3. FILTER DROPDOWN

**Component:** `View Switcher`

- Label: `All Systems`
- Icon: Chevron (expand/collapse)

**Behavior:**
- Opens **Device Overview Bottom Sheet**
- Acts as filter control

**States:**
| Option | Description | Tappable |
|--------|-------------|----------|
| All Systems | Shows all devices (default view) | Yes (chevron >) |
| Patch - All Systems | Filter devices by patch status | Yes (chevron >) |
| Patch - Scan Systems | Filter to systems needing patch scan | Yes (chevron >) |
| Reboot Pending Systems | Filter to systems pending reboot | Yes (chevron >) |
| Inventory - Scan Systems | Filter to systems needing inventory scan | Yes (chevron >) |

---

## 4. DEVICE LIST

**Component:** `List` (With OS Icon + Status)

---

### Device Item Structure

Each row contains:

- **Platform Icon** (left)
  - Module: Computer (Windows/macOS)
  - Module: Mobile (Android/macOS)
  - Inside rounded container

- **Status Indicator**
  - Green → Online
  - Red → Offline

- **Primary Text**
  - Device Name (bold)

- **Secondary Text**
  - Format:
    `{IP Address} | {Admiin/Technician}`

  Example:
  `168.28.0.01 | Administrator | Technician`

- **Divider**
  - Between list items

---

## 5. Must Validate

- Current page = Devices
- Do NOT highlight incorrect tab

### List Integrity
- Each row must have:
  - Unique device name
  - Correct platform icon
  - Proper secondary text
  

# DEVICE DETAILS MODULE

Accessed by tapping a device in the Devices list. Defines the Selected Device title with action icon, Device details submenu,detail page info card, footer navigation screen including layout.

## 1. HEADER

**Figma Component: `Title`** (variant: **Subpage**)
- **Back Arrow** (<) — returns to Devices list
- **Device Name** — centered or left-aligned title
- **Overflow Menu** (•••) — top-right, opens additional actions

## 2. Tab Bar (horizontal scrollable)

| Tab | Component Used | Content |
|-----|----------------|---------|
| **Overview** | `Detail page Card` (multiple sections) + |Computer details, agent details, assets, software summary, OS info, disk usage |
| **Patches** | `List` (Alert Variant) | Patch list for this device |
| **Hardware** | `Detail page Card` | Hardware specifications |
| **Software** | `List` (Text Only) | Installed software list |
| **BitLocker** (partially visible as "Bitl...") | — | BitLocker encryption status |

Active tab has a **blue underline**.


# DEVICE ACTIONS & CONFIRMATION

Defines the computer, mobile actions & Action confirmations

This skill defines:
- Action availability based on device type (Computer / Mobile)
- Action grouping and structure
- Confirmation behavior (Normal vs Critical)
- Validation rules

**Action Trigger Flow:**
- User swipes device row Taps `Actions` (or) device detail title action icon Taps `Actions`
- Opens **Bottom Sheet (Action List)** with the title name of 'Actions'
- No Back arrow pull down option only.

### A. COMPUTER ACTIONS

Action row contains:
- **Action Name** (left) (primary text)
- **Action icon** (right)

Action Confirmation bottomsheet contains:
- **Action Name** (primary text)
- **Action icon** 
- **Subtext** (Contextual sentence)
- **Confirm & Cancel Button** (primary & Secondary CTA)

**Figma Component: `Ec Action icon`,`Ec Action Confirmation icon` ** 
#### Patch
- Scan

#### Inventory
- Scan

#### Tools
- Remote Control
- Shutdown
- Restart
- Hibernate
- Log off current user
- Log off all users
- Lock

---

### B. MOBILE ACTIONS

**Figma Component: `MDM Action icons`, `MDM Action Confirmation icons` ** 
#### Inventory
- Scan Now

#### Security / Control
- Remote Lock
- Remote Alarm
- Clear Passcode
- Reset Passcode

#### Data Protection
- Corporate Wipe
- Complete Wipe

#### Device Modes
- Enable Lost Mode
- Resume Kiosk

#### Location
- Locate Device

#### System
- Restart

---

# # Patches Module

Covers the Patches list screen, Patches Overview bottom sheet, and the full Patch Detail page with both tabs.

---

## PATCHES LIST SCREEN

### Header
**Figma Component: `Title`** (variant: **List Page**)

"Patches ({total_count})" — large bold title

### Filter Dropdown
"Applicable Patches" with dropdown chevron (⟡). Tapping opens the **Patches Overview** bottom sheet.

### Patch List Items
**Figma Component: `List`** (variant: **Patch List**)

Each patch row contains:
- **Severity Icon** (left):
  - Red/Orange circle with "!" = Critical/Important severity
  - Gray circle with "?" = Unknown/unclassified severity
  - Blue circle with "−" = Informational/lower severity
- **Patch Name** (bold, may truncate with "...")
- **Metadata Row**: Installed: {n} | Failed: {n} | {Approval Status}
  - Approval Status: "Approved" or "Not Approved"
- Divider between rows

---

## PATCHES OVERVIEW BOTTOM SHEET

Triggered by tapping "Applicable Patches" dropdown. Modal bottom sheet.

**Header**: Uses **Title** component (variant: **Popup title**)

| Option | Description | Tappable |
|--------|-------------|----------|
| Applicable Patches | Patches applicable to managed systems | Yes (chevron >) |
| Supported Patches | All patches supported by the platform | Yes (chevron >) |

---

## PATCH DETAIL PAGE

Accessed by tapping a patch in the Patches list.

### Header
**Figma Component: `Title`** (variant: **Subpage**)
- **Back Arrow** (<)
- **Patch Filename** (e.g., "OptiPlex_7490_AIO_1.33.0.exe")
- **Overflow Menu** (•••)

### Tab Bar

| Tab | Component Used | Content |
|-----|----------------|---------|
| **Overview** | `Detail page Card` (multiple sections) | System details + patch metadata |
| **Computers** | `List` (With OS Icon + Status Dot) | List of affected computers |

---

### OVERVIEW TAB

#### Section: System Details
**Figma Component: `Detail page Card`**

#### Section: Patch Details
**Figma Component: `Detail page Card`**

---

### COMPUTERS TAB

**Search Bar**: "Search Computers" — full-width search input

**Figma Component: `List`** (variant: **With OS Icon + Status Dot**)

Each row shows:
- **OS Icon** (Windows logo) in rounded square
- **Status Dot** (gray = offline)
- **Computer Name** (bold)
- **IP Address** | **Severity** (e.g., "172.29.105.171 | Important")
- Divider between rows

---

## DATA FIELDS REFERENCE — PATCHES

### Patch Fields (Complete)
Patch Id, Bulletin Id, Patch Description, Vendor, Patch Type, Severity Type, Approval Status, Installed Systems, Missing Systems, Failed Systems

---

# Deploy Module

Covers the Deploy list screen and the full Deployment Detail page with Execution Summary and Configuration Details.

---

## DEPLOY LIST SCREEN

### Header
**Figma Component: `Title`** (variant: **List Page**)

"Deployments ({total_count})" — large bold title

---

### Segment Control
**Figma Component: `Segmented Controller`** 
Horizontal toggle between:
- **Created By Me**
- **Created By All**

Selected state is highlighted with a filled background.

---

### Deployment List Items
**Figma Component: `List`** (variant: **With OS Icon (no status dot)**)

Each row contains:
- **OS Icon** (left): Platform logo (e.g., Windows icon) in rounded square
- **Configuration Name** (bold, primary text)
- **Description** (secondary text, gray) — e.g., "Install Windows Patch"
- **Status** (right-aligned text):
  - Suspended → Red
  - Ready To Execute → Yellow/Orange
- Divider line between rows

---

## DEPLOYMENT DETAIL PAGE

Accessed by tapping a deployment item.

---

### Header
**Figma Component: `Title`** (variant: **Subpage**)

- Back Arrow (<)
- Configuration Name
- Overflow Menu (•••)

---

## EXECUTION SUMMARY

**Figma Component: `Swipe Card (v2)`**

Displayed below the header.

Each card contains:
- Circular progress indicator (ring)
- Count inside the circle
- Label next to the circle

---

### Possible States

| Metric | Color |
|--------|------|
| Yet To Apply | Yellow ring |
| Succeeded | Green ring |
| Retry In Progress | Blue ring |
| Failed | Red ring |
| Not Applicable | Gray ring |

---

### Layout Behavior

- Cards displayed in **2-column grid (2 per row)**
- Each card has rounded corners and light background
- Additional states wrap to next rows

---

## CONFIGURATION DETAILS

**Figma Component: `Detail page Card`**

Vertical key-value layout with divider lines.

---

## DATA FIELDS REFERENCE — DEPLOY

### Deployment Fields (Complete)

Name, Category, Type, Status, Owner, Modified Time, Platform

---

## STATUS COLOR RULES

| Status | Color |
|--------|------|
| Suspended | Red |
| Ready To Execute | Yellow/Orange |

---

## EXECUTION SUMMARY METRICS

Yet To Apply, Succeeded, Retry In Progress, Failed, Not Applicable

---

# Remote History Module

Covers Remote History list screen and Remote Session Detail bottom sheet.

---
## REMOTE HISTORY LIST SCREEN

### Header
**Figma Component: `Title`** (variant: **List Page**)

- Back Arrow (<)
- Title: "History"

---

### Section Title

"Recent remote control sessions"

Displayed below header as static text.

---

### Session List
**Figma Component: `List`** (variant: **Without icon List**)

Each row contains:

- **Computer Name** (bold, primary text)
- **Domain | Date & Time** (secondary text)
  - Example: WORKGROUP | 24 Mar 2026 at 10:13 AM
- Divider line between rows

- **Date & Time is styled as clickable (blue color)**

---

## REMOTE SESSION DETAIL

Triggered by tapping a session item.

Displayed as **Bottom Sheet**.

---

### Header
**Figma Component: `Title`** (variant: **Popup title**)

- Drag handle (top)
- Title: Computer Name

---

### Session Details
**Figma Component: `Detail page Card`**

Vertical key-value layout with divider lines.

---

## DATA FIELDS REFERENCE — REMOTE HISTORY

### Session Fields (Complete)

Computer, Logged on user(s), Start time, End time, Duration, Viewer IP, Domain, User Confirmation Status, Connection ID

---

## NAVIGATION CONTEXT

- Remote History is accessed from:
  - Bottom Tab → **More**
  - More → Remote History

---

## COMPONENT MAPPING SUMMARY

| Section | Component |
|--------|----------|
| Session List | `List` (Text Only) |
| Session Detail | `Detail page Card` |
| Bottom Sheet | `Title` (Bottom Sheet Header) |

---

# Remote History Module

Covers Software list screen, Software Overview bottom sheet, and Software Detail page with tabs.

---

## SOFTWARE LIST SCREEN

### Header
**Figma Component: `Title`** (variant: **List Page**)

"Software ({total_count})" — large bold title

---

### Filter Dropdown
"All Software" with dropdown chevron (⟡).

Tapping opens the **Software Overview** bottom sheet.

---

### Software List Items
**Figma Component: `List`** (variant: **Without icon List**)

Each row contains:

- **Software Name** (bold, primary text)
- **Version | Count** (secondary text, gray)
  - Example: `5.0 | 1`
- Divider line between rows

---

## SOFTWARE OVERVIEW BOTTOM SHEET

Triggered by tapping "All Software" dropdown.

**Header**: Uses **Title** component (variant: **Popup title**)

---

### Options

| Option | Description | Tappable |
|--------|-------------|----------|
| All Software | All discovered software | Yes (chevron >) |
| Managed License | Licensed software | Yes (chevron >) |
| Software Metering | Usage tracked software | Yes (chevron >) |
| Prohibited Software | Restricted software | Yes (chevron >) |

---

## SOFTWARE DETAIL PAGE

Accessed by tapping a software item.

---

### Header
**Figma Component: `Title`** (variant: **Subpage**)

- Back Arrow (<)
- Software Name (e.g., Cocoa-AppleScript Applet)

---

### Tab Bar

| Tab | Component Used | Content |
|-----|----------------|---------|
| Overview | `Detail page Card` | Software metadata and details |
| Devices | `List` (With OS Icon + Status Dot) | Devices where software is installed |

Active tab has a **blue underline**.

---

## OVERVIEW TAB

### Section: Software Details
**Figma Component: `Detail page Card`**

---

## DEVICES TAB

### Search Bar
"Search Computers" — full-width search input

---

### Device List
**Figma Component: `List`** (variant: **Devices List**)

Each row contains:

- **Device Icon** (left) inside rounded square
- **Status Dot**:
  - Red = Offline
  - Green = Online
- **Device Name** (bold)
- **Domain | Last Seen Time** (secondary text, gray)
  - Example: `WORKGROUP | Tue, 19 Aug 2025 19:28`
- Divider line between rows

---

## DATA FIELDS REFERENCE — SOFTWARE

### Software Fields (Complete)

Software Name, Version, Access Type, Compliance Status, Manufacturer, Type, Category, Network Installations, Managed Installations, Total Purchased, Remaining Copies

---

## NAVIGATION CONTEXT

- Software module is accessed from:
  - Bottom Tab → **More**
  - More → Software

- Software data is also referenced in:
  - Dashboard → Software widget (`Swipe Card (v1)`)
  - Device Detail → Software tab

---

## COMPONENT MAPPING SUMMARY

| Section | Component |
|--------|----------|
| Software List | `List` (Text Only) |
| Software Overview Sheet | Bottom Sheet + List |
| Software Detail | `Detail page Card` |
| Devices Tab | `List` (With OS Icon + Status Dot) |


# Agent Uninstall OTP Module

Covers Agent Uninstall OTP trigger and OTP display modal.

---

## ENTRY POINT

Accessed from:

- Bottom Tab → **More**
- More → **Agent Uninstall OTP**

---

## OTP MODAL

Triggered by tapping "Agent Uninstall OTP".

Displayed as a **center modal overlay** with dimmed background.

---

### Header

- Title: **Agent Uninstallation OTP**
- Center-aligned

---

### Description Text

"Use the following time-based OTP to uninstall Agent and Distribution Server manually."

Displayed below the title as multi-line text.

---

### OTP DISPLAY

**Figma Component: Input-like Container (Read-only)**

Contains:

- **OTP Code** (large spaced digits)
  - Example: `2 0 3 4 8 9`
- **Copy/Share Icon** (right side inside container)

---

### OTP VALIDITY

Displayed below OTP field:

- Text: "OTP is valid for"
- Countdown Timer:
  - Format: `HH:MM:SS`
  - Example: `01:59:22`
- Timer is styled in **red color**

---

### ACTION

- **Close** (primary action)
  - Center-aligned button at bottom

---

## DATA FIELDS REFERENCE — OTP

### OTP Fields

OTP Code, Expiry Time, Remaining Time

---

## NAVIGATION CONTEXT

- Module exists under **More**
- Does not have a standalone page
- Only accessible via modal trigger

---

## COMPONENT MAPPING SUMMARY

| Section | Component |
|--------|----------|
| OTP Modal | Modal Overlay |
| OTP Display | Input-style Container |
| Countdown | Text (Highlighted) |


# Settings Module

Covers Settings main page.

---

## SETTINGS PAGE

### Header
**Figma Component: `Title`** (variant: **List page**)

- Back Arrow (<)
- Title: "Settings"

---

## PROFILE SECTION

Displayed at top as a highlighted card.

**Figma Component: `Settings Page`

---

### Content

- **Profile Avatar** (left, circular)
- **User Name** (bold, primary text)
  - Example: uems-mobile+cloud+t0@zohotest.com (truncated)
- **Email ID** (secondary text, gray)

Entire card is tappable.

---

## SETTINGS OPTIONS


Each row contains:

- **Icon** (left inside rounded square)
- **Title** (primary text)
- **Chevron ( > )** (right)

---

### Options

| Option | Description |
|--------|-------------|
| Personalization | App customization settings |
| Quick tour | Guided walkthrough |
| Privacy & security | Security-related settings |
| Contact support | Support/help access |
| About us | App/company information |
| Accounts | Account management |

---

## BEHAVIOR

- Each option navigates to its respective sub-page
- Profile section may navigate to account/profile details
- List items have divider lines between rows

---

## NAVIGATION CONTEXT

- Settings is accessed from:
  - Bottom Tab → **More**
  - More → Settings

---

## COMPONENT MAPPING SUMMARY

| Section | Component |
|--------|----------|
| Profile Section | `Detail page Card` (Profile Variant) |
| Settings Options | `List` (With Icon + Chevron) |

