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

## Real portfolio images
The 4 project thumbnails, the work-detail modal, and the About section founder photo now
point directly at your real assets on Behance/Cloudinary (pulled from trinarymedia.lovable.app).
These will NOT render in Claude's in-chat artifact preview (it blocks loading images from other
sites), but will display correctly once this file is deployed to Vercel/GitHub Pages, since a real
website has no such restriction. If any of those source URLs ever change or go down, the page
gracefully falls back to a simple line-icon placeholder instead of a broken image.

## Replacing placeholder media with your own files
If you'd rather self-host the images (recommended long-term, so you're not dependent on
Behance/Cloudinary staying up), search `index.html` for `ph-media` and `src:` — each project
in the `projects` array has an `src` field with the current image URL. Replace it with a path to
your own file (e.g. `/assets/projects/reina-signatures.jpg`) after dropping your assets in an
`/assets` folder.

There are 7 media spots total:
- 4 project thumbnails in the "Selected Work" grid (`media: "image"` or `"video"` controls which
  placeholder style — icon + play button — renders as a fallback)
- 1 project cover inside the work detail modal (`#modalMedia`, swaps per project automatically)
- 1 founder photo in the About section
- 1 optional client headshot in the testimonials section (still a generic placeholder — no client
  testimonials were available to pull in yet)

## Notes
- Contact email is still a placeholder (`hello@trinarydigitallab.com`) — your real site uses a
  contact form with no public email listed, so update this to your real address.
- Social links (Instagram, Twitter/X, LinkedIn, Behance) are wired to your real profiles.
