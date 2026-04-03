---
name: endpoint-central-mobile-app
description: Product knowledge for the Endpoint Central Mobile App. Covers Dashboard, Devices, Patches, Software,Deploy, Remote History, Agent Uninstall OTP, Settings modules and Figma component mappings Trigger when user asks about the mobile app, its screens, navigation, widgets, device details, patch management, or references Figma component names. Also trigger for "Endpoint Central mobile App",mobile-specific UI questions. Use alongside product-knownledge skill for web vs mobile comparisons. Focus on factual product knowledge only — no UX suggestions unless asked.
---

# Endpoint Central Mobile App — Product Knowledge (Master)

This is the **master routing document** for the mobile app skill. It contains the app architecture, navigation structure, Figma component mapping, and routing instructions to detailed reference files.

**For detailed page content, read the appropriate reference file listed in the ROUTING section below.**

---

## ROUTING — Which Reference File to Read

When asked about a specific module or page, read the relevant reference file from `references/`:

| Topic | Reference File | Covers |
|-------|---------------|--------|
| Dashboard | `references/dashboard.md` |

| Devices | `references/devices.md` |
│   ├── | Device Actions & Confirmation | `device actions & confirmation.md` |

| Patches | `references/patches.md` | 

| Softwares | `references/softwares.md` | 

| Deploy | `references/deploy.md` | 

| Remote History | `references/remote history.md` | 

| Settings | `references/settings.md` | 

| Agent Uninstall OTP | `references/agent uninstall OTP.md` | 

**Always read the master file first**, then load the specific reference file for the module in question. If the question spans multiple modules, load multiple reference files.

---

## APP ARCHITECTURE OVERVIEW

The app is a native mobile client for IT administrators to monitor and manage endpoints (computers and mobile devices) from the Endpoint Central server. It provides read-access dashboards, computer & mobile device inventory view analyse and take needed action for that, patch status monitoring and deploy patching,and analyse the installed the software, configuration and deployment controls and Remote control monitoring.

---

## GLOBAL NAVIGATION

### Bottom Tab Bar
**Figma Component: `Mobile Footer`**

| Position | Label | Purpose |
|----------|------|-------|---------|
| 1 | **Dashboard** | Scrollable dashboard with summary widgets |
| 2 |  **Devices** | Device inventory list (Computers & Mobiles) |
| 3 | **Patches** | Patch list with filters |
| 4 | **Software** | Software management |
| 5 | **More** | Additional settings and options |

Active tab = **blue text** + filled icon. Persistent on all top-level screens.


### More Menu

**Figma Component: `List` (With Icon + Chevron)**

Acts as a navigation hub to secondary modules.

| Option | Destination |
|--------|------------|
| Notifications | Notifications Module |
| Software | Software Module |
| Remote History | Remote History Module |
| Agent Uninstall OTP | OTP Modal |
| Remote Control Settings | Remote Control Settings Module |
| Settings | Settings Module |


### Top Bar Behavior
**Figma Component: `Title`** (see variants below)

| Screen | Title Variant Used |
|--------|--------------------|
| Dashboard | Page title "Dashboard" left-aligned |
| Devices | **List Page Header** — "Back" link + bell icon + "Devices (count)" + Search bar |
| Patches | **List Page Header** — "Patches (count)" + Search bar |
| Detail Pages | **Detail Header** — back arrow (<) + entity name + search/info icons |
| Search Active | **Search Header** — "Cancel" link + search input |
| Bottom Sheets | **Bottom Sheet Header** — drag handle + back arrow + title |

---

## ENTITY RELATIONSHIPS

- **Dashboard widgets** aggregate data from all managed systems
- **Devices** list shows individual endpoints with status
- **Device Detail** provides per-device info across Overview, Patches, Hardware, Software, BitLocker tabs
- **Device Actions & Confirmation** as per the device details neccessary actions are intiated from here
- **Patches** list shows all applicable/supported patches across the fleet
- **Patch Detail** shows per-patch info and lists affected computers
- A single **Device** appears in both the Devices module and within Patch Detail → Computers tab
- A single **Patch** appears in both the Patches module and within Device Detail → Patches tab
- **Softwares** shows per-software info and lists installed devices
- **Remote History** shows per-remote history info and lists devices taken the remote control
- **Agent Uninstall OTP** Before removal any devices admin comes and collect the time based otp here
- **Settings** mobile app settings are be here

---

## VISUAL THEME

- **Dark mode** in live app (black/near-black backgrounds, white text)
- **Light mode** in Figma components (white/light gray cards, dark text)
- Secondary text: Gray
- Accent colors: Blue (interactive/links), Green (success), Red/Orange (warning/critical), Orange/Yellow (pending)

---

## UI PATTERNS

### Bottom Sheet Pattern
- Semi-transparent backdrop, white/light card slides up from bottom
- Header uses **Title** component (variant: **Bottom Sheet Header**)
- Tappable options with chevrons, dismissible by tapping outside

### Search Pattern
- Full-width input with magnifying glass icon
- Present on: Devices, Patches, Software tab, Patches tab, Computers tab
- Placeholder text describes scope (e.g., "Search Patches", "Search Computers")
