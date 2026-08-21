# TNO Painting & Handyman Services — demo site

Single-page demo built for **TNO Painting & Handyman Services**, a painting and handyman company serving Winter Haven, FL and the surrounding Polk County area.

- **Live:** https://wilsoninnovations.net/tno-painting-handyman/
- **Repo:** wilsonramstead/tno-painting-handyman (GitHub Pages, `main` / root)
- **Built:** 2026-08-22 (wave 73, manifest index 8)
- **Status:** demo / unpitched — `<meta name="robots" content="noindex">` is in place with a removal comment above it. Remove that line when the site goes live.

## Business facts (provenance)

All business facts come from the wave 73 manifest entry (`wave73_manifest.json`, index 8), sourced from the business's Google Business Profile via the Google Places API. The listing was re-confirmed live through the Places API during this build (place `ChIJ90R7LUVH3YgRL27AA7c6fQk`, `businessStatus: OPERATIONAL`). Nothing on the page is invented.

| Field | Value |
| --- | --- |
| Business | TNO Painting & Handyman Services (GBP display name: "TNO Painting and Handyman services LLC") |
| Category | Painting & handyman services (Places `primaryType: general_contractor`) |
| Phone | (267) 726-1015 — matched against the manifest; `tel:+12677261015` / `sms:+12677261015` |
| Locality | Winter Haven, FL (Polk County) |
| Rating | 4.7 |
| Reviews | 39 |
| Hours | Mon–Sat 9:00 AM – 7:30 PM, closed Sunday |
| Website | None (no existing site) |
| Owner | **Not named on the site** — see the naming note below |

### Phone note

The number is a **267 (Philadelphia) area code**, which is the number on the GBP listing and is presumably a transplant's cell. It is used exactly as listed and is **not** localized or substituted anywhere. Their own GBP photos were checked for painted-on phone numbers or vehicle lettering carrying a different number — there are none, so nothing conflicts with (267) 726-1015.

### Naming ambiguity — CALL ITEM

Two different names appear in the reviews and it is **not established that they are the same person**:

- Henreta J.: *"**Mr. Bucknor** is very patient, trustworthy, professional…"*
- SimplyRhonda: *"**Shane** came out the same day I called…"*
- KR M.: *"**Shane** did my tile in the kitchen…"*

They may well be one man (Shane Bucknor), but the API surfaces no evidence of that, and the manifest carries `owner_name: null`. **Nobody was promoted to owner on the site.** Both names appear **only inside verbatim review quotes**; there is no owner-personality section, no "Meet Shane", no bio, and no name in any headline, service copy, footer or JSON-LD. **Confirm the correct name (and whether Shane and Mr. Bucknor are the same person) on the call**, then it can be added.

### Address privacy

The GBP address (445 Kensington View Dr, Winter Haven) is a **residential street address**. Per the manifest's residential directive, the site publishes **no street address anywhere**:

- No street address in any visible copy, header, footer or contact block.
- JSON-LD `PostalAddress` is **locality-only** — `addressLocality` / `addressRegion` / `addressCountry`, with **no `streetAddress`** and no postal code.
- **No map embed** of any kind.
- Location is framed purely as a **service area**: Winter Haven, Lakeland, Auburndale, Bartow, Haines City, Eagle Lake, Lake Alfred and the wider Polk County area.

### SCOPE GUARD (Florida licensing) — important

The GBP reviews contain a same-day roof-patch rescue (SimplyRhonda: missing shingles replaced) and two mentions of outlets/sockets. **These are stories, not services.**

- The roof story is carried **only as a verbatim customer quote** in the reviews grid, under the neutral heading "Answered when nobody else would" — the heading is about responsiveness, not roofing.
- The site **does not market roofing, electrical or plumbing work anywhere**. There is no roofing/shingle/electrical/plumbing service card, list item, headline, meta description, or JSON-LD `Service` entry. A grep of the page for `roof|shingle|electric|plumb|outlet|socket|licens` returns hits **only inside the two verbatim review blockquotes**.
- No license or "licensed and insured" claim is made anywhere, since none was evidenced.

**Marketed scope** (all evidenced by reviews and/or their own photos): interior painting; exterior painting; tile and shower rebuilds; bathrooms and room refreshes; flooring and drywall; and a punch-list card covering blinds, door weather stripping, vent hoods, hardware, TV mounting and shelving. Shower/bath work is described as tile, surrounds, pans, vanities and trim — never as plumbing.

### Rating display

4.7 is used freely with the review count beside it (hero chip: "4.7 from 39 Google reviews"; stat strip: 4.7 / 39). The hero star row renders **four filled stars plus a fifth filled to 70%** — it is **never** shown as five solid stars. Individual review cards carry no star row.

### Hours

Google posts **Mon–Sat 9:00 AM – 7:30 PM, closed Sunday**. Per the manifest these are presented **plainly**, exactly as listed, in the Hours card and footer, plus a softening line noting that calls and texts are welcome inside those hours. No availability is promised beyond what Google publishes, and no same-day or emergency claim is made.

### Reviews

All five Google reviews the API returns were used, quoted **verbatim** with **first name + last initial** and **no dates**:

