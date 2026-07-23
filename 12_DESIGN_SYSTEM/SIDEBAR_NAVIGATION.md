# Professional Sidebar Navigation Standard

**Status:** Approved Design Standard  
**Applies To:** Customer portal, admin dashboard, technician portal, account areas, and knowledge interfaces

---

## 1. Objective

Provide a premium, fast, and accessible navigation experience inspired by the discipline of leading UAE digital services while remaining unmistakably AFAQ Alhayat.

The public marketing website should normally use a refined header and mobile navigation. A persistent sidebar is reserved for authenticated portals, dashboards, complex service directories, filters, or contextual page navigation where it genuinely improves orientation.

---

## 2. Desktop Structure

The sidebar contains, in order:

1. Brand mark and product context.
2. Optional workspace, account, or property selector.
3. Primary navigation.
4. Contextual secondary navigation.
5. Utility actions.
6. User profile, help, and sign-out area.

Recommended dimensions:

- Expanded width: `280–304px`.
- Collapsed width: `72–80px`.
- Sticky height: viewport height where appropriate.
- Inner horizontal padding: `20–24px`.
- Minimum interactive target: `44 × 44px`.

The content area must not jump or lose reading position when the sidebar changes state.

---

## 3. Navigation Model

### Primary Items

Use a small set of clear destinations:

- Overview
- Services
- Bookings
- Properties or Locations
- Requests
- Reports
- Support

Names must reflect the actual product and user role. Do not expose features that are not implemented or approved.

### Grouping

- Use concise section labels only when they improve scanning.
- Avoid more than two visible hierarchy levels.
- Use disclosure controls for expandable groups.
- Preserve open state when users move between related pages.
- Display badges only for meaningful, current counts.

### Active State

The active destination must be obvious through:

- A strong text state.
- A restrained surface or left/right indicator based on direction.
- `aria-current="page"`.

Color alone is insufficient.

---

## 4. RTL and LTR

- Arabic sidebar appears on the right by default.
- English sidebar appears on the left by default.
- Chevron, indicator, padding, and animation direction mirror correctly.
- Icons with directional meaning must mirror; universal icons must not.
- Phone numbers, references, and mixed-language labels require bidirectional handling.
- Collapse and close controls remain in a predictable location in both directions.

---

## 5. Responsive Behaviour

### Desktop

- Expanded by default when task complexity benefits from labels.
- User-controlled collapse is allowed and remembered.
- Icon-only mode requires accessible names and tooltips.

### Tablet

- Use collapsed rail or overlay according to content width.
- Opening the overlay must trap focus appropriately.

### Mobile

- The sidebar becomes an off-canvas navigation drawer.
- It must not cover the full screen without a visible close control.
- Background scrolling is locked while open.
- Focus returns to the menu trigger when closed.
- Swipe gestures may supplement but never replace visible controls.

---

## 6. Visual Direction

- Quiet neutral background with controlled use of Primary Blue.
- Generous spacing and precise alignment.
- One consistent icon set.
- Subtle divider or surface difference from the content area.
- Minimal shadow only for an overlay drawer.
- No gradients, glass effects, glowing active items, or oversized icons.
- User avatar uses initials unless an approved image exists.

The sidebar must feel stable and understated, not like a promotional panel.

---

## 7. Interaction States

Every interactive item requires:

- Default.
- Hover.
- Keyboard focus.
- Active/current.
- Pressed.
- Disabled where relevant.
- Loading where navigation depends on remote state.
- Error recovery for failed actions.

Transitions should normally stay between `150–250ms` and respect reduced-motion preferences.

---

## 8. Accessibility

- Use a semantic `<nav>` with a clear accessible label.
- Lists use correct list semantics.
- Expandable groups expose `aria-expanded` and control relationships.
- Keyboard order follows the visual order.
- Focus is always visible.
- Escape closes an overlay drawer.
- Icon-only items have accessible names.
- Touch targets meet the approved minimum.
- Contrast follows WCAG 2.2 AA.

---

## 9. Content Rules

- Use short labels in the customer’s language.
- Avoid internal department names and technical abbreviations.
- Do not place canonical phone or WhatsApp values directly in the component; retrieve verified data from the canonical contact source.
- Do not duplicate service-area lists in navigation.
- Help and support must route to an approved human-support path when available.

---

## 10. Quality Gate

- [ ] Sidebar is necessary for this interface.
- [ ] Information architecture matches the user role.
- [ ] Arabic RTL and English LTR are independently tested.
- [ ] Desktop, tablet, and mobile behaviours are verified.
- [ ] Keyboard, focus, screen-reader, and reduced-motion behaviour pass.
- [ ] Expanded and collapsed states preserve context.
- [ ] No item points to missing or draft-only functionality.
- [ ] No contact or location fact is hard-coded or duplicated.
- [ ] Active, error, loading, and empty states are designed.
- [ ] Visual treatment follows the Luxury Design Direction.

