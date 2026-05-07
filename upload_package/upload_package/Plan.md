# 🛒 FULL SHOPIFY STORE AUDIT & REDESIGN PROMPT
## Target: getcasely.com aesthetic · Theme: Taste (Free / Dawn-based) · Mode: ULTRA THINKING

---

## CRITICAL TECHNICAL CONTEXT

My store uses the **Taste theme** — a free Shopify Online Store 2.0 theme built by Shopify.
Taste shares the **exact same codebase as Dawn** (and Sense, Craft, Crave, Refresh, Studio).
This means:
- All Dawn CSS classes apply directly (`card__inner`, `button`, `banner__content`, etc.)
- All Dawn section types are available (Image banner, Featured collection, Multicolumn, etc.)
- Custom CSS goes in **Online Store > Themes > Edit Code > Assets > base.css** (add at bottom) OR in **Theme Settings > Custom CSS**
- Liquid files follow Dawn's structure (`sections/`, `snippets/`, `templates/`, `layout/theme.liquid`)

**Target inspiration:** https://getcasely.com — a bold, high-converting phone case brand store.
**Goal:** Replicate Casely's visual energy, layout structure, and UX patterns using ONLY Taste/Dawn native sections + targeted custom CSS/Liquid overrides.

**DO NOT suggest switching themes. Work 100% within Taste theme.**

---

## PHASE 1 — COMPLETE STORE GAP AUDIT

Audit every layer of my store and produce a numbered gap analysis. For each item, state: ✅ OK / ⚠️ Needs Fix / ❌ Missing.

### 1.1 Global Theme Settings Audit

| Setting | What to Check | Casely Standard |
|---|---|---|
| Color Scheme 1 | Background / Text / Button colors | White BG, Black text, bold red/brand CTA |
| Color Scheme 2 | Dark variant | Near-black BG, white text |
| Color Scheme 3 | Neutral accent | Light gray BG |
| Heading Font | Bold, condensed, or strong sans-serif | NOT generic — should feel energetic |
| Body Font | Clean, readable | 15–16px minimum |
| Button Shape | Border radius | 4–6px (slightly rounded, not pill, not sharp) |
| Button Weight | Font weight | 700 bold, uppercase |
| Page Width | Max container | 1440px |
| Section Padding | Vertical breathing room | 60–80px desktop / 40px mobile |

### 1.2 Header / Navigation Audit

- [ ] Is there a **sticky header** (stays visible on scroll)?
- [ ] Is the **logo left-aligned** on desktop?
- [ ] Is the **announcement bar** enabled with a free shipping / promo message?
- [ ] Is there a **cart icon with item count** visible?
- [ ] Is the **search icon** present and functional?
- [ ] Does the **mobile hamburger menu** open a full-screen overlay?
- [ ] Is the navigation **flat/simple or mega menu**? (Casely uses nested "Shop by Phone" mega nav)
- [ ] Is the header **transparent over the hero** image on homepage?

### 1.3 Homepage Sections Audit

Check each section: present? correct type? content populated? styled to match Casely?

| # | Section | Expected Type | Present? |
|---|---|---|---|
| 1 | Announcement Bar | Announcement bar | ❓ |
| 2 | Hero Banner | Image banner (full width) | ❓ |
| 3 | USP / Features Bar | Multicolumn (4 cols) | ❓ |
| 4 | Featured Collections Grid | Collection list | ❓ |
| 5 | Best Sellers Carousel | Featured collection | ❓ |
| 6 | Brand Story (split image+text) | Image with text | ❓ |
| 7 | Testimonials / Reviews | Multicolumn | ❓ |
| 8 | Press Logos ("As Seen In") | Logo list | ❓ |
| 9 | Email Newsletter | Email signup | ❓ |
| 10 | Footer | Footer | ❓ |

### 1.4 Collection Page Audit

