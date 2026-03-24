# Design System Strategy: The Architectural Anchor

## 1. Overview & Creative North Star: "The Curated Command"
The objective of this design system is to transform administrative hostel management from a chore into a high-end editorial experience. We are moving away from the "cluttered dashboard" trope and toward **The Curated Command**.

The North Star of this system is **Structured Serenity**. We achieve this by utilizing intentional asymmetry, expansive breathing room, and a "layered glass" philosophy. We don't just show data; we frame it. By prioritizing high-contrast typography scales and tonal depth over rigid lines, we create a workspace that feels like a premium physical office—stable, professional, and sophisticated.

---

## 2. Color Theory & Spatial Depth
This palette is rooted in `primary` (#003461), a deep, authoritative blue that anchors the experience. We move beyond flat UI by treating colors as physical layers.

### The "No-Line" Rule
**Explicit Instruction:** Designers are prohibited from using 1px solid borders to section content. Boundaries must be defined solely through background shifts. 
*   **Implementation:** Place a `surface_container_lowest` (#ffffff) card on a `surface_container_low` (#e6f6ff) section. The shift in hex value is the divider.

### Surface Hierarchy & Nesting
Treat the UI as a series of stacked sheets of fine paper or frosted glass.
*   **Level 0 (Base):** `surface` (#f3faff) - The vast canvas.
*   **Level 1 (Sections):** `surface_container` (#dbf1fe) - Defining broad workspace areas.
*   **Level 2 (Active Cards):** `surface_container_lowest` (#ffffff) - High-priority data points.
*   **Level 3 (Interactions):** `surface_bright` (#f3faff) - Hover states and active selections.

### The "Glass & Gradient" Rule
To avoid a "generic" SaaS look, use **Glassmorphism** for floating elements (e.g., Modals, Navigation bars). 
*   **Formula:** `surface_container_low` at 80% opacity + `backdrop-blur: 12px`.
*   **Signature Textures:** Use a subtle linear gradient for primary CTAs: `primary` (#003461) to `primary_container` (#004b87) at a 135-degree angle. This adds "soul" and depth that a flat fill cannot provide.

---

## 3. Typography: The Editorial Voice
We utilize a tri-font system to separate brand authority from administrative utility.

*   **Display & Headline (Manrope):** Our "Authoritative Voice." Use `display-lg` (3.5rem) for welcome screens and `headline-sm` (1.5rem) for section headers. Manrope’s geometric nature feels modern yet stable.
*   **Title & Body (Inter):** Our "Functional Core." Inter is used for data density. `title-md` (1.125rem) should be used for card titles to ensure high legibility during fast-paced management tasks.
*   **Labels (Work Sans):** Our "Micro-Utility." Used for `label-sm` (0.6875rem) in status badges and form labels. The slightly wider tracking of Work Sans ensures clarity at small scales.

---

## 4. Elevation & Depth: Tonal Layering
Traditional drop shadows are too "cheap" for this system. We use **Ambient Softness**.

*   **The Layering Principle:** Depth is achieved by stacking. An inner container should always be "whiter" or "brighter" than its parent to appear closer to the user.
*   **Ambient Shadows:** If a floating element (like a dropdown) requires a shadow, use: `box-shadow: 0 12px 32px -4px rgba(7, 30, 39, 0.06)`. Note the use of `on_surface` (#071e27) for the shadow tint—never pure black.
*   **The "Ghost Border":** If a border is required for accessibility, use `outline_variant` (#c2c6d1) at **15% opacity**. It should be felt, not seen.

---

## 5. Components: Administrative Elegance

### Data Cards
*   **Style:** No borders. Background: `surface_container_lowest`.
*   **Spacing:** `padding: 1.75rem` (8).
*   **Asymmetry:** Align primary data (e.g., Room Number) to the top left in `headline-sm`, and secondary status (e.g., Cleaning Status) to the bottom right using a `secondary_container` chip.

### Interactive Form Elements
*   **Input Fields:** Use `surface_container_highest` (#cfe6f2) as the background. On focus, transition the background to `surface_container_lowest` and add a 2px "Ghost Border" of `primary`.
*   **Buttons:**
    *   **Primary:** Gradient fill (`primary` to `primary_container`), `xl` (0.75rem) roundedness.
    *   **Secondary:** `surface_container_high` fill with `on_surface` text. No border.

### Status Badges (The Indicators)
*   **Approved/Available:** `secondary_container` (#acf4a4) background with `on_secondary_container` (#307231) text.
*   **Alert/Urgent:** `tertiary_container` (#852c00) background with `on_tertiary_container` (#ffa27f) text.
*   **Error:** `error_container` background with `on_error_container` text.

### The "Ghost" List
*   **Rule:** Forbid divider lines. Use `margin-bottom: 0.6rem` (3) and alternating tonal shifts (`surface_container_low` vs `surface_container_lowest`) to distinguish list items.

---

## 6. Do’s and Don’ts

### Do:
*   **Do** use `20` (4.5rem) or `24` (5.5rem) spacing for major section gutters to allow the layout to "breathe."
*   **Do** use `surface_dim` (#c7dde9) for inactive or "disabled" background states to maintain the blue-tinted professional atmosphere.
*   **Do** utilize `full` (9999px) roundedness for tags and badges, but keep `xl` (0.75rem) for main functional containers.

### Don’t:
*   **Don't** ever use #000000 for text. Use `on_surface` (#071e27) for high-contrast headers and `on_surface_variant` (#424750) for secondary body text.
*   **Don't** use standard "Alert Red" for everything. Reserve `tertiary` (deep orange/brown) for "Action Required" and `error` for "System Failure." 
*   **Don't** use 1px dividers. If you feel the need for a line, increase the spacing (`gap`) instead.