# Pendry San Diego — Design System Reference

Extracted from: https://www.pendry.com/san-diego/gatherings/rfp/

---

## 1. Typography

### Font Families

| Font | Usage | Source |
|------|-------|--------|
| `Queens-Condensed` | H1, H2 headings | Custom (self-hosted WOFF2) |
| `Queens` | Large decorative text, stay-connected section headings | Custom (self-hosted WOFF2) |
| `Untitled-Sans` | Body, navigation, labels, buttons, form fields | Custom (self-hosted WOFF2) |

Font weights available:
- `Untitled-Sans`: 400 (regular), 500 (medium)
- `Queens-Condensed`: 300 (light), 400 (regular)
- `Queens`: 300 (light)

---

### Type Scale

| Style | Font | Size | Weight | Line Height | Letter Spacing | Transform | Color |
|-------|------|------|--------|-------------|----------------|-----------|-------|
| H1 | Queens-Condensed | 44px | 300 | 48px | normal | none | #231f20 |
| H2 | Queens-Condensed | 24px | 400 | 29px | 0.192px | none | #231f20 |
| Decorative Large | Queens | 44px | 300 | normal | normal | none | #65656a |
| Decorative Body | Queens | 40px | 400 | normal | normal | none | #4a4a4a |
| Body | Untitled-Sans | 16px | 400 | 23px | normal | none | #65656a |
| Paragraph | Untitled-Sans | 20px | 400 | 28px | normal | none | #4a4a4a |
| Nav Link | Untitled-Sans | 13px | 400 | normal | 2px | uppercase | #231f20 |
| Reserve Button | Untitled-Sans | 14px | 500 | 22px | 2px | uppercase | #231f20 |
| Submit Button | Untitled-Sans | 14px | 500 | 22px | 2px | uppercase | #231f20 |
| Form Input | Untitled-Sans | 15px | 400 | normal | normal | none | #000000 |
| Form Label (floating) | Untitled-Sans | 10px | 400 | 10px | 0.016px | none | #4a4a4a |
| Footer Text | Untitled-Sans | 15px | 400 | 19.95px | normal | none | #65656a |
| Underline Link | Untitled-Sans | 16–18px | 400 | normal | normal | none | #35617a |

---

## 2. Colour Palette

### Primary Colours

| Name | Hex | RGB | Usage |
|------|-----|-----|-------|
| Primary Dark | `#231f20` | rgb(35, 31, 32) | Headings, nav links, button text, CTA text |
| Gray Sand | `#f1efeb` | rgb(241, 239, 235) | Section backgrounds (RFP box, footer) |
| White | `#ffffff` | rgb(255, 255, 255) | Main content background, form inputs |
| Body Grey | `#65656a` | rgb(101, 101, 106) | Body text, footer text, nav background |
| Text Medium | `#4a4a4a` | rgb(74, 74, 74) | Paragraphs, labels, form field text |
| Accent Blue | `#35617a` | rgb(53, 97, 122) | Underline buttons, animated links, accent |
| Dark Charcoal | `#23282d` | rgb(35, 40, 45) | Dark mobile menu background |

### Border / Subtle Colours

| Name | Value | Usage |
|------|-------|-------|
| Input Border | `rgba(102, 102, 107, 0.5)` | Form inputs, box buttons, contacts sidebar border |
| Input Border (Alt) | `rgba(122, 124, 133, 0.8)` | Stay-connected form inputs |
| Accent Border | `rgba(53, 97, 122, 0.5)` | Underline button border-bottom |
| Overlay Dark | `rgba(0, 0, 0, 0.5)` | Dark overlays |

---

## 3. Spacing & Layout

### Container

```
max-width: 1140px
padding: 0 24px
margin: 0 auto
```

### Page / Main Element

```
width: 1200px (at desktop viewport)
```

### Section Padding Scale

| Token | Value | Usage |
|-------|-------|-------|
| Spacing Small | `16px` | Nav sections |
| Spacing Medium | `64px` | RFP box section (top + bottom) |
| Spacing Large | `119px` | Footer (top + bottom) |
| Spacing XL | `135px` | Stay-connected section (top + bottom) |
| Form Row Gap | `30px` | Bottom margin between form rows |

### Grid / Flexbox Patterns

