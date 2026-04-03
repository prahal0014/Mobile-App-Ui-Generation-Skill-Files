# Deploy List UI Structure (Text Version)

## ASCII Wireframe

```
┌──────────────────────────────────────────────────────────┐
│                                                          │
│                                                          │
│                  **Title - Component**                   │
│                                                          │
│                                                          │
│──────────────────────────────────────────────────────────│      
│                      *12px*                              │
│   **Segment Controller - Component**                     │
│   ┌──────────────────────────────────────────────────┐   │
│   │ Created By Me (selected) | Created By All        │   │
│   └──────────────────────────────────────────────────┘   │
│                      *12px*                              │
│   **Use, list - Component**                              │
│   ┌──────────────────────────────────────────────────┐   │
│   │ [Icon]  Deployment Title                         │   │
│   │         Deployment Description    (status)       │   │
│   ├──────────────────────────────────────────────────┤   │
│   │ [Icon]  Deployment Title                         │   │
│   │         Deployment Description    (status)       │   │
│   ├──────────────────────────────────────────────────┤   │
│   │ [Icon]  Deployment Title                         │   │
│   │         Deployment Description    (status)       │   │
│   ├──────────────────────────────────────────────────┤   │
│   │ [Icon]  Deployment Title                         │   │
│   │         Deployment Description    (status)       │   │
│   ├──────────────────────────────────────────────────┤   │
│   │ [Icon]  Deployment Title                         │   │
│   │         Deployment Description    (status)       │   │
│   ├──────────────────────────────────────────────────┤   │
│   │ [Icon]  Deployment Title                         │   │
│   │         Deployment Description    (status)       │   │
│   ├──────────────────────────────────────────────────┤   │
│   │ [Icon]  Deployment Title                         │   │
│   │         Deployment Description    (status)       │   │
│───└──────────────────────────────────────────────────┘───│
│                                                          │
│                Footer Nav - Component                    │
│                  (Deploy tab selected)                   │
│                                                          │
└──────────────────────────────────────────────────────────┘
```

## Visual Hierarchy

Screen
 ├── Header Region
 │     ├── Title - Component
 │     └── Segment Controller - Component (Created By Me / Created By All)
 │
 ├── Deployment List Region (Scrollable)
 │     ├── Use, list - Component
 │     └── Deployment rows (icon + title + description + status)
 │
 └── Footer Nav - Component (Fixed)

## Behaviour Notes

- List is vertically scrollable and supports long deployment datasets.
- Segment controller filters ownership scope:
  - `Created By Me`
  - `Created By All`
- Each row displays execution status as text with semantic color:
  - `Suspended` (alert color)
  - `Ready To Execute` (warning color)
- Tapping a row opens deployment details/subpage flow.
- Footer navigation remains fixed while list scrolls.
