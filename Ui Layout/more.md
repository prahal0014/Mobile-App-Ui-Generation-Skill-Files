# More Page UI Structure (Text Version)

## ASCII Wireframe

```
┌──────────────────────────────────────────────────────────┐
│                                                          │
│                                                          │
│                  **Title - Component**                   │
│                    (Example: More)                      │
│                                                          │
│──────────────────────────────────────────────────────────│
│                      *12px*                              │
│   **Use, list Action - Component**                       │
│   **EC/MDM - Varient, check and apply varient**          │
│                                                          │
│   ┌──────────────────────────────────────────────────┐   │
│   │ [Icon] Notifications                        >    │   │
│   ├──────────────────────────────────────────────────┤   │
│   │ [Icon] Software                             v    │   │
│   ├──────────────────────────────────────────────────┤   │
│   │ [Icon] Remote History                        >    │   │
│   ├──────────────────────────────────────────────────┤   │
│   │ [Icon] Agent Uninstall OTP                   >    │   │
│   ├──────────────────────────────────────────────────┤   │
│   │ [Icon] Remote Control Settings               >    │   │
│   ├──────────────────────────────────────────────────┤   │
│   │ [Icon] Settings                              >    │   │
│   └──────────────────────────────────────────────────┘   │
│                                                          │
│──────────────────────────────────────────────────────────│
│                                                          │
│                Footer Nav - Component                    │
│                   (More tab selected)                   │
│                                                          │
└──────────────────────────────────────────────────────────┘
```

## Visual Hierarchy

Screen
 ├── Header Region
 │     └── Title - Component (More)
 │
 ├── More Menu Region (Scrollable)
 │     ├── Use, list Action - Component
 │     ├── EC/MDM - Varient, check and apply varient
 │     └── Menu rows (icon + label + trailing indicator)
 │
 └── Footer Nav - Component (Fixed)

## Behaviour Notes

- Menu list is vertically scrollable when options exceed screen height.
- Each row contains:
  - Leading icon
  - Feature label
  - Trailing affordance (`>` for navigation, `v` for expanded state)
- Tapping a navigational row opens corresponding subpage flow.
- Rows with expand indicator toggle nested options/section state.
- Footer navigation remains fixed while list scrolls, with `More` active.
