# Design System Specification: The Architectural Pulse

## 1. Overview & Creative North Star: "The Neon Architect"
This design system moves away from the "cluttered dashboard" trope of backend development. Instead, it adopts the **Neon Architect** philosophy: a high-end, editorial approach that treats complex logic as digital art. 

We are not just listing repositories; we are showcasing the invisible infrastructure of the web. To achieve this, the design system utilizes **intentional asymmetry**, **extreme typographic scale**, and **tonal layering**. By breaking the rigid, centered grid and using overlapping glass containers, we create an environment that feels like a sophisticated IDE—precise, powerful, and premium.

## 2. Colors & Surface Philosophy
The palette is rooted in deep obsidian tones, punctuated by high-frequency accents.

### The "No-Line" Rule
**Prohibit 1px solid borders for sectioning.** Boundaries must be defined solely through background color shifts. For instance, a `surface-container-low` section sitting on a `surface` background creates a natural, sophisticated break. If you feel the urge to draw a line, use a margin instead.

### Surface Hierarchy & Nesting
Treat the UI as a series of physical layers. We use Material Design's surface tokens to create "nested" depth:
- **Base Layer:** `surface` (#0b1326) – The canvas.
- **Sectioning:** `surface-container-low` (#131b2e) – To define large content areas.
- **Interactive Cards:** `surface-container` (#171f33) – The default state for nested content.
- **Prominent Elevates:** `surface-container-highest` (#2d3449) – Reserved for modals or active states.

### The "Glass & Gradient" Rule
To achieve a "Tech-Forward" feel, use **Glassmorphism** for floating elements (like Navbars or Hover Cards). Use `surface-variant` at 40% opacity with a `20px` backdrop blur. 
**Signature Texture:** Primary CTAs should not be flat. Apply a linear gradient: `primary-container` (#00D9FF) to `secondary-container` (#6001D1) at a 135-degree angle. This creates a "logic flow" visual metaphor.

## 3. Typography: Editorial Logic
We use three distinct typefaces to separate "Action," "Hierarchy," and "Data."

*   **Display & Headlines (Plus Jakarta Sans):** Used for big, bold statements. Plus Jakarta Sans provides a tech-native feel with high legibility. Use `display-lg` for hero statements with `-2%` letter spacing to feel "engineered."
*   **Subheadings & Titles (Inter):** The workhorse. Inter provides a neutral, professional bridge between the expressive headlines and functional body text.
*   **Body (Inter/Open Sans):** While the prompt suggests Open Sans, we utilize the **Inter** family for `body-lg` and `body-md` to maintain a cohesive tech aesthetic, reserving **Space Grotesk** (`label-md`) for technical metadata and mono-spaced "code-like" labels.

| Level | Token | Font | Size | Weight |
| :--- | :--- | :--- | :--- | :--- |
| Hero | `display-lg` | Plus Jakarta Sans | 3.5rem | 700 |
| Section | `headline-md` | Plus Jakarta Sans | 1.75rem | 600 |
| Subtitle | `title-md` | Inter | 1.125rem | 500 |
| Body | `body-md` | Inter | 0.875rem | 400 |
| Metadata | `label-sm` | Space Grotesk | 0.6875rem | 500 |

## 4. Elevation & Depth: Tonal Layering
Traditional drop shadows are forbidden. We use **Ambient Light** and **Tonal Stacking**.

*   **The Layering Principle:** Depth is achieved by placing a `surface-container-lowest` card on a `surface-container-low` background. This creates a "sunken" or "raised" effect without a single pixel of shadow.
*   **Ambient Shadows:** For floating elements (Modals/Dropdowns), use a shadow color of `#00D9FF` at 5% opacity with a `40px` blur. It should look like the glow of a monitor, not a physical shadow.
*   **The "Ghost Border" Fallback:** If accessibility requires a stroke, use `outline-variant` (#3c494d) at **15% opacity**. It should be felt, not seen.

## 5. Components: Engineered Precision

### Buttons
- **Primary:** Gradient (`primary-container` to `secondary-container`), `xl` roundedness (0.75rem). No border. White text (`on-primary`).
- **Secondary:** Transparent background, `Ghost Border` (outline-variant at 20%), text in `primary`.
- **Tertiary:** No background, `label-md` uppercase styling, `primary` color.

### Cards & Projects
**Forbid the use of divider lines.** Separate "Project Title" from "Tech Stack" using a `1.5rem` vertical gap.
- **Style:** Use `surface-container-low`. On hover, transition to `surface-container-high` and apply a `2px` left-accent border using the `primary` color.

### Inputs & Fields
- **Background:** `surface-container-lowest`.
- **Active State:** Change background to `surface-container` and add a subtle `primary` outer glow (4px blur).
- **Label:** Use `label-sm` in `on-surface-variant` positioned 8px above the input.

### Signature Component: The "Logic Trace" (Stepper)
For backend workflows, use a vertical Stepper. Instead of lines, use a gradient "pulse" that travels from `primary` to `secondary` as the user scrolls, connecting nodes of information.

## 6. Do's and Don'ts

### Do:
- **Embrace Negative Space:** Allow for large gutters (64px+) between sections to let the "tech" breathe.
- **Use Intentional Asymmetry:** Align text to the left but place supporting "code snippets" or graphics offset to the right to create a sophisticated, non-template look.
- **Color Coding:** Use `tertiary` (Teal) specifically for "Success/Live" states and `secondary` (Purple) for "In Progress/Beta" states.

### Don't:
- **Don't use 100% Black:** Always use `surface` (#0b1326). Pure black kills the depth of the glassmorphism.
- **Don't use Center-Align for Body Text:** Backend development is about structure; keep text left-aligned to mimic the hierarchy of a code editor.
- **Don't use standard Dividers:** If you need to separate content, use a background color shift or a `32px` vertical spacer. Avoid the "horizontal rule" at all costs.

### Accessibility Note:
Ensure that `on-surface-variant` text on `surface` backgrounds maintains a 4.5:1 contrast ratio. When using the Cyan `primary` color for text, ensure the background is at its darkest (`surface-container-lowest`) to guarantee readability for technical documentation.