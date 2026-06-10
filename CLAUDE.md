# Someone To Talk To — Website

Confidential, non-judgmental talk-session service based in Kerala (not therapy/clinical,
not a medical service — keep the footer disclaimer intact). Brand promise: "You don't
have to face everything alone."

## Project status

A complete single-file homepage exists: `index.html` (HTML + CSS + JS, no build step,
no dependencies except Google Fonts). It was redesigned from client mockups into a
professional layout while keeping the original concept and palette exactly.

### Design system (do not change without asking)
- Colors (CSS vars in `:root`): cream `#F7F4EE`, card `#FBFAF6`, forest `#2E4A3B`,
  forest-dark `#23392E`, sage `#A8BFA5`, sage-pale `#E6ECE2`, ink `#3A4540`,
  ink-soft `#6B7A72`, gold `#C9A86A` (stars only), line `#DDE3D8`
- Type: **Fraunces** (serif, headings) + **Inter** (sans, body/UI), via Google Fonts
- Signature element: arched image frames (hero arched top, FAQ arched bottom)
- Other tokens: 18px radius cards, pill buttons, thin botanical line-art SVG icons
  (inline, stroke-based, 1.4–1.6 stroke width), generous whitespace
- Tone of copy: warm, plain, reassuring; sentence case; never clinical or salesy

### Sections in index.html (in order)
sticky nav (active-section highlight via IntersectionObserver, mobile hamburger) →
hero (arched 3:4 image, trust badges) → about (1:1 image + 4 checkpoints) →
services (10 cards, 5-col grid) → how-it-works (4 numbered steps, dotted connector) →
testimonials (3 cards) → FAQ (native <details> accordion + sticky 3:4 image) →
CTA banner (deep forest) → contact (info + 16:9 image + form) → footer (with disclaimer)

### Images
Four labeled placeholders (IMG-01..IMG-04) rendered as styled `.ph` divs. Each has an
HTML comment directly above it with the exact `<img src="images/IMG-0X-*.jpg">` swap tag.
`image-prompt.md` contains the Nano Banana Pro prompt, filename, and aspect ratio for
each (3:4, 1:1, 3:4, 16:9). When real images are added: drop into `images/`, replace the
`.ph` div with the commented `<img>` tag — containers handle crop/arch/shadow.

### JS behaviors already present
Scroll-reveal (IntersectionObserver, respects prefers-reduced-motion), nav active-state
sync, mobile menu toggle. Form is front-end only — no backend yet.

## Likely next steps (confirm with Anil before large changes)
1. Sub-pages on the same design system: about.html, services.html, faq.html,
   testimonials.html, contact.html (original mockups had these as standalone pages;
   homepage nav may need updating from #anchors to page links — or keep one-page + blog)
2. Decide on Blog (main mockup nav had it; sub-page navs didn't)
3. Wire the contact form to a backend (he runs his own Linux servers — a small
   Node.js/PHP mail endpoint or a form service; ask preference)
4. Booking flow for "Book a Session" (currently anchors to #contact)
5. SEO: meta/OG tags, sitemap, schema.org LocalBusiness, favicon
6. Real images via the Nano Banana prompts in image-prompts.md

## Conventions
- Keep it dependency-free / static unless a backend is explicitly requested
- Single-file pages are fine; if splitting CSS out, extract the existing `:root` tokens
  into `styles.css` shared across pages
- Mobile breakpoints already at 1020/860/520px — test any new section at all three
- Accessibility floor: visible focus, alt text on all real images, reduced-motion respected