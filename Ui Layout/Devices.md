# Devices List UI Structure (Text Version)

## ASCII Wireframe 

```
┌──────────────────────────────────────────────────────────┐
│                                                          │
│                                                          │
│                  **Title - Component**                   │
│                                                          │
│──────────────────────────────────────────────────────────│
│                      *8px*                               │
│   **Segment Controller - Component**                     │
│   ┌──────────────────────────────────────────────────┐   │
│   │  Computers (selected) | Mobiles                  │   │
│   └──────────────────────────────────────────────────┘   │
│                      *12px*                              │
│    **View Switcher - Component**                         │
│    ┌──────────────────────────────────────────────┐      │
│    │     (Example: Title)                         │      │
│    └──────────────────────────────────────────────┘      │
│                      *12px*                              │
│   **Use, list - Component**                              │      
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
│   ├──────────────────────────────────────────────────┤   │
│   │ [Icon]  Title                                    │   │
│   │ Subtext 1 | Subtext 2 | Subtext 3                │   │
│   ├──────────────────────────────────────────────────┤   │
│   │ [Icon]  Title                                    │   │
│   │ Subtext 1 | Subtext 2 | Subtext 3                │   │
│───└──────────────────────────────────────────────────┘───│
│                                                          │
│                Footer Nav - Component                    │
│                  (Devices tab selected)                  │
│                                                          │
└──────────────────────────────────────────────────────────┘
```

## Visual Hierarchy

Screen
 ├── Header Region
 │     ├── Title - Component
 │     ├── Segment Controller - Component (Computers / Mobiles)
 │     ├── View Switcher - Component
 │    
 │
 ├── Device List Region (Scrollable)
 │     ├── Use, list - Component
 │     └── Device rows (icon + title + status metadata)
 │
 └── Footer Nav - Component (Fixed)

## Layout Rules
- Title: Top Alignment

- Content wrapper: Middle Alignment (FILL, paddingLeft=16, paddingRight=16, background=#FFFFFF,)
  - Segment Controller (layoutAlign=CENTER, layoutSizingHorizontal=HUG, auto-layout)
  - View Switcher (layoutAlign=MIN, layoutSizingHorizontal=HUG, auto-layout)
  - List items (layoutSizingHorizontal=HUG, auto-layout)

- Footer Nav: Bottom Alignment

## Behaviour Notes

- List is vertically scrollable and supports long device content.
- Each row shows device title and supporting subtext metadata.
- Row tap opens corresponding subpage/details flow.
- Footer navigation remains fixed while list scrolls.
