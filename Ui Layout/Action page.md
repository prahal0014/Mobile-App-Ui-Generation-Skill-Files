# Action Page UI Structure (Text Version)

## ASCII Wireframe

```
┌──────────────────────────────────────────────────────────┐
│ Existing Device list/detail page content visible behind  │
│          action layer (disabled interaction)             │
│                                                          │
│  . . . . . . . . .  DIMMED BACKGROUND . . . . . . . . .  │
│                                                          │
│──────────────────────────────────────────────────────────│
│                                                          │
│          **Use, list Action - Component**                │
│      **EC/MDM - Varient, check and apply varient**       │
│                                                          │
│             Action Bottom Sheet (Full Width)             │
│          (Top corners rounded + drag handle)             │
│                                                          │
│                        Actions                           │
│                                                          │
│   GROUP NAME                                             │
│   ┌──────────────────────────────────────────────────┐   │
│   │ label                                    [Icon]  │   │
│   └──────────────────────────────────────────────────┘   │
│                                                          │
│   GROUP NAME                                             │
│   ┌──────────────────────────────────────────────────┐   │
│   │ label                                    [Icon]  │   │
│   └──────────────────────────────────────────────────┘   │
│                                                          │
│   GROUP NAME                                             │
│   ┌──────────────────────────────────────────────────┐   │
│   │ label                                    [Icon]  │   │
│   ├──────────────────────────────────────────────────┤   │
│   │ label                                    [Icon]  │   │
│   ├──────────────────────────────────────────────────┤   │
│   │ label                                    [Icon]  │   │
│   ├──────────────────────────────────────────────────┤   │
│   │ label                                    [Icon]  │   │
│   ├──────────────────────────────────────────────────┤   │
│   │ label                                    [Icon]  │   │
│   ├──────────────────────────────────────────────────┤   │
│   │ label                                    [Icon]  │   │
│   ├──────────────────────────────────────────────────┤   │
│   │ label                                    [Icon]  │   │
│   └──────────────────────────────────────────────────┘   │
│                                                          │
└──────────────────────────────────────────────────────────┘
```

## Visual Hierarchy

Screen
 ├── Base Screen (Devices page)
 │     ├── Title visible in background
 │     └── Base content dimmed when action sheet opens
 │
 ├── Action Layer
 │     ├── Modal Overlay (background dim)
 │     └── Bottom Sheet Container
 │
 └── Bottom Sheet Content
       ├── Drag Handle
       ├── Sheet Title: Actions
       ├── Section Group: GROUP NAME
            └── Action Item: Label

## Behaviour Notes

- Triggered from device row swipe action (`Actions`) or device subpage title action entry point.
- Opens as a bottom sheet over the current devices screen.
- Background remains visible but non-interactive while sheet is open.
- Action items are grouped by category (PATCH, INVENTORY, TOOLS).
- Tapping an item triggers the corresponding workflow (immediate action or confirmation flow).
- Sheet can be dismissed by swipe-down gesture or tapping outside.
