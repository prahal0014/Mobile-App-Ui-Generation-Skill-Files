# Remote History Details UI Structure (Text Version)

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
│   **Use, Detail Page Card - Component**                 │
│   **EC/MDM - Varient, check and apply varient**         │
│                                                          │
│   [Scrollable Detail Content]                            │
│   ┌──────────────────────────────────────────────────┐   │
│   │                  DEVICE NAME                     │   │
│   ├──────────────────────────────────────────────────┤   │
│   │ Computer              | DESKTOP-EHS8Q7F          │   │
│   ├──────────────────────────────────────────────────┤   │
│   │ Logged on user(s)     | user@domain...           │   │
│   ├──────────────────────────────────────────────────┤   │
│   │ Start time            | 24 Mar 2026, 10:13 AM    │   │
│   ├──────────────────────────────────────────────────┤   │
│   │ End time              | 24 Mar 2026, 10:16 AM    │   │
│   ├──────────────────────────────────────────────────┤   │
│   │ Duration              | 2 Days                   │   │
│   ├──────────────────────────────────────────────────┤   │
│   │ Viewer IP             | 157.51.149.208           │   │
│   ├──────────────────────────────────────────────────┤   │
│   │ Domain                | WORKGROUP                │   │
│   ├──────────────────────────────────────────────────┤   │
│   │ User Confirmation     | Disabled                 │   │
│   │ Status                |                          │   │
│   ├──────────────────────────────────────────────────┤   │
│   │ Connection ID         | 257093889                │   │
│   └──────────────────────────────────────────────────┘   │
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
 ├── Detail Content Region (Scrollable)
 │     ├── Use, Detail Page Card - Component
 │     ├── EC/MDM - Varient, check and apply varient
 │     └── Section Card: Session Details (key-value rows)
 │
 └── No Footer Nav in Subpage

## Behaviour Notes

- Header remains visible while detail card content scrolls.
- Detail card shows complete remote session metadata for selected history entry.
- Row labels remain left aligned and values right aligned for scan readability.
- Long values (for example user identity) can wrap into multiple lines.
- This is a subpage flow and does not use bottom footer navigation.