- [ ] Product card grid: 4 columns desktop, 2 columns mobile?
- [ ] Product card hover: second image swaps in?
- [ ] Are color variant swatches showing below card?
- [ ] Is there a "Quick Add" button on hover?
- [ ] Filter bar: present and functional?
- [ ] Sort dropdown: present?
- [ ] "Load More" or pagination?

### 1.5 Product Page (PDP) Audit

- [ ] Left: Image gallery with thumbnails below?
- [ ] Right: Title, price, badges, variant selectors, qty, ATC button?
- [ ] ATC button full-width, high-contrast, bold?
- [ ] Variant selector: color swatches (not dropdowns)?
- [ ] Trust badges row below ATC button?
- [ ] Product description in accordion/tabs?
- [ ] Reviews section present?
- [ ] Related products carousel at bottom?
- [ ] Sticky ATC bar on mobile scroll?

### 1.6 Cart Audit

- [ ] Slide-out drawer cart (not redirect to cart page)?
- [ ] Free shipping progress bar in cart?
- [ ] Cross-sell or upsell block inside cart?
- [ ] Trust badges in cart?

### 1.7 Footer Audit

- [ ] 4-column layout?
- [ ] Social icons (Instagram, TikTok priority)?
- [ ] Newsletter form in footer?
- [ ] Payment icons row?
- [ ] Copyright + legal links?

---

## PHASE 2 — TASTE THEME SETTINGS CONFIGURATION

Apply these exact settings in **Online Store > Themes > Customize > Theme Settings**:

### 2.1 Colors — Set 3 Color Schemes

**Color Scheme 1 — Primary (hero, CTAs, product pages):**
```
Background:          #FFFFFF
Text:                #111111
Solid button BG:     #E8303A   ← replace with your brand primary color
Solid button text:   #FFFFFF
Outline button:      #111111
Outline button text: #111111
Shadow:              #111111
```

**Color Scheme 2 — Dark (announcement bar, footer, dark sections):**
```
Background:          #111111
Text:                #FFFFFF
Solid button BG:     #FFFFFF
Solid button text:   #111111
Shadow:              #333333
```

**Color Scheme 3 — Soft Neutral (USP bar, testimonials, secondary sections):**
```
Background:          #F7F7F7
Text:                #111111
Solid button BG:     #111111
Solid button text:   #FFFFFF
Shadow:              #DDDDDD
```

> **Important:** Replace `#E8303A` (red) with your brand's primary action color throughout. Keep HIGH CONTRAST — no pastels or muted tones for CTAs.

### 2.2 Typography

In **Theme Settings > Typography**, set:

```
Heading font:  [Choose one of these in Shopify's font picker]
  ✅ Barlow Condensed (Bold 700 or Black 900) — closest to Casely
  ✅ Oswald Bold
  ✅ Bebas Neue (display only, no lowercase)
  ✅ Antonio Bold
  — AVOID: Inter, Roboto, Open Sans (too generic)

Body font:
  ✅ DM Sans
  ✅ Nunito
  ✅ Jost
  — AVOID: Arial, Helvetica system defaults

Heading base size:  48px (desktop) — push the scale up
Body base size:     16px
```

### 2.3 Buttons (Theme Settings > Buttons)
```
Border radius:    4px
```
> For font weight + uppercase — these require CSS overrides (see Phase 7).

### 2.4 Layout (Theme Settings > Layout)
```
Page width:        1400px
Spacing (small):   20px
Spacing (large):   60px
```

---

## PHASE 3 — HOMEPAGE REBUILD (Section by Section)

Go to **Online Store > Themes > Customize > Home Page**.
Build/edit sections in this EXACT order:

---

### SECTION 1: Announcement Bar
```
Section type:    Announcement bar
Color scheme:    Scheme 2 (Dark)
Text:            "🎉 FREE SHIPPING ON ORDERS OVER $35 | SHOP NEW ARRIVALS →"
Link:            /collections/new-arrivals
Auto-rotate:     OFF (single message is cleaner)
Show arrow:      ON
```

---

