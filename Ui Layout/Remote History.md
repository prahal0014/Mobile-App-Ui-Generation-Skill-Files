# Remote History UI Structure (Text Version)

## ASCII Wireframe

```
┌──────────────────────────────────────────────────────────┐
│                                                          │
│                                                          │
│      **Title - Component, Subpage - Varient**           │
│                  (Back: More)                            │
│                                                          │
│                  **Title - Component**                   │
│                    (Example: History)                   │
│                                                          │
│   Subtitle: Recent remote control sessions              │
│                                                          │
│──────────────────────────────────────────────────────────│
│                      *12px*                              │
│   **Use, list Action - Component**                       │
│   **EC/MDM - Varient, check and apply varient**          │
│                                                          │
│   ┌──────────────────────────────────────────────────┐   │
│   │ Device Name                                      │   │
│   │ Workgroup | Session Date & Time                  │   │
│   ├──────────────────────────────────────────────────┤   │
│   │ Device Name                                      │   │
│   │ Workgroup | Session Date & Time                  │   │
│   ├──────────────────────────────────────────────────┤   │
│   │ Device Name                                      │   │
│   │ Workgroup | Session Date & Time                  │   │
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
 │     ├── Title - Component, Subpage - Varient (Back: More)
 │     ├── Title - Component (History)
 │     └── Supporting Label: Recent remote control sessions
 │
 ├── History List Region (Scrollable)
 │     ├── Use, list Action - Component
 │     ├── EC/MDM - Varient, check and apply varient
 │     └── Session rows (device name + workgroup + session timestamp)
 │
 └── Footer Nav - Component (Fixed)

## Behaviour Notes

- List is vertically scrollable and supports long remote session history.
- Each row shows:
  - Device name
  - Workgroup/domain label
  - Session date-time metadata
- Session timestamp is visually emphasized as actionable metadata.
- Tapping a row opens corresponding remote session details/log view.
- Footer navigation remains fixed while list scrolls, with `More` active.
