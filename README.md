# Atlantic Gate Logistics — website (test build)

A single-page, scroll-driven website for an import/export logistics company. It's plain HTML, CSS and JavaScript, so there's no framework and nothing to build.

> **Test build:** every element marked `data-demo` in `index.html` holds sample details for a fictional company. That covers the contact details, company facts, licences, client names and testimonials. Replace them with real information before launch.

## Files

```
index.html          the whole site (styles and script included)
media/f/d/001–097.webp  scroll animation frames, desktop (1600×900)
media/f/m/001–097.webp  scroll animation frames, phones and tablets (1280×720)
media/kv-1080.mp4       fallback video, used only if the frames can't load
media/kv-720.mp4        fallback video for small screens
media/kv-poster.jpg     first frame
vercel.json         caching headers for the media files
```

## Settings

At the top of the `<script>` in `index.html`:

```js
var CONFIG = {
  whatsappNumber: '',   // international format, digits only, e.g. country code + number
  quoteEndpoint: ''     // URL of a form service that accepts a JSON POST (e.g. Formspree)
};
```

- With `whatsappNumber` set, the floating button opens a WhatsApp chat. The tracking and quote forms also offer to send their details over WhatsApp.
- With `quoteEndpoint` set, quote requests are POSTed there as JSON. The page only shows a success message when the service accepts the request.

## Run locally

The page loads its media with `fetch()`, so open the site through a local server rather than by double-clicking the file:

```bash
npx serve .            # or: python3 -m http.server 8000
```

## Deploy to Vercel

1. Push this folder to a GitHub repository.
2. In Vercel, choose **Add New → Project** and import the repository.
3. Framework preset: **Other**. Leave the build command empty and keep the output directory as the root.
4. Click **Deploy**.

Or, with the Vercel CLI, run `vercel` from this folder.
