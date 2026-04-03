# Device Details UI Structure (Text Version)

## ASCII Wireframe 

```
┌──────────────────────────────────────────────────────────┐
│                                                          │
│                                                          │
│         **Title - Component, Subpage - Varient**         │
│                                                          │
│──────────────────────────────────────────────────────────│
│                      *12px*                              │
│   **Use, Detail Page Card - Component**                  │ 
│   **Use, Detail Page bg color-#F2F2F5**                  │                                       
│   [Scrollable Detail Content]                            │ 
│                                                          │
│   **title - Fontstyle Semibold**                         │
│   ┌──────────────────────────────────────────────────┐   │
│   │ Lable                 | Key                      │   │
│   │ Lable                 | Key                      │   │
│   │ Lable                 | Key                      │   │
│   │ Lable                 | Key                      │   │
│   │ Lable                 | Key                      │   │
│   └──────────────────────────────────────────────────┘   │
│   **title - Fontstyle Semibold**                         │
│   ┌──────────────────────────────────────────────────┐   │
│   │ Lable                 | Key                      │   │
│   │ Lable                 | Key                      │   │
│   │ Lable                 | Key                      │   │
│   │ Lable                 | Key                      │   │
│   │ Lable                 | Key                      │   │
│   └──────────────────────────────────────────────────┘   │
│   **title - Fontstyle Semibold**                         │
│   ┌──────────────────────────────────────────────────┐   │
│   │ Lable                 | Key                      │   │
│   │ Lable                 | Key                      │   │
│   │ Lable                 | Key                      │   │
│   │ Lable                 | Key                      │   │
│   │ Lable                 | Key                      │   │
│   └──────────────────────────────────────────────────┘   │
└──────────────────────────────────────────────────────────┘
```

## Visual Hierarchy

Screen
 ├── Subpage Header Region
 │     ├── Title - Component, Subpage - Varient
 │     ├── Back Navigation Icon
 │     └── More Action Icon
 │
 ├── Top Tab Region
 │     └──  Tabs: Tab 1, Tab 2, Tab 3, Tab 4, Tab 5
 │     
 ├── Detail Content Region (Scrollable)
 │     ├── Use, Detail Page Card - Component
 │     ├── Use, Detail Page bg color - **#F2F2F5**
 │     └── Section Card 
 │
 └── No Footer Nav in Subpage

## Behaviour Notes

- Header and top tabs remain visible while detail content scrolls.
- Row labels remain left aligned and values right aligned for scan readability.
- Subpage does not use the bottom footer navigation component.
