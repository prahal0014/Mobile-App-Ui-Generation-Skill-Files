# Patches List UI Structure (Text Version)

## ASCII Wireframe

```
┌──────────────────────────────────────────────────────────┐
│                                                          │
│                                                          │
│                  **Title - Component**                   │
│                                                          │
│──────────────────────────────────────────────────────────│
│    **View Switcher - Component**                         │
│    ┌──────────────────────────────────────────────┐      │
│    │     (Example: Title)                         │      │
│    └──────────────────────────────────────────────┘      │
│                      *12px*                              │
│                                                          │
│   **Use, list Action - Component**                       │ 
│   ┌──────────────────────────────────────────────────┐   │
│   │ [Icon]  Title                                    │   │
│   │ Subtext 1 | Subtext 2 | Subtext 3                │   │
│   ├──────────────────────────────────────────────────┤   │
│   │ [Icon]  Title                                    │   │
│   │ Subtext 1 | Subtext 2 | Subtext 3                │   │
│   ├──────────────────────────────────────────────────┤   │
│   │ [Icon]  Title                                    │   │
│   │ Subtext 1 | Subtext 2 | Subtext 3                │   │
│   ├──────────────────────────────────────────────────┤   │
│   │ [Icon]  Title                                    │   │
│   │ Subtext 1 | Subtext 2 | Subtext 3                │   │
│   └──────────────────────────────────────────────────┘   │
│                                                          │
│──────────────────────────────────────────────────────────│
│                                                          │
│                Footer Nav - Component                    │
│                                                          │
└──────────────────────────────────────────────────────────┘
```

## Visual Hierarchy

Screen
 ├── Header Region
 │     ├── Title - Component 
 │     └── view switcher - Component 
 │
 ├── Patches List Region (Scrollable)
 │     ├── Use, list Action - Component
 │     └── Patch rows (icon + title + status metadata)
 │
 └── Footer Nav - Component (Fixed)

## Behaviour Notes

- List is vertically scrollable and supports long patch datasets.
- Search filters patch entries by patch name/identifier.
- Each row shows patch title and secondary status metadata:
  - Installed count
  - Failed count
  - Approval state
- Tapping a row opens patch details/subpage flow.
- Footer navigation remains fixed while list scrolls.
