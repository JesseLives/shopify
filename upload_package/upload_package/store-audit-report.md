# Shopify Store Audit & Redesign Report
### Taste Theme (Dawn-Based) → Casely-Style Conversion
**Audit Date:** May 7, 2026 | Based on live theme files from Project.zip

---

## PRIORITY STACK — Do These First

| Priority | Item | Impact | Effort |
|---|---|---|---|
| 🔴 P1 | Enable transparent header on homepage | High — hero looks broken without it | 2 min |
| 🔴 P1 | Switch menu_type_desktop to "mega" | High — Shop by Device nav won't work | 2 min |
| 🔴 P1 | Add trust badges + free shipping bar to cart drawer | High — direct conversion impact | 20 min |
| 🔴 P1 | Fix heading font to bold/condensed (Barlow Condensed or Oswald) | High — visual energy entirely depends on this | 2 min |
| 🔴 P1 | Add heading + text blocks to Image With Text section | High — brand story section is blank | 5 min |
| 🟡 P2 | Upload real hero + brand story images | High — placeholders will break on publish | — |
| 🟡 P2 | Add inventory urgency Liquid to product page | Medium — proven conversion lift | 10 min |
| 🟡 P2 | Add product count to collection banner | Medium | 5 min |
| 🟡 P2 | Fill in all social links (Instagram, TikTok) | Medium | 5 min |
| 🟡 P2 | Build navigation structure (Shop by Device mega menu) | Medium | 15 min |
| 🟢 P3 | Install Judge.me reviews app | Medium — needs account setup | 30 min |
| 🟢 P3 | Upload press logos to Logo List section | Low | — |
| 🟢 P3 | Fix announcement bar color scheme (scheme-4 → scheme-2) | Low | 2 min |
| 🟢 P3 | SEO meta titles/descriptions | Low | ongoing |

---

## PHASE 1 — GAP ANALYSIS REPORT

### 1.1 Global Theme Settings

| Setting | Current Value | Casely Standard | Status |
|---|---|---|---|
| Color Scheme 1 | White/#111/#E8303A | White/Black/Bold Red | ✅ |
| Color Scheme 2 | #111/#fff | Dark BG, white text | ✅ |
| Color Scheme 3 | #f7f7f7/#111 | Light gray neutral | ✅ |
| Heading Font | **Figtree n5 (medium weight)** | Bold condensed energy font | ⚠️ Fix |
| Heading Scale | 125% | 48px+ desktop | ⚠️ Marginal |
| Body Font | DM Sans | DM Sans | ✅ |
| Button Border Radius | 4px | 4–6px | ✅ |
| Badge Corner Radius | 40px (pill — theme setting) | 3px (overridden via CSS) | ✅ via CSS |
| Page Width | 1400px | 1400px | ✅ |
| Section Spacing | 60px | 60–80px | ✅ |
| Cart Type | Drawer | Drawer | ✅ |

**Figtree fix:** Go to Theme Settings > Typography > Heading Font. Change to **Barlow Condensed Bold** (closest to Casely), or **Oswald Bold**. Increase Heading Scale to 140%.

---

### 1.2 Header / Navigation

| Check | Status | Notes |
|---|---|---|
| Sticky header | ✅ `sticky_header_type: "always"` | Confirmed in header-group.json |
| Logo left-aligned | ✅ `logo_position: "middle-left"` | Correct |
| Announcement bar | ⚠️ Scheme-4 | Should be scheme-2 (dark). Also auto_rotate is ON |
| Cart icon with count | ✅ Default Dawn behavior | |
| Search icon | ✅ Default Dawn behavior | |
| Mobile hamburger | ✅ Dawn's menu-drawer | Full overlay |
| Mega menu | ❌ `menu_type_desktop: "dropdown"` | Must change to `"mega"` for Shop by Device nav |
| **Transparent header on homepage** | ❌ **NOT ENABLED** | `enable_transparent_header` missing from header settings — hero banner will have opaque header over it |
| Marquee ticker bar | ℹ️ Custom app block present | Scrolling ticker with 3 messages found above header — nice bonus |

**Fix #1 — Enable transparent header:**
In Customize → Header section settings, look for "Enable transparent header on homepage" toggle → turn ON.

**Fix #2 — Enable mega menu:**
In Customize → Header → Desktop menu type → change from "Dropdown" to "Mega menu".

---

### 1.3 Homepage Sections

