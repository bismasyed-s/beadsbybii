# Design System Strategy: The Ethereal Atelier

## 1. Overview & Creative North Star
This design system is built to transform a digital storefront into a curated, tactile experience. Our Creative North Star is **"The Ethereal Atelier."** 

Unlike standard e-commerce platforms that rely on rigid, boxed-in layouts, this system treats the screen as a physical workspace—a soft, linen-covered table where beads are hand-sorted. We break the "template" look through **intentional asymmetry**, allowing product imagery to bleed across container boundaries, and utilizing a high-contrast typography scale that feels more like a high-end fashion editorial than a generic shop. 

The goal is to evoke the "handmade with love" sentiment by prioritizing "breath" (whitespace) and soft, organic transitions over hard structural breaks.

## 2. Colors: Tonal Depth & The "No-Line" Rule
The palette is a sophisticated blend of pastel pinks, mints, and lilacs, anchored by a deep, muted plum (`primary`) to ensure the brand feels premium, not juvenile.

*   **The "No-Line" Rule:** To maintain the "dreamy" aesthetic, designers are strictly prohibited from using 1px solid borders to define sections or cards. Boundaries must be created exclusively through background color shifts. For example, a `surface-container-low` section should sit directly on a `surface` background to create a soft, edge-less transition.
*   **Surface Hierarchy & Nesting:** Use the surface-container tiers to create organic depth. 
    *   **Base:** `surface` (#faf9f6) for the overall canvas.
    *   **Sectioning:** `surface-container-low` (#f4f4f0) for subtle content grouping.
    *   **Interaction:** `surface-container-highest` (#e1e3df) for elements that require immediate attention or hover states.
*   **The "Glass & Gradient" Rule:** Floating elements, such as navigation bars or quick-view modals, should utilize **Glassmorphism**. Use a semi-transparent `surface` color with a `backdrop-filter: blur(20px)` to allow the soft pastel backgrounds to bleed through.
*   **Signature Textures:** For primary CTAs and hero section backgrounds, use a subtle linear gradient moving from `primary` (#77556a) to `primary-container` (#fdd0ea) at a 45-degree angle. This provides a "visual soul" that flat color cannot replicate.

## 3. Typography: The Editorial Contrast
We utilize a high-low pairing of Noto Serif and Plus Jakarta Sans to convey both "graceful craftsmanship" and "modern accessibility."

*   **Display & Headlines (Noto Serif):** Use `display-lg` and `headline-lg` for product names and storytelling moments. These should often be center-aligned or placed with intentional asymmetry to draw the eye.
*   **Body & Utility (Plus Jakarta Sans):** All functional text, descriptions, and buttons must use the Sans-Serif scale. The clean, geometric nature of Jakarta provides a necessary "grounding" effect against the whimsical serif.
*   **Hierarchy Note:** Use `on-surface-variant` (#5d605c) for body copy to keep the contrast soft; reserve `on-surface` (#303330) strictly for headlines to maintain an editorial punch.

## 4. Elevation & Depth: Atmospheric Layering
Depth in this system is achieved through light and color, never through heavy shadows.

*   **The Layering Principle:** Avoid traditional "Z-index" thinking. Instead, stack containers using the surface scale. A card in `surface-container-lowest` placed on a `surface-container` background creates a natural "lift" that mimics paper resting on a table.
*   **Ambient Shadows:** When a floating effect is mandatory (e.g., a "Floating Action Button" for cart access), use an extra-diffused shadow: `box-shadow: 0 10px 30px rgba(119, 85, 106, 0.06)`. The shadow color is a tinted version of our `primary` token, ensuring the shadow feels like a natural part of the soft-lit environment.
*   **The "Ghost Border" Fallback:** If a container requires a boundary for accessibility (like an input field), use the `outline-variant` (#b1b2af) at 20% opacity. This creates a "Ghost Border" that guides the eye without breaking the flow.

## 5. Components: Softness & Intent

### Buttons
*   **Primary:** Fully rounded (`full`: 9999px). Background is `primary`, text is `on-primary`. 
*   **Secondary:** Fully rounded. Background is `secondary-container`, text is `on-secondary-container`.
*   **Interaction:** On hover, apply a subtle scale-up (1.02) rather than a color change to maintain the "handmade" softness.

### Cards & Product Displays
*   **Forbid Dividers:** Do not use lines to separate product info. Use `vertical-spacing` and `title-md` vs `body-sm` typography to create separation.
*   **Corners:** Use `xl` (3rem) for large image containers and `md` (1.5rem) for smaller UI elements. This mix of roundedness mimics the varied shapes of handmade beads.

### Input Fields
*   **Styling:** Avoid outlines. Use `surface-container-high` as a solid background fill with a `sm` (0.5rem) corner radius. 
*   **State:** When focused, the background should transition to `surface-container-lowest` with a "Ghost Border" of `primary` at 20%.

### Additional Component: "The Charm Chip"
*   A custom tag component for product attributes (e.g., "Limited Edition," "Rose Quartz"). 
*   Use `tertiary-container` with `label-md` text. The shape should be an asymmetrical pill—rounded `full` on one side and `lg` on the other—to emphasize the "handmade" quirkiness.

## 6. Do's and Don'ts

### Do:
*   **Embrace Negative Space:** Let the jewelry breathe. If you think there's enough whitespace, add 16px more.
*   **Layer Imagery:** Allow jewelry photos to slightly overlap their containers or nearby text to create a scrapbook/collage feel.
*   **Use Tonal Transitions:** Use the `mint green` (`secondary-container`) for success states and `pastel pink` (`primary-container`) for highlights.

### Don't:
*   **Don't use pure black:** Never use #000000. Use `on-surface` (#303330) to keep the vibe approachable.
*   **Don't use hard corners:** Anything less than the `sm` (0.5rem) radius is too "corporate" for this brand.
*   **Don't use traditional grids:** Avoid the 12-column "Bootstrap" look. Use offset columns and varying image sizes to make the shop feel like a boutique discovery experience.