### SECTION 2: Header (edit existing, do not add)
```
Logo:              Upload your logo (recommended: SVG or PNG, white version for dark bg)
Logo position:     Left
Sticky header:     ON
Enable menu:       Main navigation (build this — see Phase 4)
Show cart:         ON, show count
Show search:       ON (icon style)
Show country/lang: OFF (unless needed)
Color scheme:      Scheme 1 (will go transparent over hero — enable below)
Enable transparent header on homepage: ON
```

---

### SECTION 3: Image Banner (Hero)
```
Section type:      Image Banner
Layout:            Full width
Image:             Upload bold lifestyle/product photo (high energy, colorful)
Image height:      Large (70–100vh)
Desktop content position: Middle left OR Middle center
Color scheme:      Scheme 2 (transparent overlay effect)

BLOCKS inside banner:
  Block 1 — Heading
    Text:          [YOUR MAIN HEADLINE — ALL CAPS, SHORT, BOLD]
    Heading size:  H1 Extra Large
  Block 2 — Text
    Text:          [One-line subheadline]
  Block 3 — Buttons
    Button 1 label: SHOP NOW
    Button 1 link:  /collections/all
    Button 1 style: Primary (solid)
    Button 2 label: NEW ARRIVALS
    Button 2 link:  /collections/new-arrivals
    Button 2 style: Secondary (outline)
```

---

### SECTION 4: Multicolumn — USP / Features Bar
```
Section type:      Multicolumn
Heading:           (leave blank — no heading on this bar)
Number of columns: 4
Color scheme:      Scheme 3 (light gray)
Column alignment:  Center
Image width:       Small (icons only)

COLUMNS:
  Col 1: Icon (upload 🚚 icon SVG) | "Free Shipping Over $35"
  Col 2: Icon (upload 🔄 icon SVG) | "30-Day Easy Returns"
  Col 3: Icon (upload 🛡️ icon SVG) | "1-Year Warranty"
  Col 4: Icon (upload ⭐ icon SVG) | "50,000+ Happy Customers"

MOBILE:
  Swipe = ON (columns become horizontal scroll on mobile)
```

---

### SECTION 5: Collection List — Featured Collections
```
Section type:        Collection list
Heading:             "SHOP BY COLLECTION"
Collections:         Add your top 3–4 collections
Number of columns:   3 desktop
Image ratio:         Square (1:1) or Portrait (3:4)
Color scheme:        Scheme 1
```

> **CSS enhancement needed** — see Phase 7 for collection card overlay text effect.

---

### SECTION 6: Featured Collection — Best Sellers
```
Section type:      Featured collection
Heading:           "BEST SELLERS"
Description:       "The styles everyone is loving right now."
Collection:        [Select your best sellers collection]
Products to show:  8
Enable quick add:  ON
Color scheme:      Scheme 1

Product card settings (in Theme Settings > Product cards):
  Image ratio:         Square (1:1)
  Show second image:   ON
  Show vendor:         OFF
  Show rating:         ON (if reviews app installed)
```

---

### SECTION 7: Image with Text — Brand Story
```
Section type:      Image with text
Layout:            Image first (image left, text right)
Height:            Adapt to first image
Color scheme:      Scheme 1

LEFT (image):      Upload lifestyle/brand image
RIGHT (text):
  Heading:         "MADE FOR THE BOLD"
  Text:            [2–3 sentence brand story]
  Button label:    Our Story
  Button link:     /pages/about
  Button style:    Secondary
```

---

### SECTION 8: Multicolumn — Testimonials
```
Section type:      Multicolumn
Heading:           "WHAT OUR CUSTOMERS SAY"
Number of columns: 3
Color scheme:      Scheme 3 (light gray)

Each column:
  Icon:     ⭐⭐⭐⭐⭐ (use a star image or emoji in text)
  Text:     "[Customer quote — 2–3 sentences]"
  Title:    — [Customer Name, Location]
```

---