| # | Section | Type | Status | Notes |
|---|---|---|---|---|
| 1 | Announcement Bar | announcement-bar | ✅ | Text & link correct. Color scheme-2 on homepage, scheme-4 globally — fix global |
| 2 | Hero Banner | image-banner | ✅ | Headline, buttons, scheme-2 all set. ⚠️ Image is placeholder path |
| 3 | USP / Features Bar | multicolumn (4 col) | ✅ | All 4 columns configured, scheme-3 |
| 4 | Featured Collections Grid | collection-list | ✅ | 3 collections, 3 cols, scheme-1 |
| 5 | Best Sellers Carousel | featured-collection | ✅ | 8 products, quick_add, scheme-1 |
| 6 | Brand Story | image-with-text | ⚠️ | **Only has button block — missing heading + text blocks** |
| 7 | Testimonials | multicolumn | ✅ | 3 reviews, scheme-3 |
| 8 | Press Logos | logo-list | ⚠️ | Section exists, **no logos uploaded** |
| 9 | Email Signup | email-signup | ✅ | Scheme-2, correct copy |
| 10 | Footer | footer | ✅ | Present in section order |

**Fix brand story section:** In Customize → Homepage → Image with text → Add Block → "Heading" → text "MADE FOR THE BOLD". Add Block → "Text" → your 2–3 sentence brand story.

---

### 1.4 Collection Page

| Check | Status | Notes |
|---|---|---|
| 4-col desktop grid | ✅ `columns_desktop: 4` | |
| 2-col mobile grid | ✅ `columns_mobile: "2"` | |
| Second image on hover | ✅ `show_secondary_image: true` | |
| Color variant swatches | ⚠️ Depends on variant names | Taste supports pills but swatch images require manual setup or app |
| Quick Add button | ✅ `quick_add: "button"` | |
| Filter sidebar | ✅ `filter_type: "vertical"` | Left sidebar |
| Sort dropdown | ✅ `enable_sorting: true` | |
| Pagination | ✅ 16 products per page | Uses Dawn's built-in pagination |

---

### 1.5 Product Page (PDP)

| Check | Status | Notes |
|---|---|---|
| Image gallery left, thumbnails | ✅ `gallery_layout: "thumbnail"`, `media_position: "left"` | |
| Sticky product info on scroll | ✅ `enable_sticky_info: true` | |
| Image zoom | ✅ `image_zoom: "lightbox"` | |
| Title block | ✅ | |
| Price block | ✅ | |
| Star rating block | ✅ | Block present, but **needs reviews app installed** |
| Variant pills (not dropdown) | ✅ `picker_type: "button"` | |
| Quantity selector | ✅ | |
| ATC + Dynamic checkout | ✅ `show_dynamic_checkout: true` | |
| Trust badges block | ✅ Custom Liquid block with 🔒🚚🔄 | |
| 3 Collapsible tabs | ✅ Details / Shipping / Materials | |
| Related products | ✅ 4 products, heading "YOU MAY ALSO LIKE" | |
| Badges block | ⚠️ Not an explicit block | Handled in card-product.liquid template |
| Inventory urgency text | ❌ NOT ADDED | Liquid snippet needed (see Phase 8) |
| Sticky ATC bar on mobile scroll | ✅ CSS handles `position: sticky` on `.product-form__submit` | |

---

### 1.6 Cart

| Check | Status | Notes |
|---|---|---|
| Slide-out drawer cart | ✅ `cart_type: "drawer"` | |
| Free shipping progress bar | ❌ NOT PRESENT | Must add Liquid to snippets/cart-drawer.liquid |
| Trust badges in cart | ❌ NOT PRESENT | Must add HTML to snippets/cart-drawer.liquid |
| Cross-sell/upsell block | ❌ NOT PRESENT | Requires app (Rebuy, frequently bought) |

---

### 1.7 Footer

| Check | Status | Notes |
|---|---|---|
| Multi-column layout | ✅ Dawn footer default | |
| Social icons | ❌ All social links empty in settings | Fill in admin: Online Store → Themes → Customize → Theme Settings → Social media |
| Newsletter in footer | ✅ Dawn footer has newsletter by default | |
| Payment icons | ✅ Auto-populated by Shopify | |
| Copyright + legal links | ✅ Dawn default | |

---

### 1.8 CSS Status

All Phase 7 CSS overrides **are already present in assets/base.css**. This includes:
- Typography overrides (uppercase headings, banner headline size)
- Button styles (brand red, uppercase, bold)
- Product card hover lift
- Badge styles (sale red, NEW green)
- Transparent header support
- Quick add styles
- Trust badge layout
- Press logo grayscale
- Mobile responsive fixes
- Scrollbar styling

