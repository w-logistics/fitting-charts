# FittingCharts

Free hydraulic fitting reference charts for mechanics and shop techs. Plain static HTML and CSS, no build step. Hosted on GitHub Pages at [https://w-logistics.github.io/fitting-charts/](https://w-logistics.github.io/fitting-charts/).

Amazon product links use Associates tag `wlogistics-20` and `rel="sponsored noopener"`. The required sentence “As an Amazon Associate I earn from qualifying purchases” is in the footer of every page and next to the product links.

## Site structure

| File | Page |
| --- | --- |
| `index.html` | Home. Short intro and a card for each chart. |
| `jic-fitting-size-chart.html` | JIC 37° flare (SAE J514) size chart and identification. |
| `orfs-fitting-size-chart.html` | ORFS O-ring face seal (SAE J1453 / Parker Seal-Lok) size chart, O-ring sizes, and identification. |
| `sae-o-ring-boss-orb-fitting-chart.html` | SAE O-ring boss (ORB, SAE J1926) size chart, 900-series O-ring sizes, and identification. |
| `npt-thread-size-chart.html` | NPT pipe thread (ASME B1.20.1) size chart, identification diameters, and NPT versus NPTF and BSPT. |
| `bspp-bspt-thread-size-chart.html` | BSPP and BSPT pipe thread (ISO 228-1 and ISO 7-1) size chart, major diameters, and parallel versus taper sealing. |
| `din-2353-24-degree-cone-fitting-chart.html` | DIN 2353 / ISO 8434-1 24° cone size chart for LL, L, and S series, with tube OD, metric thread, and Parker hex. |
| `how-to-identify-hydraulic-fittings.html` | How to tell JIC, ORFS, NPT, BSP, ORB, and metric 24° cone fittings apart: seal, thread form, and measured thread OD and pitch. |
| `disclosure.html` | About the site, sources, and the Amazon Associates disclosure. |
| `404.html` | Not-found page. GitHub Pages serves this for unknown paths. |
| `styles.css` | Shared layout. Tables sit in `.table-wrap` so they scroll on a phone. |
| `sitemap.xml` | Pages to index. The 404 is omitted. |
| `robots.txt` | Allows crawling and points at the sitemap. |

Shared chrome on every HTML page: header with logo and nav, footer with the affiliate sentence and a link to `disclosure.html`, and the GoatCounter script immediately before `</body>`. The nav lists Home, JIC Chart, ORFS Chart, ORB Chart, NPT Chart, BSP Chart, DIN Chart, ID Guide, and About. The current page sets `aria-current="page"`.

Chart pages also set a unique title and meta description, a canonical URL under `https://w-logistics.github.io/fitting-charts/`, Open Graph tags, and JSON-LD (`TechArticle` plus `BreadcrumbList`). The home page uses `WebSite`. A page with a real FAQ also uses `FAQPage`.

## Checklist for adding a page

Copy `orfs-fitting-size-chart.html` (or `jic-fitting-size-chart.html`) as the template. Then:

1. Give the new file its own title, meta description, canonical URL (`https://w-logistics.github.io/fitting-charts/...`), Open Graph tags, and JSON-LD. Chart pages get `TechArticle` and `BreadcrumbList`. Add `FAQPage` only when the page has a real FAQ section, and make the questions match the visible text.
2. Add the page to the header nav on **every** HTML page, including `404.html`. On the new page only, set `aria-current="page"` on its nav link.
3. Add a card on `index.html` that links to it.
4. Add the canonical URL to `sitemap.xml`. Do not add `404.html`.
5. Keep the footer sentence “As an Amazon Associate I earn from qualifying purchases” and the link to `disclosure.html`. If the page has Amazon links, repeat that disclosure next to the links. Use `rel="sponsored noopener"` and `?tag=wlogistics-20`. Link a specific `/dp/ASIN` page only when you have opened that listing. If you cannot verify an ASIN, use a tagged search URL. Do not invent an ASIN or a product fact.
6. Paste this immediately before `</body>`:

```html
<script data-goatcounter="https://fittingcharts.goatcounter.com/count" async src="//gc.zgo.at/count.js"></script>
```

7. Link the new page from the related-pages list on the charts it belongs with.
8. Open each page and click every internal link.

## Hosting

GitHub Pages: Settings → Pages → Deploy from branch `main` → root. The site is already published from this repository.

Cloudflare Pages or Netlify can host the same folder. There is no build command. The publish directory is the repository root.

A custom domain can be pointed at the host later. Canonical URLs in the HTML are the GitHub Pages URLs until that changes.