### SECTION 9: Logo List — Press / "As Seen In"
```
Section type:   Logo list
Heading:        "AS SEEN IN"
Color scheme:   Scheme 1

Logos:          Upload grayscale/monochrome press logos
                All same height (40–48px recommended)
Enable greyscale:  ON (if theme supports, or CSS: filter: grayscale(1))
```

---

### SECTION 10: Email Signup
```
Section type:    Email signup
Heading:         "JOIN THE COMMUNITY"
Description:     "Get 15% off your first order + early access to new drops."
Placeholder:     "Enter your email address"
Button label:    GET 15% OFF
Color scheme:    Scheme 2 (Dark)
```

---

### SECTION 11: Footer (edit existing)
```
Enable country/region: OFF
Enable language:       OFF

MENUS (add 3 footer menus in Shopify Nav editor):
  "Shop" menu:       All Products, New Arrivals, Best Sellers, Sale
  "Help" menu:       FAQ, Shipping Info, Returns, Contact Us
  "Company" menu:    About Us, Blog, Press, Careers

Social icons:          Instagram, TikTok, Pinterest, Facebook
Newsletter in footer:  ON
Payment icons:         ON (auto-populated by Shopify)
Color scheme:          Scheme 2 (Dark)
```

---

## PHASE 4 — NAVIGATION BUILD

In **Online Store > Navigation**, build the Main Menu:

```
Main Menu Structure:
├── NEW ✨           → /collections/new-arrivals
│                     [add red "NEW" badge via CSS — see Phase 7]
├── SHOP BY DEVICE  → # (no link, acts as parent)
│   ├── iPhone 16 Series    → /collections/iphone-16
│   ├── iPhone 15 Series    → /collections/iphone-15
│   ├── Samsung Galaxy S24  → /collections/samsung-s24
│   ├── Samsung Galaxy S23  → /collections/samsung-s23
│   └── View All Devices    → /collections/all
├── COLLECTIONS     → # (parent)
│   ├── Best Sellers        → /collections/best-sellers
│   ├── Trending Now        → /collections/trending
│   └── Limited Edition     → /collections/limited-edition
├── SALE 🔥         → /collections/sale
└── ABOUT           → /pages/about
```

> **Taste/Dawn mega menu:** In Theme Settings > Header, enable "Enable dropdown menu" and set "Desktop menu type" to "Mega menu" if your version supports it. Otherwise it renders as a standard dropdown — style with CSS from Phase 7.

---

## PHASE 5 — PRODUCT PAGE (PDP) REBUILD

In **Online Store > Themes > Customize > Products > Default product**:

### Layout Settings:
```
Media position:         Left (sticky on scroll: ON)
Product image size:     Large
Enable image zoom:      ON
Enable video looping:   ON
Variant pills style:    Pills (not dropdown)
```

### Blocks order (drag to this exact order):
```
1. Badges (if available) — custom CSS handles NEW / SALE / BESTSELLER
2. Title
3. Price
4. Star rating (requires reviews app — Judge.me recommended, free tier available)
5. Variant picker — set to "Pills" style for all variants
6. Quantity selector
7. Buy buttons (this renders both Add to Cart + Dynamic checkout)
8. [Custom HTML block] — Trust badges row (see code below)
9. Collapsible tab: "Product Details"
10. Collapsible tab: "Shipping & Returns"
11. Collapsible tab: "Materials & Care"
```

### Trust Badges HTML block:
In the product page, add a **Custom Liquid** block with:
```html
<div class="trust-badges">
  <span>🔒 Secure Checkout</span>
  <span>🚚 Free Shipping $35+</span>
  <span>🔄 Easy Returns</span>
</div>
```

### Related Products:
```
Section:    Product recommendations
Heading:    "YOU MAY ALSO LIKE"
Products:   4
```

---

## PHASE 6 — COLLECTION PAGE REBUILD

In **Customize > Collections > Default collection**:

