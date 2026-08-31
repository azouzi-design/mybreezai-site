# Breez AI → EVERYAISLE: content NOT yet changed, for marketing/legal review

Scope note: I replaced "Breez"/"Breez AI"/"Breez AI Corporation" with "EVERYAISLE" everywhere in
the visible site copy and renamed the logo asset files — EXCEPT the categories below, which are
listed here rather than changed, per your instructions. (Brand spelling history: first pass used
"Everyaisle"/lowercase-a, corrected to "EveryAisle"/capital-A to match the product page's existing
casing, then per brand instruction changed again to all-caps "EVERYAISLE" — the current and final
spelling, applied site-wide including the asset filenames.)

---

## 1. Legal pages — /terms and /privacy (untouched, needs brand-owner review)

Both pages still read "Breez AI" / "Breez AI Corporation" throughout — nothing was touched here.

- **`/terms/index.html`** — ~90 instances. Defines the legal entity as "Breez AI Corporation
  ('Breez AI,' ...)" in section 1, then uses "Breez AI" as the contracting party name through
  every clause: liability, arbitration, IP ownership, disclaimers, notices. Company mailing
  address block at the bottom: "Breez AI Corporation".
- **`/privacy/index.html`** — ~100 instances, same pattern. Defines "Breez AI Corporation" as
  data controller in section 1, then "Breez AI" throughout data-collection, use, and disclosure
  sections. Company address block: "Breez AI Corporation, 9225 Bay Plaza Blvd, Suite 417 (1173),
  Tampa, FL 33619".

These need an actual entity-name decision from whoever owns the legal docs (is "Breez AI
Corporation" becoming "EVERYAISLE Corporation" / "EVERYAISLE, Inc." / something else — that's a
real legal filing, not just a find-and-replace), so I left them exactly as-is.

**Checked specifically for "GroceryAisle" too**: zero mentions of "GroceryAisle" or "EVERYAISLE"
anywhere in either legal page. The product-name rename doesn't touch `/terms` or `/privacy` at
all — nothing pending there on that front.

---

## 2. Page `<title>` tags, meta tags, JSON-LD, and other machine-facing metadata (untouched everywhere, incl. /terms and /privacy)

These are the technical/SEO fields, not reader-facing paragraphs — flagging them separately since
they need coordinated updates (new OG image, new JSON-LD logo asset, etc.) rather than a plain
text swap.

**`<title>` tags** (one per page, all currently end in "| Breez AI"):
- `error.html` → `Page Not Found | Breez AI`
- `index.html` / `home/index.html` → `Breez AI | Personalized Grocery. Powered by AI.`
- `whybreez/index.html` → `Why Breez | Breez AI`
- `bookdemo/index.html` → `Book a Demo | Breez AI`
- `privacy/index.html` → `Privacy Policy | Breez AI`
- `terms/index.html` → `Terms & Conditions | Breez AI`
- `blog/index.html` / `blog/blog/index.html` → `News & Resources | Breez AI`
- `blog/post/index.html` / `blog/blog/post/index.html` → `Loading... | Breez AI Blog` (also set
  dynamically at runtime via `document.title = \`${post.title} | Breez AI Blog\``)
- `contactus/index.html` → `Contact Us | Breez AI`
- `dev-docs/index.html` → `Dev Docs | Breez AI`
- `smartmeals/index.html` → `SmartMeals | AI-Powered Meal Planning | Breez AI`
- `groceryaisle/index.html` → `EVERYAISLE | AI-Powered Grocery Platform | Breez AI` — the product
  name here is already correct ("EVERYAISLE"); only the trailing "| Breez AI" company tag needs
  updating
- `ourstory/index.html` → `Our Story | Breez AI`
- `design-md/index.html` → `Design MD | Breez AI`
- `ourteam/index.html` → `Our Team | Breez AI`

**OG / Twitter meta tags** (on `index.html` and `home/index.html`, identical on both):
- `og:title` = `Breez AI`
- `og:site_name` = `Breez AI`
- `twitter:title` = `Breez AI`
- `og:image` / `twitter:image` = `https://www.mybreezai.com/content/og/breez-og.jpg`
- Also present on `blog/post/index.html` and `blog/blog/post/index.html`: `og:site_name` = `Breez AI`

**JSON-LD structured data** (`index.html` and `home/index.html`, identical `Organization` block):
```
"name": "Breez AI",
"url": "https://www.mybreezai.com/",
"logo": "https://www.mybreezai.com/content/BreezAI_Logo_TransparentBG.png",
"image": "https://www.mybreezai.com/content/og/breez-og.jpg"
```

**Canonical URLs**: `<link rel="canonical" href="https://www.mybreezai.com/">` on `index.html` /
`home/index.html`.

**`favicon/site.webmanifest`**:
```
{"name":"Breez AI","short_name":"Breez AI", ...}
```

**Domain-dependent references** — these are live URLs/emails on the `mybreezai.com` domain and the
`breezai.app` subdomain; changing the visible text without owning the new domain would break the
link, so these are metadata-adjacent and left alone:
- `Legal@mybreezai.com` — appears as a mailto link in `/privacy` and `/terms` (2 places)
- `https://www.mybreezai.com` — referenced as a plain link in `/terms`
- `https://breezai.app` — external app link used as the "See It In Action" CTA target on
  `smartmeals/index.html`

