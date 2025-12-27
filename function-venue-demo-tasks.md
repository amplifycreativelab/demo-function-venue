# Development Tasks - Demo 4 (Function Venue)

Source docs:

- `docs/global prompt.md`
- `function venue/function-venue-demo.md`

How to use:

- Mark items complete by changing `- [ ]` to `- [x]`.
- Work top-to-bottom; sections later in the file may depend on earlier setup tasks.

## Phase 0 - Project Decisions

- [x] Confirm GitHub Pages repo name for Astro `base` (must be `"/<repo>/"`).
- [x] Choose styling approach: Tailwind OR CSS modules + tokens (pick one and stick to it).
- [x] Choose fonts (max 2): high-end serif headings + clean sans body (buttons uppercase, slightly tracked).
- [x] Confirm venue placeholders (name, phone, address area in Perth WA, capacity range, hours).
- [x] Confirm service areas copy: Perth metro, Cottesloe, Fremantle, Swan Valley.
- [x] Confirm pricing approach: starting-from vs ranges vs enquiry-only (no exact pricing).
- [x] Confirm conversion CTA copy used site-wide: "Check Availability" (persistent on every page).
- [x] Confirm primary CTAs per page: "Book a Viewing", "View Packages".

## Phase 1 - Astro Setup (Static + GitHub Pages)

- [x] Create a new Astro project (static output).
- [x] Configure `astro.config.mjs` with `site: "https://github.com/amplifycreativelab"` and `base: "/<repo>/"`.
- [x] Ensure all internal links and asset URLs work under the base path (no hard-coded absolute `/` paths).
- [x] Add/verify npm scripts: `dev`, `build`, `preview`.
- [x] Add `src/assets/images/` placeholder images (hero, packages, weddings, corporate, gallery, OG image).
- [x] Add a hero video placeholder strategy (no autoplay sound; provide image fallback).

## Phase 2 - Design System (Elegant / Calm / Premium)

- [x] Define color palette:
  - [x] Background: soft off-white / ivory (e.g. `#FAFAF8`)
  - [x] Primary accent: warm champagne / sand (e.g. `#D8CFC4`)
  - [x] Secondary accent: muted sage / stone (e.g. `#9FA8A3`)
  - [x] Text: charcoal (e.g. `#2B2B2B`, never pure black)
  - [x] Dividers: subtle 1px lines using rgba opacity
- [x] Define spacing scale (4/8/12/16/24/32/48/64).
- [x] Define typography scale (serif headings, sans body; clear hierarchy).
- [x] Define layout rules: max width 1200-1280px; large vertical spacing (desktop padding-block ~96px); subtle radii (6-12px); avoid shadows (or extremely soft only).
- [x] Implement focus-visible styles for links/buttons/inputs.
- [x] Implement reduced motion support (`prefers-reduced-motion`).

If using Tailwind:

- [ ] Install/configure Tailwind for Astro.
- [ ] Add Tailwind theme tokens (colors, font families, spacing, radii, shadows).

If using CSS modules + tokens:

- [x] Create `src/styles/tokens.css` (colors, font families, spacing, radii, shadows).
- [x] Create base/global styles (typography defaults, container widths, utilities).

## Phase 3 - Core Layout & Shared Components

- [x] Create `src/layouts/BaseLayout.astro` with:
  - [x] Skip link
  - [x] Header/nav (Home, Packages, Weddings, Corporate, Contact)
  - [x] Persistent `AvailabilityCTA` ("Check Availability") visible on every page
  - [x] Footer with contact details + service areas list
  - [x] Title/meta slots
  - [x] OG/Twitter meta placeholders
- [x] Build design-system components (reused across pages):
  - [x] `Button` (primary/secondary + focus states; uppercase labels)
  - [x] `Card` (via PackageCard/ServiceCard)
  - [x] `SectionHeader` (inline styles or utility)
  - [x] `FormInput` / `Textarea` (label + help/error text pattern)
- [x] Build required demo components (Astro):
  - [x] `HeroVenue.astro`
  - [x] `AvailabilityCTA.astro`
  - [x] `PackageCard.astro`
  - [x] `GalleryGrid.astro`
  - [x] `TestimonialCard.astro`
  - [x] `FAQAccordion.astro`
  - [x] `VenueEnquiryForm.astro`

## Phase 4 - Content & Data Layer

- [x] Create `src/data/packages.json` (Wedding / Corporate / Private Events) with:
  - [x] `slug`, `title`, `capacity`, `priceFrom` or `priceRange`, `inclusions`, `addOns` (optional)
- [x] Create `src/data/testimonials.json` (wedding + corporate mix) with:
  - [x] `name`, `event`, `quote`
- [x] Create FAQ content (either `src/data/faqs.json` or inline where needed).
- [x] Add venue NAP content used site-wide (footer + contact + schema).
- [x] Add operating hours and response-time reassurance copy (e.g., “We respond within 1 business day.”).

## Phase 5 - Pages (Demo IA + Required Pages)

### Home (`src/pages/index.astro`)

- [x] Hero: full-width image/video placeholder + headline + subheading (capacity range + Perth location mention).
- [x] CTAs: primary "Book a Viewing" + secondary "View Packages" (+ persistent "Check Availability").
- [x] Packages preview: 3 premium package cards (Wedding/Corporate/Private Events) with:
  - [x] Starting price or price range
  - [x] Guest capacity
  - [x] 3-4 inclusions
  - [x] CTA to `/packages/`