```
Enable filtering:        ON
Enable sorting:          ON
Filter position:         Sidebar (left)
Products per row:        4 (desktop), 2 (mobile — automatic)
Image ratio:             Square (1:1)
Enable quick add:        ON
Show vendor:             OFF
Show rating:             ON
```

---

## PHASE 7 — COMPLETE CUSTOM CSS

Add ALL of the following to **Online Store > Themes > Edit Code > Assets > base.css** at the very bottom. OR paste into **Theme Settings > Custom CSS** if available.

```css
/* =====================================================
   CASELY-STYLE OVERRIDES FOR TASTE (DAWN-BASE) THEME
   ===================================================== */

/* --- GLOBAL TYPOGRAPHY --- */
h1, h2, h3, h4, .h1, .h2, .h3 {
  text-transform: uppercase;
  letter-spacing: 0.02em;
  line-height: 1.05;
}

/* Hero headline - BIG and bold */
.banner__heading {
  font-size: clamp(2.8rem, 6vw, 5.5rem) !important;
  font-weight: 900;
  letter-spacing: -0.01em;
  line-height: 1.0;
}

/* --- BUTTONS --- */
.button, .btn, button[type="submit"],
.shopify-payment-button__button {
  font-weight: 700 !important;
  text-transform: uppercase !important;
  letter-spacing: 0.08em !important;
  border-radius: 4px !important;
  transition: all 0.2s ease !important;
}

.button--primary,
.button[class*="primary"] {
  background-color: #E8303A !important;  /* ← your brand color */
  color: #FFFFFF !important;
  border-color: #E8303A !important;
}

.button--primary:hover {
  background-color: #c42030 !important;
  border-color: #c42030 !important;
}

/* ATC button on product page - full width bold */
.product-form__submit {
  width: 100% !important;
  padding: 18px 24px !important;
  font-size: 15px !important;
  font-weight: 800 !important;
  letter-spacing: 0.1em !important;
}

/* --- PRODUCT CARDS --- */
.card-wrapper {
  transition: transform 0.25s ease, box-shadow 0.25s ease;
}
.card-wrapper:hover {
  transform: translateY(-4px);
  box-shadow: 0 16px 40px rgba(0,0,0,0.10);
}

/* Remove default card border */
.card {
  border: none !important;
  border-radius: 6px;
  overflow: hidden;
}

/* Product card title */
.card__heading {
  font-size: 13px;
  font-weight: 600;
  letter-spacing: 0.02em;
  text-transform: uppercase;
}

/* Price styling */
.price {
  font-weight: 700;
  font-size: 15px;
}

/* Sale price - red */
.price--on-sale .price-item--sale {
  color: #E8303A !important;
  font-weight: 700;
}

/* Strike-through original price */
.price--on-sale .price-item--regular {
  text-decoration: line-through;
  color: #999;
  font-weight: 400;
}

/* --- BADGES --- */
.badge {
  border-radius: 3px !important;
  font-weight: 700 !important;
  font-size: 11px !important;
  letter-spacing: 0.05em !important;
  text-transform: uppercase !important;
  padding: 3px 8px !important;
}

.badge--sale, .badge--on-sale {
  background-color: #E8303A !important;
  color: #fff !important;
}

/* --- ANNOUNCEMENT BAR --- */
.announcement-bar {
  font-weight: 600;
  font-size: 13px;
  letter-spacing: 0.06em;
  text-transform: uppercase;
}

/* --- HEADER --- */
.header {
  border-bottom: 1px solid rgba(0,0,0,0.06);
  transition: box-shadow 0.3s ease;
}

/* Sticky header shadow on scroll */
.shopify-section-header-sticky .header {
  box-shadow: 0 2px 20px rgba(0,0,0,0.08);
}

/* Nav links uppercase */
.header__menu-item {
  font-weight: 600 !important;
  font-size: 13px !important;
  text-transform: uppercase !important;
  letter-spacing: 0.06em !important;
}

/* SALE nav item - red text */
.header__menu-item[href*="sale"],
.header__menu-item[href*="/collections/sale"] {
  color: #E8303A !important;
}

/* --- COLLECTION CARDS (Collection List section) --- */
.collection-card__image-wrapper {
  overflow: hidden;
  border-radius: 6px;
}

.collection-card__image-wrapper img {
  transition: transform 0.4s ease;
}

.collection-card__image-wrapper:hover img {
  transform: scale(1.04);
}

/* Collection card overlay for text legibility */
.card--card .card__inner::after {
  content: '';
  position: absolute;
  inset: 0;
  background: linear-gradient(to top, rgba(0,0,0,0.6) 0%, transparent 55%);
  pointer-events: none;
  border-radius: inherit;
}

/* --- USP / FEATURES BAR --- */
.multicolumn-list__item .icon-wrap {
  font-size: 28px;
  color: #E8303A;
  margin-bottom: 8px;
}

/* --- TESTIMONIAL QUOTES --- */
.multicolumn-list__item-text {
  font-style: italic;
  line-height: 1.6;
}

/* --- PRESS LOGOS --- */
.logo-list__item img {
  filter: grayscale(1);
  opacity: 0.55;
  transition: opacity 0.2s, filter 0.2s;
}
.logo-list__item img:hover {
  filter: grayscale(0);
  opacity: 1;
}

/* --- TRUST BADGES (Product Page) --- */
.trust-badges {
  display: flex;
  gap: 12px;
  flex-wrap: wrap;
  margin: 12px 0;
  font-size: 12px;
  color: #555;
  font-weight: 500;
}

.trust-badges span {
  display: flex;
  align-items: center;
  gap: 4px;
  white-space: nowrap;
}

/* --- STAR RATINGS --- */
.rating .icon-star,
.rating-star {
  color: #FFB800 !important;
}

/* --- SECTION HEADINGS --- */
.collection__title,
.featured-collection__title,
.section__title {
  font-size: clamp(1.6rem, 3vw, 2.4rem);
  font-weight: 800;
  text-transform: uppercase;
  letter-spacing: 0.03em;
  text-align: center;
  margin-bottom: 8px;
}

/* --- NEWSLETTER SECTION --- */
.email-signup .field__input {
  border-radius: 4px 0 0 4px !important;
  border: 2px solid #111;
}

.email-signup .button {
  border-radius: 0 4px 4px 0 !important;
}

/* --- QUICK ADD BUTTON --- */
.quick-add-modal__toggle,
.quick-add__submit {
  background: #111 !important;
  color: #fff !important;
  font-weight: 700 !important;
  text-transform: uppercase !important;
  letter-spacing: 0.08em !important;
  font-size: 12px !important;
}

.quick-add-modal__toggle:hover {
  background: #E8303A !important;
}

/* --- FOOTER --- */
.footer {
  border-top: 1px solid rgba(255,255,255,0.08);
}

.footer__heading {
  font-size: 11px;
  font-weight: 700;
  letter-spacing: 0.12em;
  text-transform: uppercase;
  opacity: 0.5;
  margin-bottom: 16px;
}

/* --- MOBILE FIXES --- */
@media (max-width: 749px) {
  .banner__heading {
    font-size: clamp(2rem, 8vw, 3rem) !important;
  }

  /* 2-column product grid on mobile */
  .grid--2-col-tablet-down {
    grid-template-columns: repeat(2, 1fr) !important;
  }

  /* Larger ATC button on mobile PDP */
  .product-form__submit {
    padding: 20px !important;
    font-size: 16px !important;
    position: sticky;
    bottom: 0;
    z-index: 10;
  }
}

/* --- SCROLLBAR STYLING (optional, nice touch) --- */
::-webkit-scrollbar { width: 6px; }
::-webkit-scrollbar-track { background: #f0f0f0; }
::-webkit-scrollbar-thumb { background: #111; border-radius: 3px; }
```

