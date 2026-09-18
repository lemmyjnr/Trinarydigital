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
Search `index.html` for `ph-media` — every spot that needs a real image or video has this class.
Placeholders are rendered as photo/video-style tiles (not icons) so the layout previews close to
final. There are 7 spots total:
- 5 project thumbnails in the "Selected Work" grid — each project object in the `projects` array
  has a `media: "image"` or `media: "video"` field controlling which placeholder style renders
- 1 project cover inside the work detail modal (`#modalMedia`, updates per project automatically)
- 1 optional client headshot in the testimonials section

To swap a project thumbnail: find its entry in the `projects` array near the top of the `<script>`
block, and replace the `${p.media === 'video' ? phVideo() : phImage()}` call for that card with a
real `<img src="..." class="absolute inset-0 h-full w-full object-cover">` or `<video>` tag. Drop
your assets in an `/assets` folder (e.g. `/assets/projects/landzero.jpg`) and reference them from
there.

## Notes
- Contact form currently just shows a confirmation message on submit — wire it to Formspree, Resend, or your own API endpoint in the `<script>` block's `contactForm` submit handler.
- Social links (Instagram/LinkedIn/WhatsApp) in the footer and contact section are placeholders — search for `href="#"` and your placeholder text to update them.
