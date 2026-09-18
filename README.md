# Trinary Digital Lab

Single-file static site (HTML + Tailwind CDN + vanilla JS). No build step required.

## Deploy on Vercel
1. Push this folder to a GitHub repo.
2. Go to vercel.com → New Project → Import your repo.
3. Framework preset: "Other" (no build command needed).
4. Deploy — Vercel will serve `index.html` at the root automatically.

## Deploy on GitHub Pages (alternative)
1. Push to a repo, enable Pages in repo Settings → Pages.
2. Set source to the branch/root containing `index.html`.

## Replacing placeholder media
Search `index.html` for `ph-media` — every spot that needs a real image or video has this class
plus an HTML comment right above it explaining exactly what to swap in and the recommended tag.
There are 7 placeholders total:
- 5 project thumbnails in the "Selected Work" grid
- 1 project cover image inside the work detail modal (swaps per project automatically)
- 1 optional client headshot in the testimonials section

Drop your real assets in an `/assets` folder (e.g. `/assets/projects/landzero.jpg`) and swap each
placeholder `<div class="ph-media">...</div>` block for an `<img>` tag as shown in the comment above it.

## Notes
- Contact form currently just shows a confirmation message on submit — wire it to Formspree, Resend, or your own API endpoint in the `<script>` block's `contactForm` submit handler.
- Social links (Instagram/LinkedIn/WhatsApp) in the footer and contact section are placeholders — search for `href="#"` and your placeholder text to update them.