---

## PHASE 8 — LIQUID TEMPLATE TWEAKS

### 8.1 Add "NEW" badge to recently added products
In `snippets/card-product.liquid`, find the badge section and add before the existing badge code:

```liquid
{% if product.created_at > 'now' | date: '%s' | minus: 2592000 %}
  {%- comment -%} Within last 30 days {%- endcomment -%}
  <div class="card__badge {{ settings.badge_position }}">
    <span class="badge badge--new">NEW</span>
  </div>
{% endif %}
```

And add this CSS for the green NEW badge:
```css
.badge--new {
  background-color: #1a8c4e !important;
  color: #fff !important;
}
```

### 8.2 Add product count to collection banner
In `sections/main-collection-banner.liquid`, after the title, add:
```liquid
<p class="collection-count">{{ collection.products_count }} Products</p>
```

### 8.3 Trust badges in cart drawer
In `snippets/cart-drawer.liquid` (or `sections/cart-drawer.liquid`), above the checkout button, add:
```html
<div class="cart-trust-badges" style="display:flex;gap:16px;justify-content:center;padding:12px 0;font-size:12px;color:#666;border-top:1px solid #eee;margin-top:12px;">
  <span>🔒 Secure</span>
  <span>🚚 Free $35+</span>
  <span>🔄 Easy Returns</span>
</div>
```

