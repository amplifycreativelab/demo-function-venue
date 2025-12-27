Demo 4 — Function Venue (Weddings & Corporate)
“Function Venue”
Objective

Build a high-intent, enquiry-driven venue website demo targeting weddings, corporate functions, and private events.
Primary KPI: qualified enquiry submissions (venue viewings, availability checks).
Secondary KPI: package exploration + gallery engagement.

This demo should feel premium, calm, and trustworthy, suitable for venues charging mid-to-high range pricing.

1. Brand & Visual Direction
Tone

Elegant, calm, refined

No loud animations or aggressive CTAs

Focus on space, light, and clarity

Color System

Background: Soft off-white / ivory (#FAFAF8 or similar)

Primary accent: Warm champagne / sand (#D8CFC4)

Secondary accent: Muted sage or stone (#9FA8A3)

Text: Charcoal (#2B2B2B), never pure black

Dividers: Subtle 1px lines with opacity (rgba)

Typography

Headings: High-end serif
Examples: Playfair Display, Cormorant Garamond, Canela-style

Body: Clean modern sans
Examples: Inter, Source Sans 3, Helvetica-like

Buttons: Uppercase, slightly tracked

Layout Rules

Max content width: 1200–1280px

Large vertical spacing (padding-block ≥ 96px on desktop)

Imagery dominates above the fold

Rounded corners subtle (6–12px max)

No shadows unless extremely soft

2. Site Architecture
Pages
/                 → Home (conversion overview)
/packages/        → Clear pricing + inclusions
/weddings/        → Wedding-specific landing
/corporate/       → Corporate & business events
/contact/         → Core enquiry page (most important)


Each page must include:

Persistent “Check Availability” CTA

Footer with contact details + service areas

Schema-friendly HTML structure (semantic sections)

3. Home Page Structure
1. Hero Section

Full-width image or video placeholder

Overlay headline:

“An elegant function venue for weddings & corporate events”

Subheading:

Capacity range + location mention

Primary CTA: Book a Viewing

Secondary CTA: View Packages

2. Packages Preview

3 premium package cards:

Wedding Package

Corporate Package

Private Events Package

Each card:

Starting price

Guest capacity

3–4 inclusions

CTA → /packages/

3. Capacity & Inclusions

Two-column layout:

Left: capacity tiers (seated / cocktail)

Right: inclusions list (AV, catering, parking, accessibility)

4. Gallery Preview

Masonry or editorial grid

Focus on:

Ceremony setups

Table styling

Corporate layouts

CTA: “View full gallery” (optional modal)

5. Testimonials

3–4 quotes

Wedding + corporate mix

Name + event type

6. FAQ Preview

4–5 accordion items

Link to full FAQ section on contact page

7. Areas Served

Short paragraph mentioning:

Perth metro

Cottesloe

Fremantle

Swan Valley

4. Packages Page (/packages/)
Structure

Intro explaining transparent pricing

3 detailed package sections

Each Package Includes

Ideal event type

Price range (avoid exact pricing if desired)

Guest capacity

What’s included

Optional add-ons

CTA: “Check availability for this package”

Use PackageCard.astro components fed by packages.json.

5. Weddings Landing (/weddings/)
Goal

Speak emotionally to couples while reinforcing logistics.

Sections

Romantic hero image

Ceremony + reception layouts

Wedding package highlights

Sample timeline

Testimonials (weddings only)

CTA block:

“Book a wedding viewing”

6. Corporate Landing (/corporate/)
Goal

Appeal to planners, HR, and agencies.

Sections

Clean, professional hero

Event types:

Conferences

Product launches

Team dinners

AV & presentation capabilities

Corporate package highlights

CTA:

“Request corporate availability”

7. Contact & Enquiry Page (/contact/)
Core Conversion Page
Enquiry Form Fields

Full name

Email

Phone

Event type (select)

Preferred date

Guest count

Budget range (select)

Message

UX Rules

Clear labels (no placeholders only)

Required fields clearly marked

Success state message

Spam-safe (honeypot or hidden field)

Supporting Content

Venue address

Contact details

Map placeholder

Operating hours

Response time reassurance

8. Components (Astro)

Required reusable components:

HeroVenue.astro
PackageCard.astro
GalleryGrid.astro
TestimonialCard.astro
FAQAccordion.astro
AvailabilityCTA.astro
VenueEnquiryForm.astro

9. Data Models
packages.json
[
  {
    "slug": "wedding",
    "title": "Wedding Package",
    "capacity": "Up to 150 guests",
    "priceFrom": "$",
    "inclusions": []
  }
]

testimonials.json
[
  {
    "name": "Emily & James",
    "event": "Wedding",
    "quote": "..."
  }
]

10. SEO & GEO Strategy
Schema

Use EventVenue OR LocalBusiness

Include:

Name

Address

Capacity

Event types

Service area

SameAs placeholders

On-Page Keywords

“Perth function venue”

“Wedding venue Perth”

“Corporate event venue Perth”

“Private function venue near Fremantle”

Local Signals

Suburb mentions naturally in copy

Footer service area list

Geo-specific testimonials

11. Performance & Accessibility

Lighthouse target: 95+

Images:

Lazy-loaded below the fold

Aspect-ratio locked

Contrast AA minimum

Keyboard-accessible form

No blocking JS

12. Demo Positioning (for your portfolio)

This demo represents:

High-value venues

Hotels, wineries, estates

Clients with longer decision cycles

Enquiry-focused UX (not ordering)