**Social account links/handles** (left as-is site-wide — renaming the href without the account
itself being renamed would 404):
- LinkedIn: `https://www.linkedin.com/company/breez-ai` (footer, on every page; also
  `contactus/index.html`)
- Twitter/X: `https://x.com/MyBreezAI` (footer, on every page; also `contactus/index.html`)
- YouTube: `https://www.youtube.com/@mybreezai` (footer, on every page)

**Checked specifically for "GroceryAisle" too**: zero mentions anywhere in metadata — no
`<title>`, meta tag, JSON-LD field, canonical URL, or `site.webmanifest` entry says
"GroceryAisle." The `groceryaisle/index.html` page's own `<title>` and meta description already
say "EVERYAISLE," not "GroceryAisle" — that part of the metadata is already correct.

---

## 3. Visual assets — logo files renamed, but artwork itself is unchanged

I renamed the actively-referenced logo (`BreezAI-Horizontal-Subtext.svg` →
`EVERYAISLE-Horizontal-Subtext.svg`) and every unused orphan logo file in `/content` to
EVERYAISLE-branded filenames, and updated `alt`/`aria-label` text sitewide to say "EVERYAISLE."

**Important**: these are vector files with the "Breez AI" wordmark drawn as literal path shapes
(no editable `<text>` element) — I cannot regenerate real "EVERYAISLE" artwork. The renamed files,
and the inline animated splash-screen logo on the homepage (`index.html` / `home/index.html`,
the `.wordmark` SVG paths in the intro overlay), will still visually render the old "Breez AI"
lettering until design delivers new logo files. Drop-in replacements at these same filenames will
fix it without any further code changes:

- `/content/EVERYAISLE-Horizontal-Subtext.svg` (used in header, footer, SmartMeals — actively
  live on every page)
- `/content/EVERYAISLE-Logo-Animated.svg`, `EVERYAISLE-NoTag.png`, `EVERYAISLE-Tag.png`,
  `EVERYAISLELogo.svg`, `EVERYAISLEWebLogo.png`, `EVERYAISLE-emails.png`, `EVERYAISLE-logo.png`,
  `EVERYAISLELogo.png` (currently unused/orphaned in the codebase, renamed for consistency — the
  last one, `EVERYAISLELogo.png`, is the pre-existing hero-logo asset noted below, also renamed to
  match once the all-caps instruction came in)
- Inline animated wordmark SVG in the homepage intro overlay (not a separate file — lives directly
  in `index.html` / `home/index.html`)

**Left un-renamed** (only referenced from the metadata block in section 2 above, so renaming now
would break that reference before marketing updates it):
- `/content/BreezAI_Logo_TransparentBG.png` — only used in the JSON-LD `logo` field
- `/content/og/breez-og.jpg` and `/content/og/breez-og.webp` — only used in OG/Twitter image meta
  and the JSON-LD `image` field

Once you have real EVERYAISLE logo artwork and updated metadata values, these three should be
renamed and swapped together.

**Pre-existing asset, unrelated to this rebrand**: `/content/EVERYAISLELogo.png` already existed
in the codebase before this work started (used as the hero logo on `groceryaisle/index.html`) and
was already correctly spelled "EveryAisle" — only its casing was updated, to `EVERYAISLELogo.png`,
to match the all-caps brand instruction.

---

## 4. Product name — "GroceryAisle" → "EVERYAISLE"

Separate from the Breez AI → EVERYAISLE company rebrand: the product itself is mid-rename from
"GroceryAisle" to "EVERYAISLE" (they're the same product; "EVERYAISLE" is simply the corrected
name). Confirmed **no legal or metadata footprint** for this one — see the "Checked specifically
for GroceryAisle" notes in sections 1 and 2 above. This is a pure visible-copy /
image-alt-text cleanup, nothing more.

**Already updated** (on `/whybreez`, per your last request):
- Body copy: "EVERYAISLE is a generative AI shopping companion..."
- Four "Explore EVERYAISLE →" link labels
- The 4th customer-benefit card, retitled from "GroceryAisle" to "AI Shopping Assistant" (it was
  the odd one out — a stale product name where its three sibling cards use descriptive titles)

**Still says "GroceryAisle" — pending your call on whether/how to update:**
- `home/index.html:372` — "Explore GroceryAisle" link text (the `index.html` twin of this same
  line already says "Explore EVERYAISLE" — these two near-duplicate files are currently
  inconsistent with each other)
- `smartmeals/index.html` — "GroceryAisle" as nav-dropdown and footer link text (3 places)
- `groceryaisle/index.html` — 8 image `alt` attributes still say "GroceryAisle ..." (one-click
  shopping list, recipe directions/cooking mode screens, "branded for Domat's/Clink's/Carney's"
  ×3, widget closed/open ×2, coupons screen) even though the same page's `<title>`, meta
  description, hero logo alt, and two body paragraphs already say "EVERYAISLE" — same
  mid-rename inconsistency as above, just within a single page.
- `dev-docs/index.html` — three informal "Grocery Aisle" (two words) mentions in dev-notes prose

Not user-facing, left alone either way: the `.groceryaisle-*` CSS class/ID naming convention is
used ~250+ times across `groceryaisle/index.html` and `groceryaisle/groceryaisles.css` — pure code
identifiers, renaming them is a refactor with no visible effect.
