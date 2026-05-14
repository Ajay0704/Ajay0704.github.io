# Portfolio Website Plan — Ajay Karthick

## File Structure

```
portfolio/
├── index.html
├── style.css
└── script.js
```

Single-page application. No build step, no dependencies, no frameworks.

---

## Color Palette

| Role            | Value         | Notes                              |
|-----------------|---------------|------------------------------------|
| Background      | `#0d1b2a`     | Deep navy                          |
| Surface         | `#1b2d42`     | Card / section backgrounds         |
| Surface Alt     | `#243447`     | Subtle differentiation             |
| Accent          | `#4a9eff`     | CTAs, links, highlights            |
| Accent Muted    | `#2d6ab4`     | Hover states                       |
| Text Primary    | `#e8edf2`     | Main body text                     |
| Text Secondary  | `#8fa3b8`     | Labels, captions, metadata         |
| Border          | `#2a3d52`     | Card borders, dividers             |

Typography: system font stack (`-apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif`) — zero load time, professional feel.

---

## Sections & Content Plan

### 1. Navbar
- Fixed top bar, blurs on scroll (backdrop-filter)
- Left: "AK" monogram or name logotype
- Right: anchor links → About · Experience · Projects · Skills · Education · Contact
- Hamburger menu on mobile (JS-toggled)

### 2. Hero
- Full viewport height
- **Headline:** `Ajay Karthick`
- **Sub-headline (positioning statement):** `"Operations-minded analyst with a manufacturing floor perspective."`
- **Supporting copy:** 2-sentence summary (MSBA, 2+ yrs manufacturing analytics, supply chain + ML)
- **CTAs:** [Download Resume] (placeholder href) · [View Projects] (scroll anchor) · [Contact Me] (scroll anchor)
- **Subtle animated background:** CSS-only dot/grid pattern, no JS animation — keeps it readable and calm
- Social icon row: LinkedIn · GitHub · Email · Phone

### 3. About
- Two-column layout (text left, stat cards right) — stacks on mobile
- Prose: manufacturing-to-analytics story, Northeastern MSBA angle
- 3 stat cards: `2+ yrs` experience · `3 roles` across industries · `3.7 GPA`

### 4. Experience
- Vertical timeline (centered line, alternating cards left/right on desktop, single column on mobile)
- Each card: company name · role · date range · location · bullet list
- Badges for company type (color-coded: Intern = accent blue, Full-time = slate green)
- Ordered newest-first

### 5. Projects (Featured Cards)
- 3-column grid on desktop → 2-col → 1-col on mobile
- Each card contains:
  - Project title
  - Context/client label (e.g., "Self-built · Trade Analytics")
  - Description (2–3 lines)
  - Key metrics chips (e.g., R²=0.85 · MAE=0.90)
  - Tech tag row
  - [GitHub →] button — only on Tariff Shock Navigator card (links to `github.com/Ajay0704/tariff-shock-navigator`)
  - Other two cards show no external link (no dead placeholder buttons)
- Cards have subtle hover lift (transform + box-shadow transition)

### 6. Skills
- 6 grouped sections rendered as tag clouds
- Groups: Languages & DBs · ML & Stats · AI & Automation · BI & Visualization · BA Tools · Soft Skills
- Each group: bold label + row of pill tags
- Accent-colored pills for primary skills, muted for secondary

### 7. Education
- Two cards side by side (stack on mobile)
- Each: institution · degree · graduation · GPA
- Northeastern highlighted slightly (more recent)

### 8. Contact
- Clean centered layout
- Email · Phone · LinkedIn · GitHub — each as a clickable row with icon
- Short call-to-action copy: "Open to full-time Business Analyst and Data Analyst roles."
- No contact form (avoids backend requirement)

### 9. Footer
- Copyright · built-with note · back-to-top link

---

## JavaScript Responsibilities (script.js)

| Feature                        | Implementation                                         |
|-------------------------------|--------------------------------------------------------|
| Mobile nav toggle             | classList toggle on hamburger click                    |
| Smooth scroll                 | `scroll-behavior: smooth` in CSS + JS for offset       |
| Active nav link on scroll     | IntersectionObserver watching each section             |
| Navbar background on scroll   | Add `.scrolled` class after 80px to trigger bg opacity |
| Scroll-reveal animations      | IntersectionObserver adds `.visible` class to cards    |

No third-party libraries. All vanilla.

---

## Responsive Breakpoints

| Breakpoint | Width     | Changes                                              |
|------------|-----------|------------------------------------------------------|
| Desktop    | ≥ 1024px  | Full layout, timeline alternates sides               |
| Tablet     | 768–1023px| Projects 2-col, timeline single-col                 |
| Mobile     | < 768px   | Single col everywhere, hamburger nav, hero stacks    |

---

## Decisions & Rationale

- **No resume embed** — a download link is cleaner and avoids PDF rendering issues; placeholder `#` until user adds actual file.
- **No contact form** — requires a backend or third-party service; direct contact links are more reliable and professional.
- **No hero photo** — not standard for analytics/ops roles; the positioning statement and stats carry the weight.
- **CSS animations kept subtle** — hiring managers in ops/manufacturing skew conservative; flashy effects would undercut credibility.
- **GitHub link only on Tariff Shock Navigator** — the other two are client/capstone projects; no public repo to link.

---

## What I Need From You Before Coding

- [ ] Approve this plan as-is, OR
- [ ] Request any changes to sections, colors, layout, or content

Once approved, I'll write all three files (`index.html`, `style.css`, `script.js`) in one pass.
