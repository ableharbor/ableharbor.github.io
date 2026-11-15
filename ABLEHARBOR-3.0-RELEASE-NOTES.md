# ABLEHARBOR 3.0 — Release notes

## Included
- CMS workspace dashboard with page, publication, section and media counts plus configuration checks.
- Quick links to homepage editing, page creation, live website and GitHub revision history.
- Global CMS settings for contact email, LinkedIn company URL, business availability and existing footer fields.
- Homepage project inquiry form with required-field validation and structured `mailto:` composition.
- Public site applies CMS-managed LinkedIn and business availability settings.
- ABLEHARBOR-branded GitHub Pages workflow.
- Existing CMS page editor, reusable section templates, drag/drop section ordering, preview, media manager, navigation editor and promotional popup manager retained.
- Generated sitemap refreshed with ABLEHARBOR canonical URLs.

## Validation performed
- `python scripts/build_pages.py` completed successfully and generated four managed pages.
- JSON parsing passed for `content/site.json` and `content/pages.json`.
- Node syntax checks passed for `admin/admin.js`, `site.js`, `script.js` and the homepage inline script.
- Required website, generated route and CMS files exist.
- Sitemap checked for the `ableharbor.github.io` canonical domain and no `opervyn.github.io` references.

## Architecture limits — intentionally not simulated
- Private enquiry inbox / CRM storage: requires a backend or external service. Current form hands the visitor's prepared message to their email app.
- Aggregate visitor analytics: requires an analytics provider or backend. No fake analytics counters were added.
- Server-side CMS authentication: GitHub Pages is static hosting. The existing fine-grained GitHub token remains session-memory-only in the browser.
- Revision history: GitHub commit history is the source of truth and is linked from the dashboard; automated one-click rollback is not added because safe rollback needs explicit commit selection and confirmation.

## Deploy
Upload the repository contents to `main` in `ableharbor/ableharbor.github.io`. GitHub Actions will build and deploy the Pages artifact. Confirm the workflow run is successful, then verify the live homepage, service pages, inquiry email handoff and `/admin/`.
