# SERFIX Service Limited Website PRD

## Original Problem Statement
Пользователь попросил сделать демо-сайт для SERFIX Service Limited и позже запросил переносимые файлы сайта для самостоятельного хостинга вне Emergent/GitHub root setup.

## Architecture Decisions
- Main app: React frontend with FastAPI/MongoDB backend for inquiry storage in the full-stack preview.
- Static export: portable React production build with relative asset paths (`PUBLIC_URL=.`).
- Static contact flow: form opens an email draft to `info@serfixservice.com`, so the site works on static hosting without backend.
- Brand content: SERFIX Service Limited, Regina, Saskatchewan, Local | Reliable | Trusted, services and contacts from supplied images.

## Implemented
- One-page SERFIX promotional website with hero, services, trust/benefits, direct phone/email CTAs, contact form, and footer.
- Backend inquiry API for the full-stack version: `POST /api/inquiries`, `GET /api/inquiries`.
- Static export package created at `/app/serfix_static_site.zip`.
- Static files folder created at `/app/serfix_static_site`.

## Testing
- JavaScript and Python lint passed.
- Backend API tested with curl and testing agent.
- Frontend tested with Playwright screenshots.
- Static export tested locally via Python static server.

## Prioritized Backlog
### P0
- User downloads `/app/serfix_static_site.zip` and uploads all contents to chosen hosting public folder.

### P1
- If database-backed requests are needed later, connect the contact form to the chosen hosting provider/backend or form service.

### P2
- Add SEO meta tags, business hours, testimonials, and project/gallery photos.


## GitHub Pages Ready Update
- Updated React routing to render the site on any path (`path="*"`), fixing blank screens on GitHub Pages subpaths like `/SERFIX4/serfix_static_site/`.
- Created `/app/docs` with static build contents and `.nojekyll` for GitHub Pages `main /docs` publishing.
- Created `/app/serfix_github_pages_ready.zip` containing both `docs` and `serfix_static_site` folders.
- Verified nested path rendering locally with `/SERFIX4/serfix_static_site/`.


## No-Badge Static Export Update
- Removed platform badge and related external scripts from `frontend/public/index.html`.
- Rebuilt `/app/docs` and `/app/serfix_static_site`.
- Repacked `/app/serfix_github_pages_ready.zip`.
- Verified rendered site has no `Made with Emergent` text and no `#emergent-badge` element.


## Hero Visual Update
- Added Regina/Saskatchewan themed background image to the hero with dark/yellow overlay.
- Increased hero poster/photo area to dominate the hero section while preserving full image information with `object-contain`.
- Added hammer-logo image badge using the provided SERFIX logo reference and positioned it outside the poster so it does not cover important content.
- Rebuilt `/app/docs`, `/app/serfix_static_site`, and `/app/serfix_github_pages_ready.zip`.


## First Slide Image Update
- Replaced the first-slide hero image with the SERFIX hammer/logo photo.
- Kept the image large and fully visible using `object-contain`, preserving important text/details.
- Removed the small added avatar/logo badge from the hero image.
- Rebuilt `/app/docs`, `/app/serfix_static_site`, and `/app/serfix_github_pages_ready.zip`.


## Hero Background Revert
- Reverted the hero background image back to the previous Regina-themed background.
- Kept the SERFIX service poster as the main first-page image.
- Rebuilt `/app/docs`, `/app/serfix_static_site`, and `/app/serfix_github_pages_ready.zip`.


## EmailJS Integration Update
- Installed `@emailjs/browser`.
- Connected static contact form to EmailJS using service ID `service_3fa8cbc`, template ID `template_wmdgw1o`, and provided public key.
- Static export now sends requests directly via EmailJS instead of opening a mailto email draft.
- Template params include `name`, `phone`, `email`, `service`, `message`, `submitted_at` and common aliases (`from_name`, `user_phone`, etc.) for compatibility.
- Rebuilt `/app/docs`, `/app/serfix_static_site`, and `/app/serfix_github_pages_ready.zip`.


## EmailJS Template Variables Alignment
- User provided EmailJS template screenshot showing variables: `name`, `time`, `message`, `email`.
- Updated EmailJS payload so `message` contains phone, email, selected service, and user message.
- `email` uses submitted email when present, otherwise SERFIX contact email as safe fallback for Reply-To.
- Rebuilt `/app/docs`, `/app/serfix_static_site`, and `/app/serfix_github_pages_ready.zip`.
