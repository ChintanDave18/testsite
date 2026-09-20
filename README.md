# Meher & Co. — static site

Four hand-written HTML pages and one stylesheet. No build step, no dependencies.

```
index.html       home, with a scrollable gallery of the collection
collection.html  what's on the racks, prices, stitching and alterations
about.html       the shop, sourcing, how we work
visit.html       appointment form, hours, directions
style.css        shared styles for all pages
```

Scoped to **women's wear only** — sarees, lehengas, salwar suits and girls' sizes.

## Publishing on GitHub Pages

1. Create a new **public** repository. Name it `USERNAME.github.io` (your own GitHub username) to get the site at the root of your account, or any name you like if `username.github.io/reponame/` is fine.
2. Upload all five files to the top level of the repo — not inside a folder. `index.html` must sit at the root or Pages will 404.
3. Open **Settings → Pages**. Under "Build and deployment", set Source to **Deploy from a branch**, branch **main**, folder **/ (root)**, and save.
4. Wait a minute or two and reload that screen — the live URL appears at the top. If you're updating an existing repo and the site still looks old, hard-refresh (Ctrl/Cmd+Shift+R) or check the Actions tab for a fresh deploy before assuming something's wrong.

When you buy a domain later, add it under Settings → Pages → Custom domain and point a CNAME record at `USERNAME.github.io`. None of these files need to change.

## Making it yours

- **Shop name**: in the `.wordmark` link, the footer heading, and each `<title>`. Search for `Meher & Co.`
- **Colors**: the six values under `:root` in `style.css` — deep wine (`--maroon`), antique gold (`--gold`), peacock teal (`--teal`) on warm ivory. Cards use soft shadows rather than hard outlines for a calmer, more tailored look.
- **Signature motif**: `.ornament`, a thin rule with one small diamond mark, used once above section headings. It's the one recurring decorative touch, kept deliberately quiet.
- **Address, phone, hours**: repeated in the footer of all four pages. Search for `555-0142` and `412 Main Street` to catch every instance.
- **Prices**: all in `collection.html`, inside `<span class="price">`. Ranges are placeholders — replace with your real numbers before publishing.

## The gallery — replacing the placeholder photos

The home page and the collection page each have a horizontally scrollable gallery (`<div class="gallery">`). Right now every image is a solid-color placeholder from placehold.co, just labelled with a dress category so the layout reads correctly before you have real photos.

To swap in your own photo, replace the placeholder `<img>` line inside a `<figure>`:

```html
<figure>
  <div class="frame"><img src="https://placehold.co/440x560/7c1f3d/f0d9a8?text=Kanjivaram&font=playfair-display" alt="Placeholder — Kanjivaram silk saree"></div>
  <figcaption>Kanjivaram silk</figcaption>
</figure>
```

becomes, once you've added a photo file to the repo (e.g. `photos/kanjivaram-01.jpg`):

```html
<figure>
  <div class="frame"><img src="photos/kanjivaram-01.jpg" alt="Deep red Kanjivaram silk saree with gold zari border"></div>
  <figcaption>Kanjivaram silk</figcaption>
</figure>
```

Photos in roughly a 3:4 portrait ratio (e.g. 900×1200px) will fill the frame most cleanly — the CSS crops to fit, so exact dimensions aren't critical. Add or remove `<figure>` blocks to change how many photos appear; the row scrolls sideways automatically no matter how many you add.

## The appointment form

GitHub Pages serves static files only and cannot process a submission. `visit.html` posts to [Formspree](https://formspree.io), which has a free tier. Create a form there, copy the form ID, and replace `YOUR_FORM_ID` in the `action` attribute. Until then the form delivers nothing; the phone and email links work regardless.
