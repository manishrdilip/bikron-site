# bikron.ca — deploy guide

Static one-page site (`index.html`). No build step.

## Hosting: Cloudflare Pages (free, commercial use allowed)
Vercel's free Hobby plan is for non-commercial use only, so use Cloudflare Pages.

1. GitHub → New repository → `bikron-site` → upload `index.html` and this README → Commit.
2. dash.cloudflare.com → Workers & Pages → Create → Pages → Connect to Git → pick `bikron-site`.
   Framework preset: None. Build command: empty. Output directory: `/`. Deploy.
3. In the Pages project → Custom domains → add `bikron.ca` and `www.bikron.ca`.
   Cloudflare shows the DNS records to add.
4. Namecheap → bikron.ca → Advanced DNS → Host Records → add exactly what Cloudflare shows
   (usually CNAME `www` → `bikron-site.pages.dev`; for the root `@`, Namecheap may need
   the domain's nameservers moved to Cloudflare — if so, re-add the Zoho MX/SPF/DKIM/DMARC
   records in Cloudflare DNS BEFORE switching nameservers).
5. Every future edit: change `index.html` on GitHub → site updates automatically.

## Running cost
| Item | Cost |
|---|---|
| Domain bikron.ca (Namecheap) | ~$11/yr |
| Zoho Mail (free plan) | $0 |
| GitHub + Cloudflare Pages | $0 |
| Payments: Interac e-Transfer / Stripe invoice | $0 monthly; Stripe ~2.9% + 30¢ per card payment |
| **Total fixed** | **~$11/year** |

## Later (optional)
- Free booking link: Cal.com → replace the email button with your booking URL.
- Add a 60-second demo video (screen recording on your own sample model, never employer files).
