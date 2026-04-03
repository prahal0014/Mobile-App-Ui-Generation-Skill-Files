# Software List UI Structure (Text Version)

## ASCII Wireframe

```
┌──────────────────────────────────────────────────────────┐
│                                                          │
│                                                          │
│      **Title - Component, Subpage - Varient**           │
│                  (Back: More)                            │
│                                                          │
│                  **Title - Component**                   │
│                (Example: Software (418))                │
│                                                          │
│──────────────────────────────────────────────────────────│
│                      *8px*                               │
│   **Controller - Component**                             │
│   ┌──────────────────────────────────────────────────┐   │
│   │ Search                                            │   │
│   └──────────────────────────────────────────────────┘   │
│                      *12px*                              │
│    **View Switcher - Component**                         │
│    ┌──────────────────────────────────────────────┐      │
│    │     (Example: All Software)                  │      │
│    └──────────────────────────────────────────────┘      │
│                      *12px*                              │
│   **Use, list Action - Component**                       │
│   **EC/MDM - Varient, check and apply varient**          │
│                                                          │
│   ┌──────────────────────────────────────────────────┐   │
│   │ Software Name                                    │   │
│   │ Version | Count                                  │   │
│   ├──────────────────────────────────────────────────┤   │
│   │ Software Name                                    │   │
│   │ Version | Count                                  │   │
│   ├──────────────────────────────────────────────────┤   │
│   │ Software Name                                    │   │
│   │ Version | Count                                  │   │
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
 │     ├── Title - Component (Software count)
 │     ├── Controller - Component (Search)
 │     └── View Switcher - Component (All Software)
 │
 ├── Software List Region (Scrollable)
 │     ├── Use, list Action - Component
 │     ├── EC/MDM - Varient, check and apply varient
 │     └── Software rows (name + version/count metadata)
 │
 └── Footer Nav - Component (Fixed)

## Behaviour Notes

- List is vertically scrollable and supports long software datasets.
- Search filters software records by software name.
- View switcher (`All Software`) controls software scope/filter.
- Each row displays software title and secondary metadata:
  - Version
  - Count
- Tapping a row opens software details/subpage flow.
- Footer navigation remains fixed while list scrolls, with `More` active.
