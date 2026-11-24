# Panda Exteriors one-page roof quote

A one-page ad landing page for Panda Exteriors, modeled on the PJ Fitzpatrick Instagram funnel Scott sent.
Someone taps an ad, answers 5 quick questions and sees a real price range for all three Panda packages on the spot,
then books a free inspection or a video walkthrough.

- `index.html`: the whole page. Everything Scott might change is in the `CONFIG`, `PACKAGES`, `SIZES`, `REVIEWS` and `FAQ`
  blocks at the top of the script.
- `img/`: Panda's own job photos and logo, taken from the pandav1 site copy.
- `vercel.json`: tells search engines not to index the page while it's a demo.

## Before it runs as a real ad

- **Offer.** `CONFIG.offer` is a sample ($2,000 off, "Black Friday Roofing Event"). Set Scott's real offer and terms,
  or set `amount` to 0 to hide every offer box.
- **License number.** Maryland requires the MHIC number on home improvement ads. Put it in `CONFIG.license`.
- **Where leads go.** `CONFIG.leadEndpoint` is empty, so the form only shows a confirmation. Point it at an n8n webhook
  or the Panda CRM; the form posts JSON with the contact details, quiz answers, price ranges shown, offer and page URL.
- **Demo ribbon.** Set `CONFIG.demo` to false.
- **Indexing.** Remove `vercel.json` (and the robots meta tag) only if the page should show up in Google. Ad landing
  pages usually stay out of the index.

## Where the numbers come from

- Package prices per square: the active "Panda Exteriors Price Book" in the Panda CRM (read Nov 23, 2026), the same
  numbers as Panda Roof Builder: Systems Plus $840, HDZ Golden Pledge $997.50, Presidential HDZ $1,043.70.
- Roof size by home size (`SIZES`) is a rough rule of thumb, so the ranges are wide until the roof is measured.
- Stats (GAF Presidential Master Elite top 0.1%, 1,500+ five star reviews, 10,000+ projects) are Scott's corrected
  figures from the Roof Builder. The 4.8 Google rating and 1,067 reviews are the main office listing as of Oct 2026.
- Reviews are real Google reviews from Panda's review list, trimmed only with "…".

## Ad links

`?size=small`, `?size=medium`, `?size=large` or `?size=xl` pre-selects the home size, so an ad with
"Tap your roof size" buttons can link each button straight to its price.
