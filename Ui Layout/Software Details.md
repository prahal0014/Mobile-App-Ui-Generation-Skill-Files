# Software Details UI Structure (Text Version)

## ASCII Wireframe

```
┌──────────────────────────────────────────────────────────┐
│                                                          │
│                                                          │
│         **Title - Component, Subpage - Varient**         │
│               (Back Icon + Software Name)               │
│                                                          │
│──────────────────────────────────────────────────────────│
│                      *8px*                               │
│    **Segment Controller - Component**                    │
│    ┌────────────────────────────────────────────────┐    │
│    │ Overview (selected) | Devices                  │    │
│    └────────────────────────────────────────────────┘    │
│                      *12px*                              │
│   **Use, Detail Page Card - Component**                 │
│   **EC/MDM - Varient, check and apply varient**         │
│                                                          │
│   [Scrollable Detail Content]                            │
│                                                          │
│   Software Details                                       │
│   ┌──────────────────────────────────────────────────┐   │
│   │ Software Name         | Cocoa-AppleScript Applet │   │
│   ├──────────────────────────────────────────────────┤   │
│   │ Access Type           | Not Assigned             │   │
│   ├──────────────────────────────────────────────────┤   │
│   │ Compliance Status     | -                        │   │
│   ├──────────────────────────────────────────────────┤   │
│   │ Version               | 1.0                      │   │
│   ├──────────────────────────────────────────────────┤   │
│   │ Manufacturer          | Unknown                  │   │
│   ├──────────────────────────────────────────────────┤   │
│   │ Type                  | Unidentified             │   │
│   ├──────────────────────────────────────────────────┤   │
│   │ Category              | --                       │   │
│   ├──────────────────────────────────────────────────┤   │
│   │ Network Installations | 1                        │   │
│   ├──────────────────────────────────────────────────┤   │
│   │ Managed Installations | 1                        │   │
│   ├──────────────────────────────────────────────────┤   │
│   │ Total Purchased       | --                       │   │
│   ├──────────────────────────────────────────────────┤   │
│   │ Remaining Copies      | --                       │   │
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
 ├── Subpage Header Region
 │     ├── Title - Component, Subpage - Varient
 │     └── Back Navigation Icon
 │
 ├── Top Tab Region
 │     ├── Segment Controller - Component
 │     └── Tabs: Overview, Devices
 │
 ├── Detail Content Region (Scrollable)
 │     ├── Use, Detail Page Card - Component
 │     ├── EC/MDM - Varient, check and apply varient
 │     └── Section Card: Software Details (key-value rows)
 │
 └── Footer Nav - Component (Fixed)

## Behaviour Notes

- Header and tab region remain visible while details scroll.
- `Overview` tab shows software metadata and installation/license counts.
- `Devices` tab shows device-level listing for this software.
- Row labels remain left aligned and values right aligned for scan readability.
- Footer navigation remains visible on this details page with `More` active.
