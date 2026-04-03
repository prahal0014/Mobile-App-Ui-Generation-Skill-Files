# Agent Uninstallation OTP UI Structure (Text Version)

## ASCII Wireframe

```
┌──────────────────────────────────────────────────────────┐
│                                                          │
│                  **Title - Component**                   │
│                    (Example: More)                      │
│                                                          │
│──────────────────────────────────────────────────────────│
│   Background Page (More list content visible/dimmed)    │
│                                                          │
│   ┌──────────────────────────────────────────────────┐   │
│   │            Agent Uninstallation OTP              │   │
│   │                                                  │   │
│   │ Use the following time-based OTP to uninstall    │   │
│   │ Agent and Distribution Server manually.          │   │
│   │                                                  │   │
│   │ ┌──────────────────────────────────────────────┐ │   │
│   │ │ 2 0 3 4 8 9                           [Share]│ │   │
│   │ └──────────────────────────────────────────────┘ │   │
│   │                                                  │   │
│   │ OTP is valid for 00:37:50                        │   │
│   │                (timer in red)                    │   │
│   ├──────────────────────────────────────────────────┤   │
│   │                     Close                        │   │
│   └──────────────────────────────────────────────────┘   │
│                                                          │
│──────────────────────────────────────────────────────────│
│                Footer Nav - Component                    │
│                   (More tab selected)                   │
└──────────────────────────────────────────────────────────┘
```

## Visual Hierarchy

Screen
 ├── Header Region
 │     └── Title - Component (More)
 │
 ├── More List Region (Dimmed while modal is open)
 │     └── Use, list Action - Component (includes Agent Uninstall OTP row)
 │
 ├── OTP Modal (Bottom Sheet Style)
 │     ├── Modal Title: Agent Uninstallation OTP
 │     ├── Description: Time-based OTP usage guidance
 │     ├── OTP Value Container
 │     │     ├── 6-digit OTP (spaced digits)
 │     │     └── Share Action Icon/Button
 │     ├── OTP Validity Timer (countdown, red emphasis)
 │     └── Primary Dismiss Action: Close
 │
 └── Footer Nav - Component (Fixed, More active)

## Behaviour Notes

- The OTP screen is presented as a modal over the `More` page, with dimmed background.
- OTP is displayed in a single bordered field for easy copy/read.
- Share icon triggers OS-level share sheet with OTP value.
- Timer is live countdown and should refresh every second.
- On expiry, OTP value should be invalidated and refreshed via backend call.
- Tapping `Close` dismisses the modal and returns to the `More` page.
- Footer stays visible underneath modal context, with `More` tab active.

## Component Notes

- Title: `Title - Component`
- List container: `Use, list Action - Component`
- Footer: `Mobile Footer`
- Modal container: rounded top corners, elevated over dim overlay
- OTP value and timer should follow existing typography scale used in `More` flow