- **Henreta J.** — the full-width feature quote and the lead angle: patient, trustworthy, professional; *"I am very picky, but TNO understood the assignment… brought my vision to life"*; dream bathroom, primary bedroom and new office space.
- **Michelle C.** — the list-clearing angle: blinds, lighting fixtures, door weather stripping, vent hood and outlets in one go; family asked for the number.
- **SimplyRhonda** — the same-day rescue (see the scope guard above). Google display name is a single handle with no surname, so it is shown as written.
- **Larry C.** — shower completely rebuilt, fast and professional.
- **KR M.** — kitchen tile; punctual, kind, clean, tidy and courteous; open communication; a reasonable quote up front. The quote is a **contiguous span from the beginning** of the review, trimmed only from the end — never spliced.

The "How the work goes" section paraphrases the four traits that recur across those reviews (quote up front, quick to show up, clean and tidy, open communication) in plain prose — no fabricated quote cards.

The aggregate figures (4.7 / 39 / 6 days a week / Polk County) are plain **stat tiles, deliberately not styled as quotes**.

**Review layout:** per Wilson's doctrine the review cards are **wide** — a 2-column grid at ≥900 px (verified in-browser: `grid-template-columns: 549px 549px` at 1440 px), collapsing to a single column at 390 px (`346px`). No 3-column skinny towers.

## Images

**Every image on the site is the business's own**, pulled from their Google Business Profile via the Places API photo-media endpoint (all 10 GBP photos are attributed to "TNO Painting and Handyman services LLC"). **Zero stock photography is used** — no Unsplash, no third-party imagery — so there is no cross-site image collision surface at all. Images are self-hosted under `img/`, re-encoded with PIL to ≤350 KB each, and every one was visually inspected and matched to its alt text.

| File | Subject |
| --- | --- |
| `hero-exterior-repaint.jpg` | Two-story home, exterior repaint with navy garage door and shutters (also the og:image) |
| `work-accent-wall-living-room.jpg` | Navy accent wall, paneling, white slat TV surround |
| `work-bathroom-remodel.jpg` | Finished bathroom — tile tub surround, wainscoting, vanity |
| `work-feature-wall-layout.jpg` | Custom geometric feature wall taped out before paint |
| `work-shower-rebuild.jpg` | Shower rebuilt to cement board, ready for tile |
| `work-flooring-install.jpg` | Plank flooring going in over the old hardwood |
| `work-entry-walkway-painted.jpg` | Entry and stucco repainted, walkway |
| `work-drywall-repair.jpg` | New drywall hung and taped |
| `work-exterior-door.jpg` | Exterior door and surround painted |
| `work-garage-door-fascia.jpg` | Garage door and fascia in matching brown |

**Privacy pass:** the hero photo had a **house number plate (visible above the garage light) blurred out** before publishing, so the address is not recoverable from the imagery. The remaining photos were checked for license plates, house numbers and other identifying detail — none present.

## Design

- **Tier 1 — Clean Slate** (per DESIGN.md): bright, trustworthy, elevated with type, motion and depth. No aurora/glow system.
- **Palette:** warm white `#FAF7F3` + charcoal-plum `#2B2330` / `#1D1722` with a goldenrod accent `#BF8916` / `#E3AE3A`. Deliberately distinct from the painter and handyman siblings — no coral/peach (sunrise-quality-painting), no cobalt or ultramarine (protech-painting, charles-handyman), no navy/tool-yellow (sf-handyman-services), no terracotta (jl-painters), no olive (lazaros-painting), no sage (bennett-home-painting).
- **Fonts:** Caladea (display) + Inter (body) — the pair assigned in the manifest.
- **Motion:** one-shot IntersectionObserver reveals with a +12% bottom `rootMargin`, staggered grid delays, a slow Ken Burns settle on the hero, plus a momentum-scroll safety sweep. All motion is gated behind `prefers-reduced-motion`.
- **JS-off safe:** reveal styles are scoped to a `.js` class that the script adds to `<html>`, so with JavaScript disabled the full page renders visible and unanimated.
- **Mobile standard:** header call CTA flush right at every width, icon-only ≤600 px, brand name wraps to 2 lines without clipping, H1 is 2 lines at 390 px, tap targets ≥44 px. **No fixed bottom call bar.**
- **Verified:** puppeteer-core + Edge at true 390 px and 1440 px full pages, plus 1440×900 and 1366×768 no-scroll fold shots — the whole hero stack (eyebrow → headline → sub → CTA pair → trust chip) sits above the fold at both desktop sizes. `scrollWidth === clientWidth` at both widths: **zero horizontal overflow**.

## Meta

- `noindex` + demo removal comment.
- Absolute `og:`/`twitter:` URLs at `https://wilsoninnovations.net/tno-painting-handyman/`, `og:image` pointing at the hero exterior repaint.
- JSON-LD `HomeAndConstructionBusiness` — locality-only address (no `streetAddress`), `areaServed` city list, `aggregateRating` 4.7/39, `openingHoursSpecification` Mon–Sat 09:00–19:30, and `makesOffer` limited to the marketed scope.
- No contact form. Contact is call/text only.
- Exactly one footer credit: "Website by Wilson Innovations" → https://wilsoninnovations.net.