- **RFP Form Layout**: Bootstrap-style flexbox row
  - Form column: `col-lg-6` (~558px wide at 1200px viewport)
  - Contact info column: `col-lg-5 offset-lg-1` (~465px wide, offset 1 col)
  - Gutter: 12px per side (24px total between cols)

- **Footer Layout**: CSS Grid
  - 4 columns: `167px 288px 403px 234px` (logo, address+social, nav links, LVX)
  - Gap: `30px 20px`

- **Nav (Desktop)**: Flexbox horizontal
  - Nav bar height: 66px
  - Header total height: 146px

---

## 4. Visual Hierarchy

### Heading Structure

1. **H1** (Queens-Condensed, 44px/300) — Page title: "Plan Your San Diego Meetings & Events"
2. **H2** (Queens-Condensed, 24px/400) — Section titles: "Contact Information", "Stay connected"
3. **Decorative headings** (Queens, 44px/300) — Used for emotional/marketing copy blocks

### Which Elements Use Which Fonts

- **Queens-Condensed**: All `<h1>` and `<h2>` elements
- **Queens**: Large decorative pull-quotes and stay-connected headings
- **Untitled-Sans**: Everything else — navigation, body, labels, buttons, footer

### Button Hierarchy

| Variant | Class | Style |
|---------|-------|-------|
| Primary CTA | `.c-button--box` | Transparent bg, 1px border `rgba(102,102,107,0.5)`, uppercase, 2px tracking, 14px/500, height 58px, width 250px |
| Secondary (nav RESERVE) | `.c-button--secondary` | No border, transparent bg, uppercase, 2px tracking, 14px/500 |
| Ghost/Underline | `.c-button--underline` | No bg/border, color `#35617a`, border-bottom 1px `rgba(53,97,122,0.5)` |
| Animated Link | `.c-button--animated` | Same as underline, animated on hover |
| Small | `.c-button--sm` | Reduced size modifier |

### Link Styles

- Nav links: uppercase, 13px, 2px letter-spacing, `#231f20`
- Footer links: 15px, `#65656a`, no underline
- Accent links: `#35617a`, animated underline border-bottom
- General links inherit body styles

---

## 5. Components & Patterns

### Navigation — Desktop (`navp`)

- Bar background: `#f1efeb`
- Height: 66px
- Logo: SVG, centered
- Menu items: Untitled-Sans, 13px, uppercase, 2px letter-spacing, `#231f20`
- Submenu: image + links in columns, submenu images 4:5 ratio (800×1000px)
- RESERVE button: `.c-button--secondary`, right-aligned

### Navigation — Mobile (`navm`)

- Background: `#23282d` (dark charcoal)
- Full-screen overlay drawer
- Burger trigger: `.c-hamburger` with 4 items

### Header Container (`.header-container`)

- Position: relative
- Total height: 146px (nav bar 66px + top utility bar ~80px)
- Background: transparent (`.inverse-default` modifier for light page backgrounds)
- Logo area: `.c-logo` with SVG image

### RFP Box Section (`.rfp-box`)

- Background: `#f1efeb`
- Padding: 64px top/bottom (via `.c-spacing__top--medium` + `.c-spacing__bottom--medium`)
- Inner container: max-width 1140px, padding 24px horizontal
- **Two-column layout**: form (col-lg-6) + contact info sidebar (col-lg-5 offset-lg-1)
- Info column (`.rfp-box__info`): padding-bottom 85px
- Contacts sidebar (`.rfp-box__contacts`):
  - Border-left: 1px solid `rgba(102,102,107,0.5)`
  - Padding: 40px all sides

### Form Fields (floating label pattern)

- All form rows: margin-bottom 30px
- Input wrapper (`.form__row`): relative positioned, height 56px
- Label (`.form__label`): absolute positioned, 10px font, floats up on focus
- Input (`.form__input--text`): height 56px, border 1px solid `rgba(102,102,107,0.5)`, border-radius 0, padding `15px 8px 0px 16px`
- Select (`.form__input--select`): same as text input, custom chevron SVG background-image
- Textarea (`.form__input--textarea`): height ~120px, padding `26px 8px 0px 16px`
- File upload (`.form__upload-button`): custom file picker with SVG icon

