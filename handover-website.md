# Handover Document — Brilliance Laser Inks Website

**Last updated:** May 23, 2026  
**Prepared by:** Support / AI-assisted build  
**Project:** Brilliance Laser Inks — Demo/Preview Landing Page

---

## 1. Project Overview

This is a **single-page marketing website** built as a demo/preview for Brilliance Laser Inks, LLC. It mirrors the look and feel of the real Shopify store at [brilliancelaserinks.com](https://brilliancelaserinks.com) but is hosted independently on **Cloudflare Workers**.

| Item | Detail |
|---|---|
| **Live Preview URL** | https://brilliance-laser-inks.joshua08161995.workers.dev/ |
| **GitHub Repo** | https://github.com/thesupportperson/brilliance-laser-inks |
| **Real Shopify Store** | https://brilliancelaserinks.com |
| **Hosting Platform** | Cloudflare Workers |
| **Deployment Type** | Manual (not auto-deployed) |

---

## 2. File Structure

```
brilliance-laser-inks/
├── index.html          # Main (and only) page — all HTML, CSS, JS in one file
├── wrangler.jsonc      # Cloudflare Workers configuration
├── README.md           # Basic repo description
├── handover-website.md # This file
└── .gitignore          # Standard Node/Wrangler ignores
```

### Key notes on `index.html`
- All CSS is **inline** in a `<style>` block (no external stylesheets)
- All JavaScript is **inline** at the bottom of the file
- Images are loaded from the **real Shopify CDN** (`brilliancelaserinks.com/cdn/shop/files/...`) — no images are hosted in this repo
- Icons use [Lucide](https://lucide.dev/) loaded via CDN
- Fonts loaded from Google Fonts (Montserrat + Inter)
- Live chat widget loaded from LeadConnector/GHL (`widgets.leadconnectorhq.com`)

---

## 3. Hosting — Cloudflare Workers

This site runs on **Cloudflare Workers** (not Cloudflare Pages). This means:

- ❌ **No automatic deployment** when you push to GitHub
- ✅ Every change to `index.html` must be **manually deployed** to Cloudflare

### How to deploy changes

**Option A — Via Cloudflare Dashboard (no CLI needed)**
1. Go to [dash.cloudflare.com](https://dash.cloudflare.com)
2. Navigate to **Workers & Pages** → select `brilliance-laser-inks`
3. Click **Edit Code**
4. Replace the content of the Worker script with the full contents of `index.html`
5. Click **Deploy**

**Option B — Via Wrangler CLI**
```bash
# Install Wrangler if not already installed
npm install -g wrangler

# Login to Cloudflare
wrangler login

# Deploy from the repo root
wrangler deploy
```

> ⚠️ Note: The `wrangler.jsonc` file in this repo already has the Worker name and configuration set up.

---

## 4. Sections / Page Structure

| Section ID | Description |
|---|---|
| `#home` | Hero slideshow (3 slides, auto-rotates every 5s) |
| `#collections` | 6-card collection grid (Metal, Stainless, Aluminum, Glass, Aerosol, Powder) |
| `#products` | Best sellers — 6 product cards with pricing |
| *(dark section)* | Feature highlights (Support, Shipping, Guarantee) |
| `#gallery` | Photo gallery of laser marking results |
| `#reviews` | 3 customer review cards |
| `#about` | About Brilliance section with stats |
| `#blog` | 3 guide/blog cards |
| `#cta` | Call-to-action band |
| `#newsletter` | Email subscribe form (front-end only, no backend) |
| `#footer` | Footer with nav links and social icons |

---

## 5. Change Log

| Date | Change | Commit |
|---|---|---|
| May 23, 2026 | Initial site build — full single-page landing page | — |
| May 23, 2026 | Fixed collection card images — replaced dark lifestyle photos with clean product bottle shots; forced 6-column grid | `9af4380` |
| May 23, 2026 | Fixed all nav/button links — replaced external Shopify URLs with internal anchor links to keep users on Workers site | `e239baca` |
| May 23, 2026 | Created this handover document | *(this commit)* |

---

## 6. Known Limitations / To-Do

- [ ] **No real cart/checkout** — "Shop Now" and "Add to Cart" buttons scroll to the products section; actual purchasing happens on the real Shopify store
- [ ] **Newsletter form is front-end only** — submitting shows a browser alert; no email is actually captured unless wired to a backend or GHL form
- [ ] **No auto-deploy** — GitHub pushes do not trigger a Cloudflare Workers redeploy (manual step required every time)
- [ ] **Images depend on Shopify CDN** — if the Shopify store removes or changes product images, they will break on this site too
- [ ] **GHL Chat widget** is live and tied to widget ID `6a043a630d6444dd882c6b05`

---

## 7. Brand Assets & References

| Asset | URL |
|---|---|
| Logo (PNG) | `https://brilliancelaserinks.com/cdn/shop/files/Copy_of_logo_3.5_x_1_in.png?v=1778790617` |
| Instagram | https://www.instagram.com/brilliancelaserinks/ |
| Facebook | https://www.facebook.com/Brilliance-Laser-Inks-110205953804077/ |
| YouTube | https://www.youtube.com/@brilliancelaserinks6292 |
| LinkedIn | https://www.linkedin.com/company/brilliancelaserinks/ |

---

## 8. Contact / Support

For questions about this demo site, reach out via the GitHub repo or through the GHL workspace associated with the chat widget above.