---

## PHASE 9 — CONVERSION FEATURES (Casely Patterns)

These require either theme blocks or lightweight app installs:

### 9.1 Free Shipping Progress Bar in Cart
**Option A (no app):** Add custom Liquid to `cart-drawer.liquid`:
```liquid
{% assign free_shipping_threshold = 3500 %} {%- comment -%} in cents = $35 {%- endcomment -%}
{% assign remaining = free_shipping_threshold | minus: cart.total_price %}
{% if remaining > 0 %}
  <div class="free-shipping-bar">
    <p>You're <strong>{{ remaining | money }}</strong> away from FREE SHIPPING! 🎉</p>
    <div class="free-shipping-bar__track">
      <div class="free-shipping-bar__fill" style="width:{{ cart.total_price | times: 100 | divided_by: free_shipping_threshold }}%"></div>
    </div>
  </div>
{% else %}
  <p class="free-shipping-bar free-shipping-bar--achieved">🎉 You've unlocked FREE SHIPPING!</p>
{% endif %}
```

**CSS for bar:**
```css
.free-shipping-bar { padding: 12px 16px; font-size: 13px; }
.free-shipping-bar__track { background: #eee; border-radius: 100px; height: 6px; margin-top: 8px; }
.free-shipping-bar__fill { background: #E8303A; height: 100%; border-radius: 100px; transition: width 0.4s ease; }
.free-shipping-bar--achieved { color: #1a8c4e; font-weight: 700; text-align: center; }
```

**Option B (app):** Install **Free Shipping Bar by Hextom** (free on Shopify App Store).

### 9.2 Inventory Urgency
In product form, show "Only X left!" when stock is low:
```liquid
{% if product.selected_or_first_available_variant.inventory_management == 'shopify'
  and product.selected_or_first_available_variant.inventory_quantity <= 5
  and product.selected_or_first_available_variant.inventory_quantity > 0 %}
  <p class="inventory-warning">⚠️ Only {{ product.selected_or_first_available_variant.inventory_quantity }} left in stock!</p>
{% endif %}
```
```css
.inventory-warning { color: #E8303A; font-size: 13px; font-weight: 600; margin: 8px 0; }
```

### 9.3 Reviews App
Install **Judge.me Product Reviews** (free tier):
- Auto-import reviews from AliExpress/Amazon if dropshipping
- Shows star rating on product cards and PDP
- Generates review rich snippets for Google SEO

### 9.4 Exit Intent Popup
Install **Privy** (free tier) or **Klaviyo**:
- Trigger: Mouse moves to top of browser (exit intent)
- Offer: 10–15% off first order
- Collect email + phone (for SMS marketing)