### Submit Button (`.c-button--box`)

- Width: 250px, height: 58px
- Background: transparent
- Border: 1px solid `rgba(102,102,107,0.5)`
- Font: Untitled-Sans 14px/500, uppercase, 2px letter-spacing
- Color: `#231f20`
- Border-radius: 0

### Stay-Connected Section (`.stay-connected`)

- Padding: 135px top/bottom
- Background: transparent (white body background shows through)
- Layout: 2-column flex (`col-12 col-lg-7` for copy, form alongside)
- Heading: Queens 44px weight 300, `#65656a`
- Description: Queens 40px, `#4a4a4a`
- Form inputs: height 48px, border `1px solid rgba(122,124,133,0.8)`, padding 10px
- Submit: `.c-button--animated c-button--underline`, color `#35617a`, font-size 18px

### Footer (`.footer`)

- Background: `#f1efeb`
- Padding: 119px top/bottom
- Layout: CSS Grid, 4 columns (`167px 288px 403px 234px`), gap `30px 20px`
- **Col 1**: Pendry rose logo (SVG)
- **Col 2**: Hotel name, address, phone, social icons (Facebook, Instagram)
- **Col 3**: Navigation links (Contact, Magazine, Media, FAQs, partner hotels, shop, careers, legal)
- **Col 4**: LVX logo (SVG)
- Font: Untitled-Sans 15px, `#65656a`
- Links: no underline, `#65656a`

### Social Icons (`.c-social`)

- SVG icons, 32×32px
- Classes: `.c-social__link--facebook`, `.c-social__link--instagram`
- Background-image SVG approach

### Cookie Banner

- Alert dialog overlay, standard Montage International consent flow

---

## 6. Imagery & Media

### Image Aspect Ratios

| Usage | Ratio | Example Dimensions |
|-------|-------|--------------------|
| Nav submenu preview images | 4:5 (portrait) | 800×1000px |
| Nav dropdown images (desktop) | ~3:2 | 960×700px |
| Hero images (other pages) | 16:9 or 3:2 | — |

### Image Treatments

- Submenu images: full-bleed, object-fit cover
- No visible image overlays on this RFP page (form-focused layout)

### Icons

- Social icons: inline SVG via CSS background-image
- Select chevron: inline SVG base64 background-image
- File upload: SVG icon (20×20px)
- All icons: single color, `#231f20` or `#65656a`

---

## 7. Component Inventory

| Component | Class(es) | File |
|-----------|-----------|------|
| Site navigation (desktop) | `.navp`, `.navp__menu-link` | components/nav.html |
| Mobile burger menu | `.navm`, `.c-hamburger` | components/nav.html |
| Hero / page header | `.rfp-box__header` | components/hero.html |
| RFP form section | `.rfp-box`, `.form__row` | components/rfp-form.html |
| Stay-connected CTA | `.stay-connected` | components/cta-section.html |
| Footer | `.footer`, `.footer__container` | components/footer.html |
| Box button | `.c-button--box` | pendry-components.css |
| Underline button | `.c-button--underline` | pendry-components.css |
| Form input (floating label) | `.form__row`, `.form__label`, `.form__input` | pendry-components.css |

---

## 8. Usage Notes

- **Fonts are custom**: Queens, Queens-Condensed, and Untitled-Sans are proprietary fonts. For production use obtain licensing. As a fallback use `Georgia, serif` for Queens/Queens-Condensed and `Helvetica Neue, Arial, sans-serif` for Untitled-Sans.
- **Border-radius is always 0**: This is a deliberate luxury-brand design decision — no rounded corners anywhere.
- **Floating labels**: The form uses a floating label pattern where labels animate from inside the field to above it on focus/fill. This requires JavaScript to add `.form__label--focus` class.
- **Color is restrained**: The palette is intentionally muted — warm whites, grays, and one accent blue. Avoid introducing new colors.
- **All-caps sparingly**: Only navigation links, buttons, and utility labels use uppercase. Body copy and headings are sentence/title case.
- **Spacing is generous**: Large section padding (64px–135px) creates a luxury, airy feel. Maintain this breathing room.
- **The `.inverse` modifier**: Applied to header elements when the page background is light, ensuring nav text/logo appear in dark `#231f20` rather than white.
