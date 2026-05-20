# The Muscle Bee Fitness — Website

## Overview

The site is delivered as **one primary page**: `index.html` — black luxury background (**#050505**), charcoal (**#111111**), gold accents (**#ffcc00** / **#f5b301**), honeycomb-style lines, particles, glass cards, scroll reveal, hero counters, parallax on the hero visual, modals (join / trial), sticky mobile CTAs, and **WhatsApp** to **+91 73535 77774** (`917353577774`).

- **Logo / favicon**: `gym.png` (project root)
- **Hero video**: `gym_video.mp4` (poster frame: `poster.jpeg`)
- **Contact number**: **7353577774** (shown as +91 73535 77774 in UI)
- **Fonts** (Google Fonts, linked): Bebas Neue, Oswald, Poppins  
- **No Tailwind / GSAP / AOS / Font Awesome** — vanilla CSS + JS in `index.html` only

## Other `.html` files

`about.html`, `services.html`, `classes.html`, `trainers.html`, `membership.html`, `contact.html`, `gallery.html`, `transformations.html`, and `ai-fitness.html` are **short redirects** to the matching section on `index.html` (e.g. `index.html#about`) so old bookmarks still work.

## How to open

Open `index.html` in a browser from this folder (double-click or “Open with Live Server”).

## Deploy to Vercel

Step-by-step: push to GitHub, connect Vercel, env notes — see **[DEPLOY.md](./DEPLOY.md)**.

## Structure inside `index.html`

| Section ID   | Content                          |
|-------------|-----------------------------------|
| `#home`     | Hero, stats, CTAs, logo visual   |
| `#why`      | Why choose (6 cards)             |
| `#about`    | Story, mission, timeline, stats  |
| `#services` | Service pillars                  |
| `#classes`  | Sample weekly schedule           |
| `#trainers` | Trainer cards                    |
| `#membership` | Pricing (Basic / Pro / Elite) |
| `#testimonials` | Reviews                     |
| `#gallery`  | Placeholder grid (replace with photos) |
| `#lead`     | Mid-page CTA strip               |
| `#contact`  | Phone, WhatsApp, enquiry form    |

## Customisation

- Replace gallery placeholders with real `<img>` tags or background images.
- Point forms to your backend or a form service.
- Update address / social links in the footer and contact blocks.

© 2026 The Muscle Bee Fitness
