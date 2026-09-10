# Breez AI → EVERYAISLE: what's still missing

Everything else (metadata, visual assets, page removals/renames + redirects,
alt text, orphaned duplicates, unused legacy assets) is done, committed, and
deployed to production. This file tracks only what's left.

## Needs a decision from you

- **`/terms` and `/privacy` body text** — still say "Breez AI Corporation" as
  the legal entity throughout (~180 instances combined: liability,
  arbitration, IP, data-controller clauses, mailing address). This is a real
  legal-filing decision (new entity name? DBA?), not a text swap.
- **Social links** (footer on every page, plus `/contactus`) — still point at
  `linkedin.com/company/breez-ai`, `x.com/MyBreezAI`, `youtube.com/@mybreezai`.
  Needs the accounts themselves renamed first, or the links will 404.
- **Domain** — still `mybreezai.com` everywhere (canonical URLs, OG/JSON-LD
  image URLs, `Legal@mybreezai.com`). Needs a domain decision.

## Cosmetic / internal-only, no visible or functional impact

- CSS class names still prefixed with old brand names: `.groceryaisle-*`
  (~250+ uses in `/product`), `.whybreez-*`, `.comparison-col-breez`,
  `.breez-calendar` (bookdemo's date picker)
- Blog category keys `breez-news` / `breez-in-the-news` / `breez-insights`
  (button labels already correctly say "EVERYAISLE News" etc. — only the
  internal `data-category` values are old)
- A code comment ("BREEZ AI BLOG STYLES") in `insights/insights.css`
