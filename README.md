# Squeege ’n’ Shine — website

Single-page website for **Squeege ’n’ Shine Services**, window cleaning in Bentleigh & surrounding suburbs (VIC).

- 📞 0403 927 894
- ✉️ sebastian@squeegenshineservices.com

The whole site is one self-contained file, `index.html` (styles, scripts and images are embedded). No build step, no dependencies. Only Google Fonts loads from the web.

## Repo contents

| Path | What it is |
|---|---|
| `index.html` | The live website |
| `.nojekyll` | Tells GitHub Pages to serve the file as-is |
| `photos/` | Source copies of the images embedded in the page, plus `credits.json` for the stock photos |
| `photos/client-originals/` | Sebastian’s job photos (Google Business Profile) |

## Publish on GitHub Pages (free)

1. Create a new repository on GitHub, e.g. `squeege-n-shine-website`.
2. Upload everything in this folder: **Add file → Upload files**, drag the contents in, and commit. Include `.nojekyll`. On a Mac it’s hidden, so press `Cmd+Shift+.` in Finder to show it.
3. Go to **Settings → Pages**. Under *Build and deployment*, choose **Deploy from a branch**, branch `main`, folder `/ (root)`, then **Save**.
4. After a minute or two the site is live at `https://<your-username>.github.io/squeege-n-shine-website/`.

### Use the real domain (squeegenshineservices.com)

1. In **Settings → Pages → Custom domain**, enter `www.squeegenshineservices.com` and save. GitHub adds a `CNAME` file for you.
2. At the domain registrar, add these DNS records:
   - `CNAME` record for `www` pointing to `<your-username>.github.io`
   - `A` records for the root `@` pointing to `185.199.108.153`, `185.199.109.153`, `185.199.110.153` and `185.199.111.153`
3. Once DNS has updated, tick **Enforce HTTPS**.

⚠️ The domain currently points to an existing website. Changing DNS replaces it, so agree on the switch-over timing with Sebastian first.

## Enquiry forms

Both forms (the hero quick-quote and the contact form) work out of the box. They open the visitor’s email app with a pre-filled message to Sebastian.

To receive enquiries directly, without the visitor’s email app:

1. Create a free form at [formspree.io](https://formspree.io), using Sebastian’s email as the recipient.
2. Copy the endpoint, e.g. `https://formspree.io/f/abcdwxyz`.
3. In `index.html`, search for `const FORM_ENDPOINT=''` and paste it between the quotes:
   `const FORM_ENDPOINT='https://formspree.io/f/abcdwxyz';`
4. Commit. The site updates automatically.

## Editing content

All text (services, FAQ, reviews, hours, phone and so on) lives in one JSON block near the top of `index.html`:

```html
<script type="application/json" id="site-data"> … </script>
```

Edit the text there and commit. Keep the JSON valid: quotes around strings, commas between items.

## Before going live — checklist

- [ ] Sebastian has approved the copy, especially the service inclusions (water-fed pole, gutters, screens, after-hours commercial rounds)
- [ ] OK to show the Google reviews with reviewer names
- [ ] Higher-resolution originals of the job photos (current ones are ~680px wide)
- [ ] Formspree endpoint added (optional)
- [ ] "Fully insured" claim confirmed
- [ ] Stock photo credits stay in the footer (CC BY / CC BY-SA licences require attribution) unless replaced with Sebastian’s own photos
