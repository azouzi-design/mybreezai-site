# Breez AI → EVERYAISLE: rebrand status

Tracks the Breez AI → EVERYAISLE company rebrand and the GroceryAisle → EVERYAISLE
product rename. Supersedes the original metadata-only report — this now covers
everything: visible copy, metadata, visual assets, page structure, and what's
still open. **Nothing described as "done" below has been committed or pushed
yet** — all of it is local, uncommitted working-tree changes.

---

## Done

**Visible copy** — "Breez"/"Breez AI"/"Breez AI Corporation" replaced with
"EVERYAISLE" across all site copy, logo `alt`/`aria-label` text, and the
`groceryaisle`→`product` page's image `alt` attributes — except where noted
under "Open" below.

**Page `<title>`, `<meta name="description">`, OG/Twitter tags, JSON-LD** —
rewritten across every page. Real per-page descriptions were written where
none existed before (most pages had none). `favicon/site.webmanifest`
`name`/`short_name` updated to EVERYAISLE.

**Visual brand assets recreated** — the old logo/OG-image files had "BREEZ AI"
drawn as literal vector path shapes (no editable text), so they couldn't be
edited, only replaced:
- `content/EVERYAISLE_Logo.png` — new JSON-LD `logo`, built from the real
  EVERYAISLE cart/arrow icon already live in the homepage splash animation
- `content/og/everyaisle-og.png` — new OG/Twitter share image (1512×794)
- Both wired into `index.html` / `home/index.html`'s OG, Twitter, and JSON-LD
  tags, replacing every reference to the old `breez-og.jpg` /
  `BreezAI_Logo_TransparentBG.png`

**Pages removed:**
- `/dev-docs` and `/design-md` — deleted, links removed from the shared
  footer partial and (the now-also-removed) `/smartmeals` inline footer
- `/smartmeals` — deleted. Confirmed orphaned first (no other page linked to
  it; its "GroceryAisle"/"SmartMeals" mentions elsewhere were just CSS class
  names and a partner-logo image, not links to the page). Redirected to
  `/product` for any stray external traffic.

**Pages renamed** (directory + internal `git mv`, so history is preserved),
each with every internal link fixed (nav, footer, cross-page CTAs) and a 301
redirect added in `vercel.json` so existing bookmarks/search listings/shared
links don't break:
- `/groceryaisle` → `/product` (`groceryaisles.css` → `product.css`)
- `/whybreez` → `/whyeveryaisle` (`whybreez.css` → `whyeveryaisle.css`)
- `/blog` → `/insights` (`blog.css` → `insights.css`; footer label "Blog" →
  "Insights" to match the nav, which already said Insights)

---

## Open — needs a decision or hasn't been touched

### Needs a decision from you
- **`/terms` and `/privacy` body text** — still say "Breez AI Corporation" as
  the legal entity throughout (~180 instances combined: liability,
  arbitration, IP, data-controller clauses, mailing address). This is a real
  legal-filing decision (new entity name? DBA?), not a text swap — left
  entirely alone pending that call. Page `<title>`/description metadata for
  both *was* updated to say EVERYAISLE, since that's pure metadata, not the
  contracting-party name.
- **Social links** (footer on every page, plus `/contactus`) — still point at
  `linkedin.com/company/breez-ai`, `x.com/MyBreezAI`, `youtube.com/@mybreezai`.
  Left alone because the accounts themselves haven't been renamed — changing
  the link text/href without the account renamed would 404.
- **Domain** — still `mybreezai.com` everywhere (canonical URLs, OG/JSON-LD
  image URLs, `Legal@mybreezai.com`). Unchanged since ownership/DNS hasn't
  moved.
- **Orphaned `blog/blog/` duplicate directory** — a stale, fully-orphaned copy
  of the old blog (nothing links to it, confirmed twice now). Not deleted —
  same situation `/dev-docs` and `/design-md` were in before you had those
  removed. Flagged repeatedly, no decision yet either way.

### Bugs / regressions to fix
- **`/whyeveryaisle` title regression** — its `<title>`, `og:title`, and
  `twitter:title` still read "Why Breez | EVERYAISLE". The original metadata
  pass deliberately preserved "Why Breez" as page-specific text and only
  fixed the trailing "| Breez AI" company tag — but the page has since been
  renamed to `/whyeveryaisle/`, so "Why Breez" is now stale next to its own
  URL. Needs fixing.

### Cosmetic / internal-only, no visible or functional impact
- CSS class names still prefixed with old brand names: `.groceryaisle-*`
  (~250+ uses in `/product`), `.whybreez-*`, `.comparison-col-breez`,
  `.breez-calendar` (bookdemo's date picker)
- Blog category keys `breez-news` / `breez-in-the-news` / `breez-insights`
  (button labels already correctly say "EVERYAISLE News" etc. — only the
  internal `data-category` values are old)
- A couple of code comments ("BREEZ AI BLOG STYLES") in `insights/insights.css`
  and the orphaned `blog/blog/blog.css`
- 7 unused legacy image files in `/content`, confirmed referenced nowhere:
  `GAlogo.png`, `GrocerAisle.png`, `SVG GrocerAisle.svg`,
  `groceryaisle-logo.png`, `groceryaisle-v2.png`, `groceryaisle.png`,
  `groceryaisle_mockup.png`

### Deployment
- Everything above that's marked "Done" is still **uncommitted, unpushed**.
  Production (mybreezai.com) is running the old code until this is committed
  and deployed.