### 9.5 Announcement Bar Countdown (Flash Sales)
If running a sale, modify the announcement bar text with urgency:
```
"⏰ FLASH SALE ENDS MIDNIGHT — 20% OFF EVERYTHING → USE CODE FLASH20"
```
For a live countdown, install **Hurrify** or use custom JS.

---

## PHASE 10 — MOBILE-FIRST QA CHECKLIST

Casely is predominantly mobile traffic. Test every item on iPhone Safari:

- [ ] Hero text: legible at 375px width, not cut off
- [ ] Hero CTA: thumb-reachable (bottom half of screen preferred)
- [ ] Navigation: hamburger opens smooth full-screen overlay
- [ ] Product cards: 2-up grid (NOT 1-up)
- [ ] Product images: full-width, swipe-to-navigate
- [ ] ATC button: sticky at bottom of viewport when scrolling PDP
- [ ] Cart drawer: opens from right, doesn't shift page content
- [ ] Checkout: Apple Pay / Google Pay buttons visible
- [ ] Font sizes: nothing below 14px
- [ ] Tap targets: all buttons minimum 44x44px
- [ ] Page speed mobile: target 70+ in Lighthouse
  - All images: WebP format, max 800px wide for cards, 1600px for hero
  - Lazy load: ON for all off-screen images (Shopify handles this natively)

---

## PHASE 11 — SEO & PERFORMANCE AUDIT

### SEO Checklist:
- [ ] Homepage `<title>`: `[Brand Name] | [Product Category] — Free Shipping`
- [ ] Homepage meta description: Written (140–160 chars)
- [ ] All product images: have descriptive `alt` text (not "image-1.jpg")
- [ ] All collection pages: have SEO description text (Shopify admin > Collections > Description)
- [ ] URL structure: `/collections/phone-cases` NOT `/collections/12345`
- [ ] Sitemap: Submit `yourdomain.com/sitemap.xml` to Google Search Console

### Performance:
- [ ] Compress all images before upload: use **Squoosh.app** or **TinyPNG**
- [ ] Remove unused apps (each app adds JS weight)
- [ ] Use `loading="lazy"` on images (Dawn/Taste does this natively)
- [ ] Check with **Google PageSpeed Insights** — target 90+ desktop, 70+ mobile

---

## DELIVERABLES EXPECTED FROM AI

When you process this prompt, provide for each phase:

1. **Gap Analysis Report** — Numbered list of what's wrong/missing in my current store
2. **Exact Settings** — Step-by-step instructions for every Theme Settings change
3. **CSS Output** — Complete, copy-pasteable CSS block for `base.css`
4. **Liquid Snippets** — Drop-in code for any template modifications
5. **Priority Stack** — Rank all changes by conversion impact: do HIGH impact first
6. **"Won't work in Taste" flags** — Note any Casely features that need a paid app or paid theme upgrade to replicate

---

## HARD CONSTRAINTS

- ✅ Work 100% within the **Taste theme** (Dawn codebase)
- ✅ Prefer native Shopify sections and blocks over custom code
- ✅ All custom CSS in `base.css` bottom OR Theme Settings > Custom CSS
- ✅ All Liquid changes must be isolated — never edit `theme.liquid` header/footer unless required
- ✅ Test on a **duplicated theme copy** before publishing live
- ❌ Do NOT recommend switching themes
- ❌ Do NOT modify `/checkout` or payment flows
- ❌ Do NOT suggest code that breaks existing product/collection data

---

## REFERENCE

- **Target store:**  https://getcasely.com
- **My theme:**      Taste (free) by Shopify — Online Store 2.0
- **Theme docs:**    https://help.shopify.com/en/manual/online-store/themes/themes-by-shopify/taste
- **Dawn docs:**     https://help.shopify.com/en/manual/online-store/themes/themes-by-shopify/dawn
  (Taste = Dawn under the hood — all Dawn docs apply)
- **CSS classes:**   All standard Dawn class names apply (card, banner, button, header, etc.)

---

*End of Prompt — Begin Full Audit*