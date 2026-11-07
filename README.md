# Brand Sales Agent V2.1 — GitHub Pages release

## Files
- `index.html` — application (HTML, CSS and JavaScript)
- `manifest.webmanifest` — installable PWA metadata
- `sw.js` — same-origin app-shell caching and offline fallback
- `icon.svg` — PWA icon

## Deploy on GitHub Pages
1. Create/open the repository for Brand Sales Agent.
2. Upload **all four files** to the repository root (not inside an extra nested folder).
3. In GitHub, open Settings → Pages; deploy from the `main` branch and `/ (root)`.
4. Wait for the published HTTPS URL.
5. In Supabase Authentication → URL Configuration, set the Site URL to the published app URL and add the same URL (and any required auth callback path) to Redirect URLs.
6. Open the hosted app, go to Settings & Data, enter the dedicated Brand Sales Supabase Project URL and publishable key, then Connect project.

## Safety notes
- Use the dedicated Brand Sales Agent Supabase project, not the CV Screener project.
- Never put a Supabase service-role/secret key, database password, or account password in this app.
- Export a JSON backup before the first cloud sync or any restore.
- Do not press Restore unless you intend to replace this device's current local app data with the selected cloud workspace.
- Test with sample records before entering real customer information.
- The SQL setup was already run in the dedicated Supabase project and `workspace_state` was verified. Do not run a database script again as part of this upload.

## Current implementation boundaries
- The app uses local browser storage and a versioned JSON workspace snapshot for cloud sync.
- The Supabase client is loaded from jsDelivr, so initial connection requires internet access.
- AI prospect enrichment, WhatsApp/Meta integrations and automated outbound messaging are not connected; outbound automation remains disabled.
- Verify email confirmation, redirect handling, RLS access, sync and restore on the hosted URL before relying on cloud data.
