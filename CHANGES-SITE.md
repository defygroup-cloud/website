# Defy website — what changed (16 Oct 2026)

## Structure
- **First screen = the Defy game, unchanged.** `/` still opens on the landing ("Enter site" / "Defy my expectations") and the arcade game is the original code.
- **Choosing "Enter site" turns Defy into a proper website** with a sticky header: **Main · Platform · Clients · Team · Journal (blog) · Log in · Talk to us** and a "▶ Play" button that returns to the game.
  - Returning visitors in the same session, and anyone arriving via an internal link (`/#main`, `/#platform`, …), skip the landing.
  - The main-site content is in the HTML of `/` (not hidden), so search and AI crawlers can read it.
- **Journal (blog):** `/blog/` (English) plus `/blog/zh/` (中文), `/blog/es/`, `/blog/pt/`, `/blog/fr/`, `/blog/de/`. There are 60 articles: every one is in English and Chinese, and 25 also keep their original Spanish, Portuguese, French or German version (145 article pages in total). Articles D51–D60 form a series on agency AI adoption and include redrawn framework diagrams.
- **Log in:** the header button and `/login/` both go to https://cloud.defygroup.ai.
- **Founder portraits:** Ian and Alek are now on the same SOMIN-generated backdrop, with matched zoom, tone and red rim light (`/assets/img/founder-*.jpg|webp`).
- The base64 images that were inlined in `index.html` are now real files in `/assets/img/`, which makes the page much lighter.
- **Founders' pet projects** (brugge2026, cannes, cassidyswing, dickietour, eligodublin, hasbro, navarino, roadtoberkshire, twostoneshowdown) and `defy-deck-pipeline.html` are byte-for-byte unchanged and are not linked from the site, sitemap or llms files.

## Google Analytics
G-LPDJLDH8ZT (the exact snippet supplied) is on `/`, every blog hub, every article and `/login/`. Extra events: `enter_site`, `play_game`, `login_click`, `contact_click`, `blog_click`, `blog_filter`, `login_redirect`.

## SEO / AEO / GEO
- Every page has: title, meta description, canonical, robots (max-image-preview:large), Open Graph and Twitter cards with 1200×630 preview images (one per article and language, in Defy brand), hreflang clusters across languages with x-default = English, and favicons/app icons (`favicon.ico/.svg`, 16/32/48, apple-touch, 192/512) plus `site.webmanifest`.
- JSON-LD: Organization (founders), WebSite, three SoftwareApplications, FAQPage and a speakable WebPage on `/`. Each article has BlogPosting (citations, workTranslation/translationOfWork links, speakable), FAQPage and BreadcrumbList. Each hub has Blog and BreadcrumbList.
- Answer-first article layout: "The question behind this article" with a short answer, key takeaways, question-style H2s, one table, a numbered how-to, FAQ, sources and a "Why we wrote this" note.
- Files: `sitemap.xml` (hreflang + image entries), `robots.txt` (search + AI crawlers allowed, /login/ disallowed), RSS per language (`/blog/feed.xml`, `/blog/zh/feed.xml`, …), `llms.txt`, `llms-full.txt`, `ai.txt`, `humans.txt`, `.well-known/security.txt`.

## Domain assumption
All absolute URLs use **https://defygroup.ai**. If the site is served from another host (for example www.), search-and-replace that string before deploying. No CNAME file was added.

## Dates
All articles are dated 16 Oct 2026, the day they were produced. To stagger publication, change the dates in the article JSON and rebuild, or edit `datePublished` and the visible dates.
