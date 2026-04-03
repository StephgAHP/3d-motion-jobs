# Creative & 3D Design Jobs Board

## What This Is
A curated jobs board for Jimi Richardson - independent 3D motion designer specialising in Houdini simulation, product animation, and immersive brand visuals. Built as a static HTML site, deployed on Vercel, auto-updated weekly.

**Live site:** https://3d-jobs-board.vercel.app
**Pages:**
- `index.html` - Main jobs board (all listings, studios, communities, AI tools, tips)
- `apply.html` - Pitches & Outreach (tailored cover letters, cold outreach templates, application tracker)
- `gmail-setup.html` - Gmail CRM setup guide (Google Apps Script to auto-track outreach emails)

## Jimi's Profile (for matching roles)
- **Speciality:** Houdini simulation, product animation, CGI rendering, brand visuals
- **Clients:** Jurlique, MCO Beauty, Phyco Health, Shaw + Smith, Minirig, Royal Salute
- **Industries:** Health, beauty, beverage, premium consumer brands
- **Studio:** Animaforma (with Eliza Richardson)
- **Approach:** Photographer's eye for light, texture, weight, time. 20+ years across photography, moving image, design, motion
- **Portfolio:** jimirichardson.com
- **Email:** jimi@jimirichardson.com
- **LinkedIn:** linkedin.com/in/jimirichardson
- **Instagram:** instagram.com/jimirichardson

## Site Structure

### index.html sections (in order):
1. **Hero** - stats, two CTA buttons (Pitches & Outreach, Gmail CRM Setup)
2. **Nav** - 4 dropdown menus: Jobs, Employers, Resources, Learn
3. **Top Picks** - 10 curated best-match roles with "Your Pitch is Ready" CTAs
4. **Brand & Creative Jobs** - remote creative/brand designer roles
5. **3D & Motion Jobs** - motion designer, 3D artist roles
6. **Houdini & FX Jobs** - Houdini specialist, FX artist roles
7. **Studios & Agencies** - 55+ studios organized by: Remote-First, Branding, Digital, Motion, VFX
8. **Tech Companies** - AR/VR/spatial roles at Apple, Meta, Snap, Epic, etc.
9. **Job Boards** - 30+ boards: Creative/Brand, 3D/Motion specialist, General
10. **Communities** - Facebook groups, Discord, forums, Reddit, design communities
11. **Freelance** - platforms, talent networks, recruitment agencies
12. **Salaries** - pay rate benchmarks with visual bars
13. **AI Tools** - Houdini 21 ML features, complementary tools, coding assistants, learning resources
14. **Tips** - 10 tips for getting hired

### apply.html sections:
1. **Profile** - one-click copy: one-liner, full bio, portfolio, LinkedIn, email, Instagram
2. **Tailored Pitches** - accordion cards with pre-written cover letters for each top pick role
3. **Cold Outreach Templates** - 4 templates: general studio, branding agency, product CGI, VFX studio
4. **Studios to Contact** - 12 studios with direct email/careers links
5. **Gmail Auto-Sync CTA** - links to gmail-setup.html
6. **Tracker** - job applications + studio outreach tracker with status cycling (localStorage)
7. **Add Your Own** - form to add custom entries to tracker

### gmail-setup.html:
- Step-by-step guide to set up Google Apps Script that auto-logs outreach emails to a Google Sheet
- Copy-paste script with pre-loaded studio domains and keywords
- Runs hourly, matches sent emails to studios

## How to Update

### Refresh job listings:
1. Search job boards (see the "Where to Search" section for all URLs)
2. Update the relevant section in `index.html`
3. Each job card follows this HTML pattern:
```html
<div class="job-card">
  <div class="company">COMPANY NAME</div>
  <div class="title">JOB TITLE</div>
  <div class="meta">
    <span class="tag remote">Remote</span>
    <span class="tag salary">$XXk-$XXk</span>
  </div>
  <div class="desc">Brief description.</div>
  <a class="apply-link" href="URL" target="_blank">View Role <svg class="arrow-svg" viewBox="0 0 16 16" fill="none" stroke="currentColor" stroke-width="2"><path d="M3 8h10M9 4l4 4-4 4"/></svg></a>
  <a class="kit-link" href="apply.html" style="font-size:0.72rem;">Use Outreach Template</a>
</div>
```

### Tag classes available:
- `.tag.remote` - cyan, for remote roles
- `.tag.hybrid` - orange, for hybrid roles
- `.tag.onsite` - grey, for onsite roles
- `.tag.salary` - green, for salary info
- `.tag.level` - purple, for experience level
- `.tag.hot` - yellow, for new/notable
- `.tag.contract` - pink, for contract roles
- `.tag.closing` - red, for closing dates
- `.tag.top-pick` - cyan bold, for top pick roles

### Top pick cards use:
```html
<div class="job-card top-pick">
  <!-- same structure but with top-pick class, gets cyan border + "TOP PICK" badge -->
  <!-- use "Your Pitch is Ready" kit-link instead of "Use Outreach Template" -->
</div>
```

### Update stats in hero:
Change the numbers in the `.stat .num` divs at the top of the page.

### Update date:
Change the date in the hero `.subtitle` and in the `<footer>`.

## Design System
- **Theme:** Dark with purple (#7c3aed) and cyan (#22d3ee) accents
- **Background:** #0a0a0f
- **Surface:** #141420
- **Border:** #2a2a42
- **Text:** #e8e8f0, muted: #8888a8
- **Border radius:** 12px (cards), 8px (small), 99px (pills/tags)
- **Mobile:** Fully responsive. Single column below 768px. Dropdown nav works via tap on mobile.

## Deployment
- **Hosting:** Vercel (auto-deploys from GitHub on push to master)
- **Repo:** github.com/StephgAHP/3d-motion-jobs
- **No build step** - just static HTML files. Push and it's live.
- **Hidden from Google:** noindex meta tags + X-Robots-Tag headers via vercel.json

### To deploy changes:
```bash
git add -A
git commit -m "describe your change"
git push origin master
```
Vercel deploys automatically in ~10 seconds.

## Weekly Auto-Refresh
There is a scheduled Claude Code agent that refreshes listings every Monday 7am ACST. It searches all job boards, updates the HTML, commits and pushes. This runs on Steph's Claude account.

If you want to set up your own: use Claude Code's `/schedule` command to create a weekly trigger pointing at this repo.

## Key Job Sources to Search
**Best for Jimi's niche (product animation / brand CGI):**
- If You Could Jobs: ifyoucouldjobs.com
- Motionographer: motionographer.com/jobs
- ArtStation: artstation.com/jobs
- SideFX Forum: sidefx.com/forum/60/
- Dribbble Jobs: dribbble.com/jobs
- Working Not Working: workingnotworking.com

**Beauty/FMCG careers pages:**
- Estee Lauder: careers.elcompanies.com
- L'Oreal: careers.loreal.com
- Diageo: diageo.com/careers
- LVMH: lvmh.com/join-us
- Unilever: careers.unilever.com

**Freelance:**
- Upwork: upwork.com/freelance-jobs/houdini/ (112 gigs)
- Upwork: upwork.com/freelance-jobs/3d-product-animation/ (1,910 gigs)

## Writing Rules
- No em dashes. Use commas, full stops, or rewrite.
- Keep descriptions to 1-2 sentences per job card.
- Salary in USD unless otherwise noted.
- "View Role" for job links, "View Careers" for studio career pages.
- "Your Pitch is Ready" for top picks, "Use Outreach Template" for other jobs.
