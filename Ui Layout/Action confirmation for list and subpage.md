# Action confirmation for list & subpage UI Structure (Text Version)

## ASCII Wireframe 

```
┌──────────────────────────────────────────────────────────┐
│        Existing List/Subpage content visible behind      │
│         confirmation layer (disabled interaction)        │
│                                                          │
│  . . . . . . .. . . DIMMED BACKGROUND . . . . . . . . .  │
│                                                          │
│──────────────────────────────────────────────────────────│
│                                                          │
│                                                          │
│          **Use, Action confirmation - Component**        │
│       **EC/MDM - Varient, check and apply varient**      │
│                                                          │
│             Action Confirmation Bottom Sheet             │
│                                                          │     
│                      Action Title                        │
│                                                          │
│                                                          │
│                         [ Icon ]                         │
│                                                          │
│                                                          │
│                    Confirmation Text                     │
│                                                          │
│                                                          │
│                                                          │
│       ┌──────────────────────────────────────────┐       │
│       │                  Primary CTA             │       │
│       └──────────────────────────────────────────┘       │
│                                                          │
│                        (Text CTA)                        │
│                                                          │
│                                                          │
│                                                          │
└──────────────────────────────────────────────────────────┘
```

## Visual Hierarchy

Screen
 ├── Base Screen (List / Subpage content)
 │     ├── Title + Search + Device List (existing)
 │     └── Base content is dimmed when modal opens
 │
 ├── Action Confirmation Layer
 │     ├── Modal Overlay (background dim)
 │     └── Bottom Sheet Container
 │
 └── Bottom Sheet Content
       ├── Action Title
       ├── Action Icon
       ├── Confirmation Message
       │     └── Device Name highlighted in message
       ├── Primary Button
       └── Secondary Action

## Behaviour Notes

- Triggered from device-level action (list/subpage).
- Appears as a bottom sheet over the current page.
- User can:
  - Confirm action with primary CTA
  - Dismiss with secondary action 
- Background content remains visible but non-interactive while sheet is open.
