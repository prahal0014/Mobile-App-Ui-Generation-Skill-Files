# Deploy Detail UI Structure (Text Version)

## ASCII Wireframe

```
┌──────────────────────────────────────────────────────────┐
│                                                          │
│                                                          │
│         **Title - Component, Subpage - Varient**         │
│             (Back Icon + Deployment Name)                │
│                                                          │
│──────────────────────────────────────────────────────────│
│                      *12px*                              │
│   **Use, Detail Page Card - Component**                  │
│   **EC/MDM - Varient, check and apply varient**          │
│                                                          │
│   [Scrollable Detail Content]                            │
│                                                          │
│   Execution Summary                                      │
│   ┌───────────────────────┐  ┌───────────────────────┐  │
│   │ [Count Badge]         │  │ [Count Badge]         │  │
│   │ Yet To Apply          │  │ Succeeded             │  │
│   └───────────────────────┘  └───────────────────────┘  │
│                                                          │
│   Configuration Details                                  │
│   ┌──────────────────────────────────────────────────┐   │
│   │ Name                 | My Configuration           │   │
│   ├──────────────────────────────────────────────────┤   │
│   │ Category             | User                       │   │
│   ├──────────────────────────────────────────────────┤   │
│   │ Type                 | Install Windows Patch      │   │
│   ├──────────────────────────────────────────────────┤   │
│   │ Status               | Ready To Execute           │   │
│   ├──────────────────────────────────────────────────┤   │
│   │ Owner                | UEM Mobile                 │   │
│   ├──────────────────────────────────────────────────┤   │
│   │ Modified Time        | 5 Mar 2026, 9:54 AM        │   │
│   ├──────────────────────────────────────────────────┤   │
│   │ Platform             | Windows                    │   │
│   └──────────────────────────────────────────────────┘   │
│                                                          │
│──────────────────────────────────────────────────────────│
│                                                          │
│                Footer Nav - Component                    │
│                  (Deploy tab selected)                  │
│                                                          │
└──────────────────────────────────────────────────────────┘
```

## Visual Hierarchy

Screen
 ├── Subpage Header Region
 │     ├── Title - Component, Subpage - Varient
 │     └── Back Navigation Icon
 │
 ├── Detail Content Region (Scrollable)
 │     ├── Use, Detail Page Card - Component
 │     ├── EC/MDM - Varient, check and apply varient
 │     ├── Summary Section: Execution Summary
 │     │     ├── Metric Card: Yet To Apply
 │     │     └── Metric Card: Succeeded
 │     └── Section Card: Configuration Details (key-value rows)
 │
 └── Footer Nav - Component (Fixed)

## Behaviour Notes

- Header stays fixed while content scrolls.
- Execution summary cards show quick counters for deployment progress states.
- Configuration details are shown in key-value rows for scan readability.
- Values are right aligned; labels are left aligned.
- Footer navigation remains visible on this detail page with `Deploy` active.