**Status: ✅ Complete — no CSS changes needed.**

---

### 1.9 Liquid Snippets Status

| Snippet | Status |
|---|---|
| NEW badge in card-product.liquid | ✅ Implemented (lines 129–132, 531–532) |
| Product count in collection banner | ❌ NOT YET ADDED |
| Trust badges in cart drawer | ❌ NOT YET ADDED |
| Free shipping progress bar in cart | ❌ NOT YET ADDED |
| Inventory urgency on PDP | ❌ NOT YET ADDED |

---

## PHASE 2 — REMAINING THEME SETTINGS CHANGES

Only one settings change is still needed — the heading font. Everything else in settings is already correct.

**Go to:** Online Store → Themes → Customize → Theme Settings → Typography

Change heading font from **Figtree** to one of:
- **Barlow Condensed** Bold 700 (best match to Casely)
- **Oswald** Bold 700
- **Antonio** Regular/Bold

Set Heading Scale to **140** (up from 125).

---

## PHASE 3 — HOMEPAGE FIXES NEEDED

All 10 sections are built. Only the brand story section needs content blocks added:

**Go to:** Customize → Home Page → Image with text section

Add these blocks in order:
1. **Block: Heading** → Text: `MADE FOR THE BOLD` → Size: H2
2. **Block: Text** → Your 2–3 sentence brand story paragraph

The button block (Our Story → /pages/about) is already there.

Also upload real images:
- Hero image (`hero-image.jpg` is a placeholder path)
- Brand story image (`brand-story.jpg` is a placeholder path)

---

## PHASE 4 — NAVIGATION BUILD

Currently `menu_type_desktop` is set to `"dropdown"`. **First, change to mega menu in Customize → Header.**

Then in **Online Store → Navigation → Main Menu**, build this structure:

```
Main Menu:
├── NEW ✨              /collections/new-arrivals
├── SHOP BY DEVICE      # (no link)
│   ├── iPhone 16 Series        /collections/iphone-16
│   ├── iPhone 15 Series        /collections/iphone-15
│   ├── Samsung Galaxy S24      /collections/samsung-s24
│   ├── Samsung Galaxy S23      /collections/samsung-s23
│   └── View All Devices        /collections/all
├── COLLECTIONS         # (no link)
│   ├── Best Sellers            /collections/best-sellers
│   ├── Trending Now            /collections/trending
│   └── Limited Edition         /collections/limited-edition
├── SALE 🔥             /collections/sale
└── ABOUT               /pages/about
```

The SALE item will automatically turn red via the existing CSS rule:
```css
.header__menu-item[href*="/collections/sale"] { color: #E8303A !important; }
```

---

## PHASE 8 — LIQUID SNIPPETS (REMAINING)

### 8.1 Add product count to collection banner
**File:** `sections/main-collection-banner.liquid`

Find the title output line (search for `collection.title`) and add immediately after the closing tag:

```liquid
<p class="collection-hero__count">{{ collection.products_count }} Products</p>
```

The CSS for `.collection-hero__count` is already in base.css. No CSS change needed.

---

### 8.2 Add trust badges + free shipping bar to cart drawer
**File:** `snippets/cart-drawer.liquid`

Search for the checkout button — look for `class="cart__checkout-button button"` or `name="checkout"` (around line 568). Add the following block ABOVE the checkout button:

```liquid
{% comment %} Free Shipping Progress Bar {% endcomment %}
{% assign free_shipping_threshold = 3500 %}
{% assign remaining = free_shipping_threshold | minus: cart.total_price %}
{% if remaining > 0 %}
  <div class="free-shipping-bar">
    <p>You're <strong>{{ remaining | money }}</strong> away from <strong>FREE SHIPPING</strong> 🚚</p>
    <div class="free-shipping-bar__track">
      <div class="free-shipping-bar__fill"
           style="width:{{ cart.total_price | times: 100 | divided_by: free_shipping_threshold | at_most: 100 }}%">
      </div>
    </div>
  </div>
{% else %}
  <p class="free-shipping-bar free-shipping-bar--achieved">🎉 You've unlocked FREE SHIPPING!</p>
{% endif %}

{% comment %} Cart Trust Badges {% endcomment %}
<div class="cart-trust-badges">
  <span>🔒 Secure Checkout</span>
  <span>🚚 Free $35+</span>
  <span>🔄 Easy Returns</span>
</div>
```

