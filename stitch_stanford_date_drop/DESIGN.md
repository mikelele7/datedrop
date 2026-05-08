# Design System Specification

## 1. Overview & Creative North Star: The Academic Salon
This design system rejects the frantic, "gamified" visual language of traditional social discovery apps. Instead, it draws inspiration from high-end editorial university publications and exclusive social clubs. The Creative North Star is **"The Academic Salon"**—a space that feels curated, intellectual, and intentionally paced. 

To break the "template" look, this system utilizes high-contrast typography scales, intentional asymmetry, and a philosophy of "negative space as a luxury." By layering surfaces rather than boxing them in, we create a digital environment that feels like physical stationery or a tech-forward alumni journal.

---

## 2. Color Philosophy & Surface Architecture
The palette is anchored by the prestigious Stanford Red, used as a surgical accent against a sea of warm, organic neutrals.

### The "No-Line" Rule
To maintain a premium, editorial feel, **1px solid borders are strictly prohibited for sectioning.** Boundaries between content areas must be defined exclusively through background color shifts or tonal transitions. 
- *Implementation:* A section using `surface-container-low` (#f5f4ee) should sit directly against a `surface` (#fbf9f3) background. The change in "paper weight" is the only divider needed.

### Surface Hierarchy & Nesting
Treat the UI as a series of physical layers—stacked sheets of fine cardstock.
- **Base Layer:** `surface` (#fbf9f3)
- **Secondary Content:** `surface-container` (#efeee8)
- **Elevated Cards/Modals:** `surface-container-lowest` (#ffffff) to provide a "pop" of clean white.
- **Deep Recesses:** `surface-dim` (#dbdad4) for background utility areas or footer contexts.

### The "Glass & Gradient" Rule
Standard flat colors can feel sterile. To inject "soul" into the interface:
- **Glassmorphism:** Use semi-transparent variants of `surface` with a `backdrop-filter: blur(20px)` for floating navigation bars or sticky headers.
- **Signature Textures:** For primary CTAs and hero headers, use a subtle linear gradient (135°) transitioning from `primary-container` (#8c1515) to `primary` (#680006). This adds a three-dimensional richness that signals "Premium."

---

## 3. Typography: The Dialogue of Form
The typography system relies on a sophisticated tension between the intellectual Serif and the functional Sans-Serif.

*   **The Editorial Voice (Newsreader):** Used for `display` and `headline` roles. This serif typeface conveys history, trust, and the collegiate spirit. It should be used for user names, section titles, and high-impact quotes.
*   **The Functional Voice (Inter):** Used for `title`, `body`, and `label` roles. Inter provides a clean, tech-forward contrast that ensures high legibility for bios, settings, and metadata.

**Hierarchy as Identity:**
- Use `display-lg` for welcome screens to create a "magazine cover" feel.
- Pair a `headline-sm` (Serif) with a `label-md` (Sans-Serif, All Caps, Letter Spacing +5%) to create a clear, sophisticated content hierarchy.

---

## 4. Elevation & Depth
In this design system, hierarchy is earned through **Tonal Layering** rather than structural scaffolding.

### The Layering Principle
Depth is achieved by "stacking" surface tiers. For example, place a `surface-container-lowest` (#ffffff) card on a `surface-container-low` (#f5f4ee) section. This creates a soft, natural lift that mimics natural paper behavior without the clutter of drop shadows.

### Ambient Shadows
When a "floating" element (like a floating action button or a modal) is required:
- **Shadow Profile:** Shadows must be extra-diffused. 
- **Values:** `box-shadow: 0 12px 32px rgba(27, 28, 25, 0.06);` 
- **The Tint Rule:** Never use pure black for shadows. Use a tinted version of `on-surface` to mimic ambient environmental light.

### The "Ghost Border" Fallback
If a border is legally required for accessibility or input clarity, use a **Ghost Border**: the `outline-variant` (#e0bfbb) at 20% opacity. 100% opaque, high-contrast borders are forbidden as they break the soft, editorial flow.

---

## 5. Components

### Buttons
- **Primary:** Gradient from `primary-container` to `primary`. Text in `on-primary` (#ffffff). Border radius: `md` (0.375rem).
- **Secondary:** Surface `surface-container-highest` (#e3e3dd) with `on-surface` text. No border.
- **Tertiary:** No background. `primary-container` text weight: 600. Focus on generous horizontal padding (1.5rem).

### Cards & Profiles
- **Style:** Use `surface-container-lowest` (#ffffff). 
- **Rule:** Forbid divider lines. Separate content using `body-md` for text and `spacing-lg` for vertical air.
- **Interaction:** On hover, transition the background to `surface-bright` and increase the ambient shadow opacity slightly.

### Input Fields
- **Background:** `surface-container-high` (#e9e8e2).
- **Border:** Ghost Border (20% `outline-variant`) only on focus.
- **Label:** Use `label-md` in `on-surface-variant` (#59413e).

### Selection Chips
- **Unselected:** `secondary-container` (#e3dfd9) with `on-secondary-container` text.
- **Selected:** `primary-container` (#8c1515) with `on-primary` text. Use `full` roundedness (pill shape).

### University Context Components (Custom)
- **The "Academic Badge":** Small, elegant tags for "Major" or "Club" using `tertiary-container` (#574410) with `on-tertiary-fixed` (#251a00) text.
- **The "Drop" Indicator:** A signature flourish using a `surface-tint` (#ae2f2a) soft-glow effect behind a profile photo to indicate a new connection.

---

## 6. Do's and Don'ts

### Do
- **Do** use generous white space. If you think there is enough space, add 16px more.
- **Do** lean into asymmetry. For example, right-align a "Match" button while left-aligning the profile name.
- **Do** use `Newsreader` for emotional moments and `Inter` for data-heavy moments.

### Don't
- **Don't** use 1px solid lines to separate list items. Use a 12px gap instead.
- **Don't** use high-saturation reds for backgrounds. Keep the red (#8C1515) as a focused accent or CTA.
- **Don't** use sharp corners. Stick to the `md` (0.375rem) and `xl` (0.75rem) rounding scale to keep the experience feeling "soft" and approachable.
- **Don't** use standard "Drop Shadows." If an element needs to feel elevated, use Tonal Layering first.