- [x] Capacity & inclusions section (two-column): capacity tiers + inclusions list (AV, catering, parking, accessibility).
- [x] Gallery preview section (masonry/editorial grid).
- [x] Testimonials section (3-4 quotes; wedding + corporate mix).
- [x] FAQ preview (4-5 accordion items) + link to full FAQ section on Contact page.
- [x] Areas served section with natural suburb mentions (Perth metro, Cottesloe, Fremantle, Swan Valley).

### Packages (`src/pages/packages/index.astro`)

- [x] Intro explaining transparent pricing.
- [x] Render 3 detailed package sections from `packages.json` using `PackageCard.astro`.
- [x] Each package includes: ideal event type, price range, guest capacity, inclusions, optional add-ons.
- [x] Per-package CTA: "Check availability for this package" (deep-link to contact with preselected package if desired).

### Weddings (`src/pages/weddings/index.astro`)

- [x] Romantic hero image + emotional copy with clear logistics.
- [x] Ceremony + reception layouts section.
- [x] Wedding package highlights (from `packages.json` where relevant).
- [x] Sample timeline section.
- [x] Testimonials (weddings only).
- [x] CTA block: "Book a wedding viewing" (+ persistent availability CTA).

### Corporate (`src/pages/corporate/index.astro`)

- [x] Clean, professional hero.
- [x] Event types section (conferences, product launches, team dinners).
- [x] AV & presentation capabilities section.
- [x] Corporate package highlights (from `packages.json` where relevant).
- [x] CTA: "Request corporate availability" (+ persistent availability CTA).

### Contact (`src/pages/contact/index.astro`) (CORE)

- [x] Enquiry form (`VenueEnquiryForm.astro`) with fields:
  - [x] Full name
  - [x] Email
  - [x] Phone
  - [x] Event type (select)
  - [x] Preferred date
  - [x] Guest count
  - [x] Budget range (select)
  - [x] Message
- [x] Form UX rules: clear labels (no placeholders-only), required fields marked, success state message.
- [x] Spam-safe: honeypot/hidden field.
- [x] Supporting content: address, contact details, map placeholder, operating hours, response time reassurance.
- [x] Full FAQ section (accordion) included on this page.

### Required pages from base prompt

- [x] About (`src/pages/about.astro`) - venue story, team, positioning (weddings + corporate).
- [x] Services (`src/pages/services.astro` or equivalent) - event types + planning support + add-ons.
- [x] Privacy (`src/pages/privacy.astro`) - simple legal page.
- [x] Local SEO/GEO page (choose one):
  - [x] Ensure Home + Footer include robust Perth-targeted content beyond a suburb list

## Phase 6 - SEO & GEO (Perth)

- [x] Page titles follow a consistent template (per-page + venue name).
- [x] Meta description per page (unique, enquiry-focused).
- [x] Canonical URLs set correctly (respecting `site` + `base`).
- [x] OpenGraph: title/description + placeholder OG image.
- [x] Twitter card meta.
- [x] Add JSON-LD schema (choose one primary):
  - [x] `EventVenue` OR `LocalBusiness` including name, address, capacity, event types, service area, `sameAs` placeholders
- [x] Add on-page keyword coverage naturally:
  - [x] "Perth function venue"
  - [x] "Wedding venue Perth"
  - [x] "Corporate event venue Perth"
  - [x] "Private function venue near Fremantle"
- [x] Add `robots.txt`.
- [x] Add sitemap (if straightforward) and verify it works with the configured `site`.
- [x] Internal linking: Home -> Packages -> Weddings/Corporate -> Contact (and back) with clear CTAs.

## Phase 7 - Accessibility & UX Checks

- [x] Contrast AA minimum.
- [x] One H1 per page; heading order is logical.
- [x] Skip link works and is visible on focus.
- [x] Keyboard navigation works across header, CTAs, accordion, and forms.
- [x] Touch targets are large enough for mobile.
- [x] Form is fully keyboard accessible with clear error messaging.

## Phase 8 - Performance

- [x] Target Lighthouse 95+ (mobile).
- [x] Use `astro:assets` for images where possible; responsive sizes + lazy loading below the fold.
- [x] Lock aspect ratios for media to prevent layout shift.
- [x] Avoid heavy JS; keep accordion behavior lightweight (or CSS-only where feasible).
- [x] No blocking JS.

## Phase 9 - Deployment & Handoff

- [x] Add build/run instructions (README or `/docs/`):
  - [x] `npm install`
  - [x] `npm run dev`
  - [x] `npm run build`
  - [x] `npm run preview`
- [x] Verify the built site works under the GitHub Pages base path (no broken links/assets).
- [x] Quick QA pass:
  - [x] Persistent "Check Availability" CTA on every page
  - [x] Packages data renders correctly
  - [x] Contact form labels + required markers + success state
  - [x] FAQ accordion keyboard support
  - [x] Basic SEO meta presence (view-source)

## Optional / Bonus

- [ ] Prefill contact form event type/package via query params (e.g., `?type=wedding&package=wedding`).
- [ ] Downloadable brochure CTA (PDF placeholder; keep it lightweight).
- [ ] Gallery modal/lightbox (optional; keep JS minimal).
