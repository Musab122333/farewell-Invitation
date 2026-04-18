# Design System Document: Synthetic Elegance

## 1. Overview & Creative North Star
This design system is built to facilitate a high-end, editorial experience for a Tech Club Farewell. We are moving away from "utilitarian tech" and toward "synthetic elegance." 

**The Creative North Star: "The Luminescent Archive."**
The goal is to treat digital space as a deep-sea or deep-space void where information doesn't sit on a grid, but floats within it. We break the "template" look through intentional asymmetry—placing typography off-center and allowing glowing accents to bleed across container boundaries. The aesthetic must feel "emotional high-tech": the precision of code mixed with the atmospheric weight of a farewell.

## 2. Colors & Atmospheric Depth
Our palette is rooted in the void (`#070e1b`) and punctuated by ionized gas glows.

*   **The "No-Line" Rule:** To maintain a premium, seamless feel, 1px solid borders are prohibited for sectioning. Boundaries must be defined through background shifts—specifically moving from `surface` to `surface-container-low`—or through soft, radial gradients that suggest a perimeter without drawing a hard line.
*   **Surface Hierarchy & Nesting:** Depth is achieved through a "Z-stack" of surfaces. 
    *   Base Layer: `surface` (`#070e1b`).
    *   Secondary Content: `surface-container-low`.
    *   Featured "Hero" Cards: `surface-container-high`.
    *   This nesting mimics sheets of dark, polished obsidian layered on top of one another.
*   **The "Glass & Gradient" Rule:** All floating elements (modals, dropdowns, or featured invitation cards) must use Glassmorphism. Apply `surface-variant` at 40% opacity with a `backdrop-filter: blur(20px)`. 
*   **Signature Textures:** Use a dual-tone linear gradient for primary CTAs: `primary` (`#81ecff`) to `primary-container` (`#00e3fd`) at a 135-degree angle. To evoke the "emotional" aspect, integrate a subtle grain texture (3% opacity) over the `background` to eliminate sterile digital banding.

## 3. Typography: The Editorial Voice
We use a tension between the technical `Space Grotesk` and the sophisticated `Manrope`.

*   **Technical Authority (Space Grotesk):** Reserved for `display`, `headline`, and `label` roles. This typeface provides the "High-Tech" soul. Use `display-lg` with a `-0.04em` letter-spacing to create a tight, cinematic impact for the club name or "FAREWELL."
*   **Human Connection (Manrope):** Used for `body` and `title` roles. Manrope’s balanced proportions provide the "Emotional" weight needed for farewell messages. 
*   **Scale Contrast:** To achieve an editorial look, avoid "medium" sizes. Pair a massive `display-md` headline directly with a small, tracked-out `label-md` in all-caps. This high-contrast pairing signals intentional, premium design.

## 4. Elevation & Depth: Tonal Layering
In this system, light comes from the elements themselves, not an external sun.

*   **The Layering Principle:** Instead of shadows, use "Inner Glows." A card sitting on `surface` should have a 1px inner stroke using `outline-variant` at 20% opacity to catch the "rim light" of the interface.
*   **Ambient Shadows:** When an object must float (e.g., a primary button), use a diffused shadow colored with `surface-tint` at 10% opacity, with a blur radius of at least `32px`. Avoid black shadows; they muddy the deep blue tones of the background.
*   **The "Ghost Border" Fallback:** If a container requires definition in a crowded space, use a Ghost Border: a 1px stroke of `primary` or `secondary` at 15% opacity. 
*   **Neon Accents:** Use "Glow-Points." A 2px wide, 40px long vertical line of `secondary` (`#d277ff`) placed asymmetrically on the edge of a container can act as a sophisticated visual anchor.

## 5. Components

### Buttons
*   **Primary:** A glassmorphic base (`surface-variant` at 20%) with a vibrant 1px border of `primary`. On hover, the background fills with a `primary` to `secondary` gradient at 10% opacity.
*   **Tertiary:** No background or border. `label-md` typography in `primary` with a `0.1em` letter-spacing and a subtle `drop-shadow` glow of the same color.

### Cards & Lists
*   **Constraint:** Forbid the use of divider lines. 
*   **Separation:** Group related items on a `surface-container-low` plinth. Use `2.5rem` (40px) of vertical white space to separate distinct content blocks.
*   **Interaction:** On hover, a card should transition its border from `outline-variant` (20%) to `primary` (60%), creating a "powering on" effect.

### Input Fields
*   **Style:** Minimalist "Underline" style. A 1px base line using `outline-variant`. Upon focus, the line expands to 2px and glows with `primary`.
*   **Labels:** Use `label-sm` in `on-surface-variant`, positioned 8px above the input line.

### Additional Signature Component: The "Particle Scrim"
*   For the Farewell context, use a background scrim component that renders slow-moving, 1px - 2px particles using `secondary_fixed_dim`. These should appear sparingly behind `display` typography to create atmospheric depth.

## 6. Do's and Don'ts

*   **DO:** Use asymmetrical layouts. Place your "Register" button or "Date" label in unexpected (but balanced) locations to break the "Bootstrap" feel.
*   **DO:** Lean into the "Glow." Use `secondary_container` for soft, large-scale radial blurs in the background to suggest a nebula effect.
*   **DON'T:** Use pure `#ffffff` for text. Use `on-surface` (`#e2e8fb`) to keep the typography integrated into the cool-toned atmosphere.
*   **DON'T:** Use the `DEFAULT` roundedness (4px) for everything. Use `none` (0px) for a sharper, more "brutalist-tech" look on large containers, and `full` for interactive chips.
*   **DO:** Ensure accessibility by checking that neon `primary` text on `surface` backgrounds maintains a 4.5:1 contrast ratio. If it fails, use `primary_dim`.