Add this CSS to the bottom of base.css (or Theme Settings → Custom CSS):

```css
/* --- FREE SHIPPING BAR (Cart Drawer) --- */
.free-shipping-bar {
  padding: 12px 16px;
  font-size: 13px;
  color: #444;
  line-height: 1.4;
}
.free-shipping-bar__track {
  background: #eee;
  border-radius: 100px;
  height: 6px;
  margin-top: 8px;
  overflow: hidden;
}
.free-shipping-bar__fill {
  background: #E8303A;
  height: 100%;
  border-radius: 100px;
  transition: width 0.4s ease;
  min-width: 4px;
}
.free-shipping-bar--achieved {
  color: #1a8c4e;
  font-weight: 700;
  text-align: center;
  padding: 12px 16px;
}

/* --- CART TRUST BADGES --- */
.cart-trust-badges {
  display: flex;
  gap: 16px;
  justify-content: center;
  padding: 12px 0;
  font-size: 12px;
  color: #666;
  border-top: 1px solid #eee;
  margin-top: 12px;
  flex-wrap: wrap;
}
```

---

### 8.3 Add inventory urgency to product page
**File:** `sections/main-product.liquid`

Find where the quantity selector or buy button block renders. Search for `{% when 'buy_buttons' %}` or `{% when 'quantity_selector' %}`. Add this after the quantity block, before the buy buttons block:

```liquid
{% comment %} Inventory Urgency {% endcomment %}
{% if product.selected_or_first_available_variant.inventory_management == 'shopify'
   and product.selected_or_first_available_variant.inventory_quantity <= 5
   and product.selected_or_first_available_variant.inventory_quantity > 0 %}
  <p class="inventory-warning">
    ⚠️ Only {{ product.selected_or_first_available_variant.inventory_quantity }} left in stock!
  </p>
{% endif %}
```

Add to base.css:
```css
.inventory-warning {
  color: #E8303A;
  font-size: 13px;
  font-weight: 600;
  margin: 8px 0;
  animation: pulse 1.5s ease-in-out infinite;
}
@keyframes pulse {
  0%, 100% { opacity: 1; }
  50% { opacity: 0.7; }
}
```

**Note:** This requires inventory tracking to be enabled per-product in Shopify admin. If you use "Don't track inventory," this won't display.

---

## PHASE 9 — CONVERSION FEATURES STATUS

| Feature | Status | Action |
|---|---|---|
| Free shipping bar in cart | ❌ | Add Liquid above (Phase 8.2) |
| Inventory urgency on PDP | ❌ | Add Liquid above (Phase 8.3) |
| Reviews app (Judge.me) | ❌ | Install free from Shopify App Store |
| Exit intent popup | ❌ | Install Privy (free tier) or Klaviyo |
| Announcement countdown | ⚠️ | Marquee ticker present but no countdown |
| Apple Pay / Google Pay | ✅ | `show_dynamic_checkout: true` renders these automatically |

---

## PHASE 10 — MOBILE QA CHECKLIST

Test each on iPhone Safari (375px) after publishing to a theme duplicate:

- [ ] Hero headline legible, not cut off (CSS uses `clamp(2rem, 8vw, 3rem)` — should be fine)
- [ ] Both hero CTA buttons visible in viewport
- [ ] Hamburger menu opens smooth full-screen overlay
- [ ] Product cards render 2-up (CSS rule `grid--2-col-tablet-down` applied)
- [ ] Product images full-width, swipe works
- [ ] ATC button sticky at bottom on PDP scroll (CSS `position: sticky; bottom: 0` applied)
- [ ] Cart drawer slides from right, doesn't push page
- [ ] Marquee ticker readable at mobile size
- [ ] Font sizes: nothing below 14px — verify headings don't go tiny
- [ ] Tap targets: all buttons 44x44px minimum

---

## PHASE 11 — SEO & PERFORMANCE

| Item | Status | Action |
|---|---|---|
| Homepage `<title>` | ❓ | Set in Online Store → Preferences → Title |
| Homepage meta description | ❓ | Same location |
| Product image alt text | ❓ | Set when uploading images (Files section) |
| Collection descriptions | ❓ | Add in each Collection's "Description" field |
| Sitemap to Google Search Console | ❓ | Submit `yourdomain.com/sitemap.xml` |
| Image formats (WebP) | ⚠️ | Shopify auto-converts to WebP on delivery — upload high quality JPG/PNG |
| Image compression before upload | ⚠️ | Use Squoosh.app before uploading |
| Lazy loading | ✅ | Dawn handles this natively |
| Unused apps | ⚠️ | Audit installed apps, remove anything unused |

