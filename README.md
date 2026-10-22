# Cumulo

A sample cloud storage website: a marketing landing page, a demo storage app, and the legal pages. Everything is plain HTML, CSS and JavaScript in single files. There is no build step and nothing to install.

## Pages

| File | What it is |
| --- | --- |
| `index.html` | Landing page shown before login: features, security highlights and sign-up prompts |
| `app.html` | Demo storage app: file grid and list views, search, upload by drag and drop, star, trash and restore, storage meter |
| `privacy.html` | Privacy policy (sample) |
| `terms.html` | Terms of service (sample) |

All pages link to each other with relative paths, so keep them in the same folder.

## Run it locally

Open `index.html` in a browser, or serve the folder:

```bash
python3 -m http.server 8000
```

Then visit <http://localhost:8000>.

## Deploy

Because the site is static, any static host works: GitHub Pages, Netlify, Cloudflare Pages, Vercel, or an S3 bucket with static hosting. Upload the folder contents so that `index.html` sits at the root.

## Features

- Responsive layout that works down to phone width
- Light and dark themes that follow the system setting (the app also has a manual toggle)
- Keyboard-friendly focus styles and reduced-motion support
- No frameworks or dependencies. The only external request is the Schibsted Grotesk font from Google Fonts, with system fonts as a fallback

## What is demo-only

- **No real login.** The Log in and Sign up buttons open `app.html` directly.
- **No real storage.** Uploads in `app.html` are held in the browser’s memory and disappear on refresh. The starting files are sample data.
- **Placeholder details.** The brand name, prices, security claims (end-to-end encryption, 99.99% uptime), email addresses and the address in the legal pages are all invented.

## Before you go live

1. Replace placeholder text: company name, `*@cumulo.example` emails, address, plan sizes and prices.
2. Have a lawyer review `privacy.html` and `terms.html` and update them to match what your product really does. They are samples, not legal advice.
3. Replace the demo login links in `index.html` (search for `app.html`) with your real sign-in and sign-up routes.
4. Connect `app.html` to a backend for authentication, file storage and sharing. Services such as S3 or Supabase Storage can handle storage.
5. Check that every claim on the landing page is true for your service.
6. Add analytics or a cookie banner if you use optional cookies, as `privacy.html` describes.

## Customizing the look

Colors live in CSS variables at the top of each file (`--accent`, `--bg`, `--ink` and so on), with a matching dark set. Change the variables to re-theme a page. The same block is repeated in each file, so update all four to keep them consistent.

## License

Add your license here.
