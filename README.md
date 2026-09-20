# Meher & Co. — static site

Four hand-written HTML pages and one stylesheet. No build step, no dependencies.

```
index.html       home
collection.html  what's on the racks, prices, stitching and alterations
about.html       the shop, sourcing, how we work
visit.html       appointment form, hours, directions
style.css        shared styles for all pages
```

Currently scoped to **women's wear only** — sarees, lehengas, salwar suits and girls' sizes.

## Publishing on GitHub Pages

1. Create a new **public** repository. Name it `USERNAME.github.io` (your own GitHub username) to get the site at the root of your account, or any name you like if `username.github.io/reponame/` is fine.
2. Upload all five files to the top level of the repo — not inside a folder. `index.html` must sit at the root or Pages will 404.
3. Open **Settings → Pages**. Under "Build and deployment", set Source to **Deploy from a branch**, branch **main**, folder **/ (root)**, and save.
4. Wait a minute or two and reload that screen — the live URL appears at the top. If you're updating an existing repo and the site still looks old, hard-refresh (Ctrl/Cmd+Shift+R) or check the Actions tab for a fresh deploy before assuming something's wrong.

When you buy a domain later, add it under Settings → Pages → Custom domain and point a CNAME record at `USERNAME.github.io`. None of these files need to change.

## Making it yours

- **Shop name**: in the `.wordmark` link, the footer heading, and each `<title>`. Search for `Meher & Co.`
- **Colors**: the six values under `:root` in `style.css` drive every page — deep maroon, temple gold, peacock teal and saffron on warm ivory.
- **Signature motif**: the scalloped gold strip under the header and above the footer (`.scallop`) is the one recurring decorative element, styled after a temple/sari border. It's deliberately used just twice per page rather than everywhere.
- **Address, phone, hours**: repeated in the footer of all four pages. Search for `555-0142` and `412 Main Street` to catch every instance.
- **Prices**: all in `collection.html`, inside `<span class="price">`. Ranges are placeholders — replace with your real numbers before publishing.
- **Photos**: this is the one thing the site most needs. Drop image files into the repo and add `<img src="saree-green.jpg" alt="Emerald Kanjivaram with gold border">` inside any `.panel`, or above the `<h1>` in the hero. Images are already capped to their container width.

## The appointment form

GitHub Pages serves static files only and cannot process a submission. `visit.html` posts to [Formspree](https://formspree.io), which has a free tier. Create a form there, copy the form ID, and replace `YOUR_FORM_ID` in the `action` attribute. Until then the form delivers nothing; the phone and email links work regardless.
