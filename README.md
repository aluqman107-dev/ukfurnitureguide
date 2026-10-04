# UK Furniture Guide — "Honest UK furniture buying guides"

A complete static affiliate/guide website for the UK furniture niche. No build step, no frameworks, no dependencies — just HTML, hand-written CSS and vanilla JS.

## Preview locally

```bash
cd ~/workspace/furniture-guide-uk
python3 -m http.server 8000
# then open http://localhost:8000
```

(Opening `index.html` directly also works, but a local server avoids any file:// quirks.)

## What to replace before launch

1. **Domain** — the site assumes `https://ukfurnitureguide.co.uk/`. Search-and-replace `ukfurnitureguide.co.uk` with your real domain in: all `.html` files (JSON-LD blocks, og tags), `sitemap.xml`, `robots.txt`, `llms.txt`.
2. **Affiliate links** — every "Check Price" button points to `https://www.amazon.co.uk/dp/PLACEHOLDER` and is marked with `<!-- REPLACE WITH YOUR AMAZON AFFILIATE LINK -->`. Replace with your real Amazon Associates links (include your tracking tag). Buttons marked `<!-- REPLACE WITH YOUR AWIN/WAYFAIR AFFILIATE LINK -->` (currently `href="#"`) need your Awin/Wayfair links.
3. **Product images** — every product card has a styled placeholder block plus an HTML comment with suggested alt text, e.g.:
   `<!-- IMAGE: replace with product photo of "…". Suggested alt text: "…" -->`
   Add real photos to an `images/` folder and swap the placeholder divs for `<img>` tags using the suggested alt text. Also create `/images/og-banner.jpg` (1200×630) — og tags already reference it.
4. **Contact form** — `contact.html` has a placeholder form (marked `TODO`). Connect it to Formspree, Netlify Forms, or your own endpoint.
5. **Newsletter form** — `index.html` has a placeholder signup (marked `TODO`). Connect to Brevo/Mailchimp.
6. **Cookie consent** — `privacy-policy.html` references a consent banner (marked `TODO`). Add one before enabling analytics/ads.
7. **Email** — currently `info@ukfurnitureonline.co.uk` throughout. Replace with the site's own address if different.
8. **Affiliate programme list** — `affiliate-disclosure.html` has a `TODO` to update the programme list as you join networks.

## Launch checklist

- [ ] Domain registered and DNS pointed at hosting
- [ ] Static hosting chosen (Netlify, Vercel, Cloudflare Pages, or any cheap shared host — all fine for static files)
- [ ] Domain replaced everywhere (see above)
- [ ] Real affiliate links in place (Amazon Associates approved — needs a live site with content first)
- [ ] Awin application submitted (Wayfair UK + furniture merchants)
- [ ] Product images added with alt text; og-banner.jpg created
- [ ] Contact form backend connected
- [ ] Cookie consent banner added
- [ ] Submitted to Google Search Console + Bing Webmaster Tools (submit sitemap.xml)
- [ ] Google Analytics (or privacy-friendly alternative) installed
- [ ] AdSense: apply later, once the site has steady traffic (needs substantial content + traffic for approval)
- [ ] Re-check all £ prices quarterly — stale prices kill trust

## File map

| Path | What it is |
|---|---|
| `index.html` | Homepage: hero, tool feature, guide cards, trust band, newsletter |
| `guides/best-sofas-uk.html` | 7 Best Sofas 2026 (ItemList + FAQPage schema) |
| `guides/best-beds-uk.html` | 7 Best Beds 2026 (ItemList + FAQPage schema) |
| `guides/best-dining-sets-uk.html` | 6 Best Dining Sets 2026 (ItemList + FAQPage schema) |
| `guides/best-mattresses-uk.html` | 6 Best Mattresses 2026 (ItemList + FAQPage schema) |
| `guides/sofa-buying-guide.html` | Sofa buying guide (Article + FAQPage schema) |
| `guides/bed-buying-guide.html` | Bed buying guide (Article + FAQPage schema) |
| `tools/sofa-size-finder.html` | Interactive sofa size tool (working JS) |
| `about.html`, `contact.html` | Brand story, contact form |
| `privacy-policy.html`, `affiliate-disclosure.html` | UK-appropriate legal texts |
| `css/style.css` | All styling (teal #0E7C7B + coral #FF6B35) |
| `js/main.js` | Mobile nav toggle, footer year |
| `sitemap.xml`, `robots.txt`, `llms.txt` | SEO + AI-crawler files |

## SEO/AEO notes

- Every page: Organization + WebSite JSON-LD; unique title + meta description; og tags.
- Guides/tools: BreadcrumbList JSON-LD.
- All 4 listicles: ItemList JSON-LD (product positions) + FAQPage (5 FAQs each).
- Both buying guides: Article JSON-LD + FAQPage.
- Every guide opens with an "In short:" 40–60 word direct answer for answer engines.
- `robots.txt` explicitly allows GPTBot, ClaudeBot, PerplexityBot, Google-Extended.
- Internal linking: listicles ↔ buying guides, tool linked from homepage + sofa pages, cross-links at page bottoms.
