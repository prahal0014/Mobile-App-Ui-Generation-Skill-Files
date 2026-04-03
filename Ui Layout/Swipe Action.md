# Swipe Action UI Structure (Text Version)

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
|                       *12px*                             │
│    **View Switcher - Component**                         │
│    ┌──────────────────────────────────────────────┐      │                        
│    │     (Example: All Systems)                   │      │
│    └──────────────────────────────────────────────┘      │
│                      *12px*                              │
│   **Use, Swipe Action - Component**                      │
│   **EC/MDM - Varient, check and apply varient**          │       
│                                                          │
│ **List Name partially shifted to left, list bottom line  │
│ only connected upto action bg**                          │
│                               ┌────────────┬─────────────│
│tle                            │  Action 1  │  Action 2   │
│Subtext 2 | Subtext 3          │  blue bg   │   gray bg   │
│───────────────────────────────┴────────────┴─────────────│   
│                                                          │
│   **Use, list Action - Component**                       │
│   ┌──────────────────────────────────────────────────┐   │
│   │ Title                                            │   │
│   │ Subtext 1 | Subtext 2 | Subtext 3                │   │
│   ├──────────────────────────────────────────────────┤   │
│   │ Title                                            │   │
│   │ Subtext 1 | Subtext 2 | Subtext 3                │   │
│   ├──────────────────────────────────────────────────┤   │
│   │ Title                                            │   │
│   │ Subtext 1 | Subtext 2 | Subtext 3                │   │
│   ├──────────────────────────────────────────────────┤   │
│   │ Title                                            │   │
│   │ Subtext 1 | Subtext 2 | Subtext 3                │   │
│   ├──────────────────────────────────────────────────┤   │
│   │ Title                                            │   │
│   │ Subtext 1 | Subtext 2 | Subtext 3                │   │
│   ├──────────────────────────────────────────────────┤   │
│   │ Title                                            │   │
│   │ Subtext 1 | Subtext 2 | Subtext 3                │   │
│───└──────────────────────────────────────────────────┘───│
│                                                          │
│                Footer Nav - Component                    │
│                                                          │
└──────────────────────────────────────────────────────────┘
```

## Visual Hierarchy

Screen
 ├── Header Region
 │     ├── Title - Component
 │     ├── Segment Controller - Component (Computers / Mobiles)
 │     ├── View Switcher - Component 
 │         └── Filter Label: All Systems
 │
 ├── Device List Region (Scrollable)
 │     ├── Use, Swipe Action - Component
 │     ├── EC/MDM - Varient, check and apply varient
 │     ├── Active Swiped Row
 │     │     ├── Row content shifted left
 │     │     ├── Quick Action 1: (primary)
 │     │     └── Quick Action 2: (secondary)
 │     └── Remaining rows in default state
 │
 └── Footer Nav - Component (Fixed)

## Behaviour Notes

- Swipe gesture is applied per row (left reveal).
- Only one row should remain expanded at a time.
- Tapping `Action 1` triggers immediate quick action.
- Tapping `Action 2` opens the action list page flow.
- Tapping outside or scrolling collapses the revealed action panel.
- List remains vertically scrollable while non-active rows stay in normal state.

## Layout Rules

- Content wrapper: paddingLeft = 16, paddingRight = 16
- Segment Controller: layoutAlign = CENTER, layoutSizingHorizontal = HUG
- View Switcher: layoutAlign = MIN (left-aligned), layoutSizingHorizontal = HUG
- List items: layoutSizingHorizontal = HUG
- Footer Nav: layoutSizingHorizontal = FILL (pinned to bottom)

## Swipe Action Spec (Condensed)

- Frame: `393x852`.
- Active swiped row: container `393x79`, `layoutMode = NONE`, `clipsContent = true`.
- Right action panel (`Swipe Action`): width `186`, x-position `207`, y `0` (fixed).
- Left content (`List` → `Devices` variant): y `7`, x `-96` for default partial-open, x `-186` for fully open.
- Composition rule: keep action panel fixed on the right; only left list content shifts.
- Divider rule: bottom divider appears only under left content, not under action panel.
- Row content rule: first visible row is swiped (partial-open default), remaining rows are normal; use meaningful varied text (no placeholders).
- Validation: `y==0` for swiped content, action panel right-aligned/visible, partial-open uses `x=-96`, footer active tab = `Devices`, no extra top gap, segmented control remains a true component instance.
