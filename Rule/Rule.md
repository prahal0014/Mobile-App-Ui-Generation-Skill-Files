## TARGETED VALIDATION RULES

These rules enforce critical UI correctness based on common failure patterns. Apply AFTER UI generation.

 ## RULE — FRAME SIZE ENFORCEMENT

Mobile screen frames **must** be exactly **393×852** with **FIXED** sizing on both axes.

- Frame `layoutSizingHorizontal` = `FIXED` (width locked to 393)
- Frame `layoutSizingVertical` = `FIXED` (height locked to 852)
- **Never use HUG** on the screen-level frame — only inner content wrappers may use HUG
- After setting `layoutMode`, always explicitly set sizing to `FIXED` — auto-layout defaults to HUG which shrinks the frame to content height
- Content that exceeds 852px should overflow within the fixed frame (use `clipsContent = true`)

❌ Not allowed:
- Screen frame height < 852 or > 852
- Screen frame with `primaryAxisSizingMode = AUTO`

If frame height ≠ 852 after creation:
👉 Set `layoutSizingVertical = 'FIXED'` and resize to 393×852

---
## RULE — FLOW TYPE UI STRUCTURE VALIDATION (MANDATORY)

After completing every frame in a flow:

- Take a screenshot of the frame
- Cross-check it against:
  - the relevant `Ui Structure` file
  - the design-system component rules
  - the frame/layout rules in `Rule.md`
- Validate:
  - frame size is correct
  - child order is correct
  - active tab/state matches the page
  - spacing/padding matches the UI structure
  - only approved design-system components are used
  - no custom/invented UI is introduced
- If any mismatch is found:
  - fix it immediately
  - re-check with screenshot before final delivery

---

## RULE — Components usage

- Use **only** components defined in the ios Design System,
- **Don't add** an additional padding,components are already having enough padding,
- **Create only** with autolayout, 
- **Never invent** a custom ui.

---

## RULE — After complete each page

**After complete each page, cross check ui structure > layout rules is satisfied** if it violates change it as per the layout rules

---

## RULE - Read Skills

**Then read supporting skills:**
- Read `Domain` skill relevant product skills
- Read `Ui Structure` skill for analysis structure
- Read `Component` skill if creating new components from scratch

---

## RULE - PROPERTIES FIRST

CRITICAL: - Use **only** components defined in the ios Design System, components are having enough padding so don't add padding for the autolaouts — never invent custom UI.
    Before making ANY change to a component instance, **always inspect its component properties first** using `get_metadata` or `figma_get_component_details`. Components often have built-in properties (booleans, text, icon swaps, variant toggles) that control their behavior.
    
---

## RULE — LIST VARIATION VALIDATION

If `List` component is used:

- Each list item must NOT repeat identical structure blindly

Check for:
- Same title repeated across items ❌
- Same subtext repeated across items ❌
- Same icon used without meaning ❌

Required:
- Title must represent unique entity
- Subtext must provide contextual variation 
- Icon must match platform/type 

If repetition detected:
👉 Replace with meaningful data variation based on module context

---

## RULE — FOOTER NAVIGATION STATE VALIDATION

If `Mobile Footer` is present:

- Active tab must match the current screen/module

Check:
- Current page = Dashboard → Dashboard tab active
- Current page = Devices → Devices tab active
- Current page = Patches → Patches tab active
- Current page = Deploy → Deploy tab active
- Current page = More / submodules → More tab active

❌ Not allowed:
- Random tab highlighted
- Default tab selected without context
- Multiple tabs appearing active

If mismatch:
👉 Correct the active tab to match the current module

---

## RULE — PRE-DELIVERY STRUCTURE CHECK (MANDATORY)

Before final output, always verify with metadata:

- Screen children order is exactly:
  1. `Title`
  2. `Content Wrapper`
  3. `Footer Nav`
- `Title.y = 0`
- `Content Wrapper.y = Title.height`
- `Footer Nav.y = 766` for `393x852` mobile frame
- `Content Wrapper` fill is solid white

If any check fails:
👉 Fix it first, then provide result.

---

## RULE — How to detect platform

1. Screenshot the target frame and check its dimensions using `get_metadata`
2. Apply these rules:

| Frame Width | Platform | Product Knowledge Skill |
|-------------|----------|------------------------|
| **≤ 500px** (e.g., 393x852) | **Mobile** | Read `endpoint-central-mobile-app` skill (master first, then the relevant `references/` file) |
| **> 500px** (e.g., 1440x860) | **Web** | Read `product-knownledge` skill |

3. If the user explicitly mentions "mobile" or "web", use that as override — don't rely on dimensions alone.

---

## Rule - What NOT to Do

- Never create frames outside the target design frame
- Never generate Mermaid diagrams or flow charts
- Never write extensive analysis documents in Figma
- Never add annotation layers or sticky notes unless explicitly asked
- Never create "before/after" comparison layouts
- Keep chat analysis minimal — the Figma result IS the deliverable
- Never use web components in a mobile frame or mobile components in a web frame
- **Never manually delete/hide a node if the component has a boolean property to toggle it** — use the property
- **Never clone a component and leave its icon/variant properties unchanged** — always set the correct icon, variant, and text properties for the new context

---
