# Ridgetop Plumbing & Air: DEMO SITE

## What this is

A demo website for a **fictional** plumbing, heating and cooling company in Northern Kentucky. Kenneth Potter builds it to show local shop owners what a fast, call-focused website looks like. It's public proof on his LinkedIn, GitHub and Facebook.

Nothing on this site may look like a real business that someone could hire.

## Stack

- Astro with static output: no adapter, no SSR. Tailwind CSS. TypeScript.
- Hosting: Cloudflare Workers static assets through Workers Builds (`wrangler.jsonc`, assets in `./dist`). A push to `main` deploys.
- No UI frameworks (React, Vue and so on). Use vanilla JS only where it's needed (mobile menu, demo form), and keep it small.
- Ask before adding any dependency, analytics, cookies, trackers or third-party scripts.

## Business details (all fictional)

Put all of these in `src/data/business.ts`. Every page reads from that file, so swapping it out turns this into a starter for another site.

- **Name:** Ridgetop Plumbing & Air
- **Phone:** (859) 555-0142, `tel:+18595550142`. Use 555-01xx numbers only, since that range is reserved for fiction.
- **Email / address:** none shown. The request form is the contact path.
- **Hours:** Mon–Fri 7am–7pm, Sat 8am–2pm, plus a 24/7 emergency line
- **Service area:** Boone, Kenton and Campbell counties: Florence, Union, Burlington, Hebron, Independence, Erlanger, Covington, Fort Mitchell, Newport, Fort Thomas, Alexandria, Cold Spring
- **Services (4):** Furnace repair & replacement · AC repair & replacement · Water heaters (tank & tankless) · Drain cleaning & leak repair
- **Promises:** upfront price before work starts · same-day service when booked by noon · licensed & insured (demo) · financing available (demo)
- **Demo credit:** Kenneth Potter, workwithkenneth@pm.me, https://www.linkedin.com/in/kennethpotterco, https://github.com/kennethpotterco
- **Settings:** `demo.noindex: true` (see the demo rules below)

## Demo rules (non-negotiable)

1. **Banner on every page,** at the top, slim and readable: "DEMO SITE: Ridgetop Plumbing & Air is a fictional business. Website by Kenneth Potter." It links to `/demo`.
2. **Footer on every page:** "Fictional business for demonstration only. Not a real company. Please don't call or send personal info." Then "Demo site by Kenneth Potter" with the LinkedIn and GitHub links.
3. **Titles:** every `<title>` ends with " (Demo)".
4. **No indexing:** add `<meta name="robots" content="noindex, nofollow">` on every page, controlled by `demo.noindex`. Don't block crawlers in `robots.txt`, because LinkedIn and Facebook link previews have to be able to read the pages. No sitemap.
5. **Nothing that could pass as real:**
   - no street address, license numbers or badges (BBB, Angi, Google)
   - no manufacturer names or logos (Carrier, Trane, Rheem and so on)
   - no invented stats: years in business, jobs done, star ratings, review counts
6. **Reviews:**
   - at most 3 cards, each labeled "Sample review"
   - one note under them: "A real build shows the shop's actual Google reviews."
   - no reviewer names
7. **Request form:**
   - no backend, and nothing is sent or stored
   - on submit, validate the fields, then show "This is a demo form. Nothing was sent."
8. **People:** no photos of people presented as "our team", and no owner name.
9. **Schema:** JSON-LD (`Plumber` / `HVACBusiness`) built from `business.ts`, with a description saying it's a fictional demo business.

## Pages

- `/` **Home:**
  - hero with headline, call button and request button
  - emergency line visible above the fold
  - trust strip (the promises)
  - 4 service cards
  - "How it works": call → upfront price → fixed right
  - service-area teaser
  - sample reviews
  - closing call band
- `/services` plus `/services/[slug]` (4 pages, generated from `business.ts`). Each service page has:
  - common problems
  - what we do
  - an upfront-pricing note
  - 3 FAQs
  - call and request buttons
- `/service-area`: counties and towns, with a call to action
- `/about`: how the shop works and what it stands for. No owner persona.
- `/request-service`: the demo form (name, phone, ZIP, service, urgency, message)
- `/demo`, **"About this demo":** written for a shop owner. It covers:
  - what each feature does for them (more calls, mobile call bar, fast load, clear service area)
  - the stack
  - Lighthouse scores (placeholder until measured)
  - "Want one for your business?" with a link to contact Kenneth
- `404`, with the banner, footer and a call button

## Conversion features (the point of the demo)

- Phone number in the header on every page; tap-to-call on mobile.
- Sticky bottom bar on mobile with "Call now" and "Request service". It must not cover content.
- Every page ends with a call or request call to action.

## Design

- Clean and minimal with lots of white space. Kenneth's taste is the Apple and Netlify look.
- Colors: a deep navy for the brand and one warm accent (for example safety orange), used only for calls to action.
- Fonts: the system font stack or one self-hosted font. Icons are inline SVG, not an icon font.
- Mobile-first. Tap targets at least 44px. Body text at least 16px. WCAG AA contrast.
- Images:
  - Astro `<Image />` for optimization, with descriptive alt text
  - placeholders in `src/assets/` until Kenneth adds real ones
  - nothing that shows a real company's truck or logo

## Quality bar

- `npm run build` passes with no errors or warnings.
- Lighthouse on mobile: 95+ for Performance, Accessibility and Best Practices.
  - SEO flags `noindex`, and that's on purpose.
  - For a clean SEO number, set `demo.noindex: false` locally, run `npm run preview`, and measure there.
- Semantic HTML, one `h1` per page, a skip link, labeled form fields, and keyboard support throughout.

## How to work with Kenneth

- **Plan first.** Show the plan and wait for his OK before writing code.
- Make small commits with clear messages. Kenneth pushes.
- Never put secrets, keys or personal info in the repo.
- After each task, say how to check it: which path to open and what to look for.
