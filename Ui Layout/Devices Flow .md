# Device List Flow UI Structure (Text Version)

## Flow Summary

1. Device List Page
2. Swipe Action Page
3. Action Confirmation Page
4. Device Details Page (Overview only)

---

## 1) Device List Page

### ASCII Wireframe

```
┌──────────────────────────────────────────────────────────┐
│                                                          │
│                                                          │
│                  **Title - Component**                   │
│                                                          │
│──────────────────────────────────────────────────────────│
│                      *8px*                               │
│  **Segment Controller - Component, Separate Autolayout** │
│   ┌──────────────────────────────────────────────────┐   │
│   │  Computers (selected) | Mobiles                  │   │
│   └──────────────────────────────────────────────────┘   │
│                      *12px*                              │
│    **View Switcher - Component, Separate Autolayout**    │
│    ┌──────────────────────────────────────────────┐      │
│    │     (Example: Title)                         │      │
│    └──────────────────────────────────────────────┘      │
│                      *12px*                              │
│   **Use, list - Component, Separate Autolayout**         │      
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
│                (Devices tab selected)                    │
│                                                          │
└──────────────────────────────────────────────────────────┘
```

## Layout Rules
- Title: Top Alignment

- Content wrapper: Middle Alignment (FILL, paddingLeft=16, paddingRight=16, background=#FFFFFF,)
  - Segment Controller (layoutAlign=CENTER, layoutSizingHorizontal=HUG, Separate auto-layout)
  - View Switcher (layoutAlign=MIN, layoutSizingHorizontal=HUG, Separate auto-layout)
  - List items (layoutSizingHorizontal=HUG, Separate auto-layout)

- Footer Nav: Bottom Alignment

---

## 2) Swipe Action Page

### ASCII Wireframe

```
┌──────────────────────────────────────────────────────────┐
│                                                          │
│                                                          │
│                  **Title - Component**                   │
│                                                          │
│──────────────────────────────────────────────────────────│
│                      *8px*                               │
│  **Segment Controller - Component, Separate Autolayout** │
│   ┌──────────────────────────────────────────────────┐   │
│   │  Computers (selected) | Mobiles                  │   │
│   └──────────────────────────────────────────────────┘   │
|                       *12px*                             │
│    **View Switcher - Component, Separate Autolayout**    │
│    ┌──────────────────────────────────────────────┐      │                        
│    │     (Example: All Systems)                   │      │
│    └──────────────────────────────────────────────┘      │
│                      *12px*                              │
│   **Use, Swipe Action - Component, Separate Autolayout** │
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
│                (Devices tab selected)                    │
│                                                          │
└──────────────────────────────────────────────────────────┘
```
## Layout Rules
- Title: Top Alignment

- Content wrapper: Middle Alignment (FILL, paddingLeft=16, paddingRight=16, background=#FFFFFF,)
  - Segment Controller (layoutAlign=CENTER, layoutSizingHorizontal=HUG, Separate auto-layout)
  - View Switcher (layoutAlign=MIN, layoutSizingHorizontal=HUG, Separate auto-layout)
  - List items (layoutSizingHorizontal=HUG, Separate auto-layout)

- Footer Nav: Bottom Alignment

## Swipe Action Spec (Condensed)

- Frame: `393x852`.
- Active swiped row: container `393x79`, `layoutMode = NONE`, `clipsContent = true`.
- Right action panel (`Swipe Action`): width `186`, x-position `207`, y `0` (fixed).
- Left content (`List` → `Devices` variant): y `7`, x `-96` for default partial-open, x `-186` for fully open.
- Composition rule: keep action panel fixed on the right; only left list content shifts.
- Divider rule: bottom divider appears only under left content, not under action panel.
- Row content rule: first visible row is swiped (partial-open default), remaining rows are normal; use meaningful varied text (no placeholders).
- Validation: `y==0` for swiped content, action panel right-aligned/visible, partial-open uses `x=-96`, footer active tab = `Devices`, no extra top gap, segmented control remains a true component instance.

---

## 3) Action Confirmation Page

### ASCII Wireframe

```
┌──────────────────────────────────────────────────────────┐
│        Existing List/Subpage content visible behind      │
│         confirmation layer (disabled interaction)        │
│                                                          │
│  . . . . . . .. . . DIMMED BACKGROUND . . . . . . . . . │
│                                                          │
│──────────────────────────────────────────────────────────│
│          **Use, Action confirmation - Component**        │
│       **EC/MDM - Varient, check and apply varient**      │
│                                                          │
│             Action Confirmation Bottom Sheet             │
│                                                          │
│                      Action Title                        │
│                         [ Icon ]                         │
│                    Confirmation Text                     │
│                                                          │
│       ┌──────────────────────────────────────────┐       │
│       │                  Primary CTA             │       │
│       └──────────────────────────────────────────┘       │
│                        (Text CTA)                        │
│                                                          │
└──────────────────────────────────────────────────────────┘
```

### Interaction Out

- Tap `Primary CTA` -> action executes, then return to **1) Device List Page**
- Tap `Text CTA` / dismiss -> return to **2) Swipe Action Page** (collapsed or previous state)

---

## 4) Device Details Page (Overview Only)

### ASCII Wireframe

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
## Layout Rules

- Content wrapper: paddingLeft = 16, paddingRight = 16
- Detail page card items: layoutSizingHorizontal = HUG

### Interaction Out

- Back navigation -> return to **1) Device List Page**
- Overview content scrolls independently within detail page

---

## Combined Flow Rules

- Device list is the entry screen for this flow.
- Swipe action is a row-level transient state of the device list.
- Action confirmation is a modal/bottom-sheet overlay on top of list/subpage context.
- Device details in this flow includes only the **Overview** page (no additional subpages).
