# Design System Strategy: The Digital Vault

## 1. Overview & Creative North Star
The "Creative North Star" for this design system is **"The Digital Vault."** 

We are not building a standard e-commerce store or a generic database; we are creating a high-end, editorialized sanctuary for collectors. The experience must feel like a high-tech obsidian gallery where physical assets meet digital precision. 

To break the "template" look, we move away from rigid, boxed grids. Instead, we use **intentional asymmetry** and **overlapping layers**. A card’s rarity or price trend shouldn't just be a text label; it should be an atmospheric presence. By utilizing high-contrast typography scales—pairing the aggressive, wide stance of *Space Grotesk* with the technical precision of *Manrope*—we create a rhythm that feels both "Street-Tech" and "Elite Finance."

## 2. Colors: Tonal Depth & Atmospheric Accents
The palette is rooted in the "Abyss" (`#0c0e11`). We use high-vibrancy accents not as mere decoration, but as "Energy Signatures" that identify the game universe.

*   **Primary (`#69daff`):** Use for "Electric" or tech-focused interactions (e.g., Yu-Gi-Oh!).
*   **Secondary (`#ac89ff`):** Reserved for "Mystic" or high-rarity indicators (e.g., Magic: The Gathering).
*   **Tertiary (`#ff6e85`):** Reserved for "Fire" or aggressive market movements (e.g., Pokémon or price drops).

### The "No-Line" Rule
**Prohibit 1px solid borders for sectioning.** Boundaries are defined by background shifts. To separate a sidebar from a main feed, place a `surface-container-low` (`#111417`) panel against the `surface` (`#0c0e11`) background. Hard lines feel cheap; tonal transitions feel expensive.

### Surface Hierarchy & Nesting
Treat the UI as a series of physical layers. 
*   **Base:** `surface-dim` (`#0c0e11`).
*   **Mid-Ground:** `surface-container` (`#171a1d`) for secondary content areas.
*   **Foreground/Focus:** `surface-container-highest` (`#23262a`) for active cards or modals.
Nesting should always move from Darker (background) to Lighter (foreground) to simulate light hitting a raised object.

### The "Glass & Gradient" Rule
Floating elements (like price popovers or hovering cards) must use **Glassmorphism**. Apply `surface-variant` (`#23262a`) at 60% opacity with a `20px` backdrop-blur. 
Use subtle gradients for CTAs, transitioning from `primary` (`#69daff`) to `primary-container` (`#00cffc`) at a 135-degree angle to provide a "liquid crystal" feel.

## 3. Typography: The Editorial Edge
Typography is our primary tool for conveying "Data-Rich Premium."

*   **Display & Headlines (*Space Grotesk*):** This is our "Stylized" voice. Use `display-lg` for card names and `headline-md` for section titles. Its geometric, slightly futuristic cut communicates high-tech authority.
*   **Titles & Body (*Manrope*):** This is our "Data" voice. Use `title-md` for price figures and `body-md` for card descriptions. *Manrope* offers the legibility required for dense statistics without losing the premium feel.
*   **Labels (*Inter*):** Use `label-sm` in all-caps with a `0.05rem` letter-spacing for micro-data (e.g., "SET NUMBER" or "MARKET CAP"). This adds a "technical blueprint" aesthetic to the data.

## 4. Elevation & Depth
In this system, elevation is a property of light and opacity, not geometry.

*   **The Layering Principle:** Place `surface-container-lowest` (`#000000`) elements inside `surface-container-low` (`#111417`) sections to create "recessed" wells for data tables. Place `surface-container-highest` cards on `surface` backgrounds to create a "lift."
*   **Ambient Shadows:** Use shadows sparingly. When required, the shadow must be `0 24px 48px`, color: `rgba(0, 0, 0, 0.4)`. Avoid grey; shadows should feel like the absence of light in the charcoal void.
*   **The "Ghost Border" Fallback:** If a border is required for accessibility, use the `outline-variant` (`#46484b`) at 15% opacity. It should be felt, not seen.
*   **Glassmorphism Depth:** To truly achieve the "high-tech" look, apply a `1px` inner-glow (stroke) using `primary` at 10% opacity on the top and left edges of glass containers.

## 5. Components

### Cards (The Hero Component)
*   **Structure:** No borders. Use `xl` (`1.5rem`) rounded corners.
*   **Surface:** Use `surface-container-high` with a subtle gradient overlay.
*   **Data Overlay:** Use `label-md` for rarity. Price trends (`error` for down, `primary` for up) should use the `primary_dim` or `error_dim` values to ensure legibility against dark backgrounds.

### Buttons
*   **Primary:** `primary` background, `on-primary` text. `full` roundedness. No shadow, but a subtle glow using a `2px` blur of the `primary` color on hover.
*   **Tertiary (Ghost):** No background. `primary` text. Use `spacing-2` (`0.4rem`) for horizontal padding to keep them sleek.

### Input Fields
*   **Style:** `surface-container-lowest` background. No border, only a bottom-aligned `2px` accent line that glows in `primary` when focused. 
*   **Typography:** User input should be `body-lg` in *Manrope*.

### Price Indicators (Custom Component)
*   **Trend Sparklines:** Use `primary` (up) or `error` (down) with a `1.5` weight stroke. 
*   **Pill Shuttles:** Use `secondary-container` for neutral price holds, ensuring the `on-secondary-container` text remains high-contrast.

## 6. Do's and Don'ts

### Do:
*   **Use breathing room:** Use `spacing-16` (`3.5rem`) between major sections to let the high-end typography shine.
*   **Layer your surfaces:** Always place higher-contrast data on a darker "recessed" surface.
*   **Embrace asymmetry:** Offset card images so they break the container boundary slightly (using negative margins) for a dynamic, non-templated look.

### Don't:
*   **Don't use pure white:** Never use `#ffffff`. Use `on-surface` (`#f9f9fd`) to avoid visual fatigue and maintain the "Digital Vault" atmosphere.
*   **Don't use dividers:** Never use a horizontal rule `<hr>`. Use a `spacing-8` (`1.75rem`) vertical gap or a color shift from `surface` to `surface-container`.
*   **Don't crowd data:** If a card has 10 data points, use `label-sm` and increase the tracking. Quality of data over quantity of ink.