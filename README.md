# Elite Laser Services — Website

**Advanced Skin & Laser Clinic, Saskatoon SK**
[elitelaserservice.ca](https://elitelaserservice.ca)

---

## Stack

- **HTML / CSS / JS** — Zero framework, zero dependencies
- **Hosting:** Cloudflare Pages
- **CMS:** Sanity (Phase 2)
- **Fonts:** Google Fonts (Cormorant Garamond, DM Sans, Bebas Neue)

---

## Project Structure

```
elite-laser/
├── index.html          # Main homepage (single-page)
├── css/
│   └── styles.css      # Full design system + all component styles
├── js/
│   └── main.js         # Cursor, scroll animations, nav, form
├── assets/             # Local images/icons (Phase 2)
├── _headers            # Cloudflare Pages security & cache headers
├── _redirects          # Cloudflare Pages URL redirects
└── README.md
```

---

## Deploy to Cloudflare Pages

### First time
1. Push this folder to a GitHub repo (e.g. `elite-laser-site`)
2. Go to [Cloudflare Pages Dashboard](https://dash.cloudflare.com)
3. Create a new project → Connect to Git → Select repo
4. Build settings:
   - **Framework preset:** None
   - **Build command:** *(leave blank)*
   - **Build output directory:** `/` (root)
5. Deploy → Done

### Custom domain
1. In CF Pages project → Custom domains → Add `elitelaserservice.ca`
2. Update nameservers to Cloudflare (or add CNAME if already on CF)

### Updates
```bash
git add .
git commit -m "your message"
git push
```
Cloudflare auto-deploys on push. Usually live in ~30 seconds.

---

## Design System

| Token | Value |
|-------|-------|
| Background | `#0C0B0F` |
| Surface | `#141218` |
| Accent Gold | `#C8A97E` |
| Accent Cream | `#E8D5BA` |
| Text Primary | `#F5F0EB` |
| Text Muted | `#6B6478` |
| Display Font | Cormorant Garamond |
| Body Font | DM Sans |
| Label Font | Bebas Neue |

---

## Sections (Homepage)

1. **Nav** — Fixed, blurs on scroll
2. **Hero** — Full-screen with laser scan animation + parallax
3. **Trust Bar** — SharpLight / All Skin Types / Pain-Free / Free Consult / Personalized
4. **About** — Split layout, pillars, clinic photo
5. **Services** — 7-service editorial grid (6 + 1 full-width)
6. **Why Elite** — Full-width 3-pillar statement section
7. **Process** — 3-step numbered layout
8. **Testimonials** — 3-card quote grid
9. **CTA** — Full-bleed conversion section
10. **Contact** — Split: form + hours/address
11. **Footer** — Brand, services, clinic, contact, socials

---

## Phase 2: Sanity CMS

Planned schemas:
- `service` — name, slug, description, heroImage, details, faqs
- `testimonial` — quote, author, location, rating, service
- `teamMember` — name, role, bio, photo
- `siteSettings` — phone, email, address, hours, bookingUrl

---

## Phase 3: Service Subpages

Each service gets its own page using a shared `service.html` template,
populated via GROQ queries from Sanity. URLs will follow `/services/[slug]`.

---

*Built by AltX Media for Elite Laser Services*