---

## "WON'T WORK IN TASTE" FLAGS

These Casely patterns require a paid app or theme upgrade — Taste/Dawn cannot do them natively:

| Feature | Limitation | Best Free Solution |
|---|---|---|
| **Color swatch images on cards** | Taste shows pill text buttons, not image-based color swatches | Swatch King app (paid) or manual swatch images via metafields |
| **Slide-in cross-sell in cart** | No native upsell widget in cart drawer | Rebuy (paid) or AfterSell |
| **Sticky "Add to Cart" bar** (separate persistent bar, not just the button sticking) | CSS `position: sticky` on the form button works, but a dedicated floating bar with variant name + image requires JS | Sticky ATC - Selling Point app |
| **Countdown timer in announcements** | Taste announcement bar has no timer widget | Hurrify app or custom JS |
| **"Complete the look" on PDP** | No native outfit builder | Frequently Bought Together app |
| **SMS opt-in in popup** | Privy free tier is email-only | Klaviyo (free up to 250 contacts) |
| **Mega menu with images** | Taste mega menu is text links only (no product/image cards in dropdown) | Needs theme upgrade or custom Liquid in `snippets/header-mega-menu.liquid` |

---

## COMPLETE ADDITIONAL CSS BLOCK

Add the following to the bottom of `assets/base.css` (the free shipping bar and urgency CSS not yet in your file):

```css
/* --- FREE SHIPPING BAR (Cart Drawer) --- */
.free-shipping-bar {
  padding: 12px 16px;
  font-size: 13px;
  color: #444;
  line-height: 1.4;
}
.free-shipping-bar__track {
  background: #eee;
  border-radius: 100px;
  height: 6px;
  margin-top: 8px;
  overflow: hidden;
}
.free-shipping-bar__fill {
  background: #E8303A;
  height: 100%;
  border-radius: 100px;
  transition: width 0.4s ease;
  min-width: 4px;
}
.free-shipping-bar--achieved {
  color: #1a8c4e;
  font-weight: 700;
  text-align: center;
  padding: 12px 16px;
}
.cart-trust-badges {
  display: flex;
  gap: 16px;
  justify-content: center;
  padding: 12px 0;
  font-size: 12px;
  color: #666;
  border-top: 1px solid #eee;
  margin-top: 12px;
  flex-wrap: wrap;
}

/* --- INVENTORY URGENCY (PDP) --- */
.inventory-warning {
  color: #E8303A;
  font-size: 13px;
  font-weight: 600;
  margin: 8px 0;
  animation: pulse 1.5s ease-in-out infinite;
}
@keyframes pulse {
  0%, 100% { opacity: 1; }
  50% { opacity: 0.7; }
}

/* --- VARIANT PILLS SHAPE OVERRIDE --- */
/* Make variant pills slightly more rectangular (Casely uses rectangular pill) */
.swatch-input__input + .swatch__label--pill {
  border-radius: 4px !important;
}
```

---

## SUMMARY SCORECARD

| Phase | Status |
|---|---|
| Theme color schemes (3 schemes) | ✅ Complete |
| Typography — body font | ✅ Complete |
| **Typography — heading font** | **❌ Fix required (Figtree → Barlow Condensed/Oswald)** |
| Layout settings | ✅ Complete |
| Homepage sections (10 sections) | ✅ Built — brand story needs content blocks |
| **Header: transparent on homepage** | **❌ Must enable in Customize** |
| **Header: mega menu** | **❌ Must switch from dropdown to mega** |
| Navigation structure | ⚠️ Needs to be built in admin |
| Collection page settings | ✅ Complete |
| Product page blocks | ✅ Complete |
| Custom CSS (base.css) | ✅ Complete |
| NEW badge Liquid | ✅ Complete |
| **Cart trust badges** | **❌ Liquid needs to be added** |
| **Free shipping progress bar** | **❌ Liquid needs to be added** |
| Inventory urgency Liquid | ❌ Not added |
| Collection banner product count | ❌ Not added |
| Social links | ❌ All empty |
| Real images (hero, brand story) | ❌ Placeholders only |

**Overall completion: ~70%** — The hard foundation (all CSS, color schemes, section structure, PDP blocks) is solid. The remaining 30% is mostly admin configuration (font, header settings, nav build) and 3 Liquid snippets (cart drawer, PDP urgency, collection count).
