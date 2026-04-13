# Design System Specification: The Ethereal Professional

## 1. Overview & Creative North Star
**The Creative North Star: "The Digital Atelier"**

This design system is not a utility; it is a curated environment. Moving beyond the "bootstrap" look of enterprise software, this system treats the interface as a physical workspace of layered glass, fine paper, and soft light. It rejects the rigid, boxy constraints of traditional SaaS in favor of **intentional asymmetry** and **tonal depth**. 

By utilizing wide margins, dramatic typography scales, and overlapping surfaces, we create a "High-End Editorial" experience. The goal is to make the user feel like they are interacting with a premium physical object—intelligent, expensive, and meticulously crafted.

---

## 2. Colors & Surface Architecture

The palette is rooted in monochromatic sophistication, punctuated by a singular, muted cyan accent. It is designed to feel "cool" and "architectural."

### The "No-Line" Rule
Traditional 1px solid borders are strictly prohibited for sectioning. Structural definition must be achieved through:
1.  **Background Shifts:** Placing a `surface-container-low` section against a `background` floor.
2.  **Tonal Transitions:** Using subtle gradients to suggest a change in area.
3.  **Negative Space:** Utilizing the spacing scale to create "invisible" boundaries.

### Surface Hierarchy & Nesting
Treat the UI as a series of physical layers. We use **Tonal Nesting** to define importance:
*   **Base Floor:** `background` (#f7f9fb) – The canvas.
*   **Recessed Areas:** `surface-container` (#e8eff3) – Use for sidebars or utility panels.
*   **Elevated Elements:** `surface-container-lowest` (#ffffff) – Use for primary content cards to create a "pop" of clean white against the pearl background.

### The "Glass & Gradient" Rule
To achieve the "expensive" vibe, floating elements (modals, dropdowns, sticky headers) must use **Glassmorphism**:
*   **Fill:** `surface-container-lowest` at 70% opacity.
*   **Effect:** 20px - 32px Backdrop Blur.
*   **Signature Texture:** Main CTAs should not be flat. Apply a subtle linear gradient from `primary` (#006a6a) to `primary_dim` (#005c5c) at a 145° angle to provide a "metallic silk" finish.

---

## 3. Typography

The system utilizes a dual-font strategy to balance authority with readability.

*   **Display & Headlines (Manrope):** Chosen for its geometric precision and modern "tech-luxury" feel. Use `display-lg` and `headline-lg` with tight letter-spacing (-0.02em) to create an editorial, high-contrast look.
*   **Body & UI (Inter):** The workhorse. Inter provides maximum legibility for dense enterprise data.
*   **Hierarchy as Identity:** Use `label-sm` in all-caps with increased letter-spacing (+0.05em) using the `secondary` (#546073) color for metadata. This creates a "stamped" architectural feel.

---

## 4. Elevation & Depth

We convey hierarchy through **Tonal Layering** rather than traditional structural lines.

### The Layering Principle
Depth is achieved by stacking. A `surface-container-lowest` card sitting on a `surface-container-low` section creates a natural "lift." Avoid shadows unless the element is literally "floating" over other interactive content.

### Ambient Shadows
When a floating effect is required (e.g., a primary modal):
*   **Blur:** 40px to 60px.
*   **Opacity:** 4% - 6%.
*   **Color:** Use a tinted shadow (`on_surface` at low opacity) rather than pure black to keep the "pearl" aesthetic clean.

### The "Ghost Border" Fallback
If a container requires a border for accessibility (e.g., input fields):
*   **Token:** `outline_variant` (#a9b4b9).
*   **Opacity:** Max 20%.
*   **Stroke:** 1px hairline.
*   **Constraint:** Never use 100% opaque borders.

---

## 5. Components

### Buttons
*   **Primary:** Gradient fill (`primary` to `primary_dim`). `xl` roundedness. Subtle inner-glow (1px white overlay at 10% on top edge).
*   **Secondary:** `surface-container-lowest` fill with a "Ghost Border."
*   **Hover State:** Increase shadow spread by 4px and shift gradient brightness by 5%. Transitions should be long (300ms) and "lazy" (cubic-bezier(0.4, 0, 0.2, 1)).

### Tactile Inputs
*   **Field:** `surface-container-lowest` background. 
*   **Shape:** `md` (0.75rem) roundedness.
*   **Interaction:** On focus, the "Ghost Border" transitions to `primary` at 40% opacity, and a subtle `primary_container` outer glow appears.

### Cards & Lists
*   **The Divider Ban:** Strictly forbid `<hr>` tags or divider lines. 
*   **Separation:** Use `8px` of vertical white space or a subtle shift from `surface-container-low` to `surface-background`.
*   **Radius:** Cards must use `xl` (1.5rem) roundedness to evoke the "Apple-esque" premium hardware feel.

### Additional Signature Components
*   **The "Glass Breadcrumb":** A floating navigation element using 80% transparency and heavy blur to keep the user grounded without breaking the editorial flow.
*   **Status Indicator:** Use the `primary` (cyan) as a soft pulsing "glow" rather than a hard-edged dot.

---

## 6. Do’s and Don’ts

### Do:
*   **Embrace Negative Space:** If a layout feels "crowded," double the padding. Luxury is defined by the space you *don't* use.
*   **Use Asymmetric Grids:** Align text to the left but allow imagery or data visualizations to bleed off the right edge of the grid.
*   **Optical Alignment:** Trust your eyes over the software. Because of the large `xl` radii, some icons may need manual adjustment to feel centered.

### Don’t:
*   **Don't use 100% Black:** Typography should never be `#000000`. Use `on_surface` (#2a3439) for a softer, "charcoal on paper" ink effect.
*   **Don't Use Sharp Corners:** Every interactive element must have at least a `sm` (0.25rem) radius. Sharp corners feel "industrial" and "budget."
*   **Don't Over-Animate:** Avoid bouncy, playful animations. Use slow, linear, or ease-out fades that feel like a camera lens focusing.