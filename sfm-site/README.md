# Stories from SFM

Student publication of the School of Future Media, HKU.
Plain HTML and CSS. No build step, no dependencies.

## Structure

    index.html          Home, mosaic grid
    articles.html       Full archive
    authors.html        Author cards
    about.html          About and editorial policy
    style.css           Every style on the site
    stories/            One file per article
      mtr.html
      language.html
      typhoon.html
      sleepover.html
      fire.html
      payments.html
    img/                Covers, logo, photos
      mtr.svg  language.svg  typhoon.svg
      sleepover.svg  fire.svg  payments.svg
      sofm-logo-white.png
      about-eliot-hall.jpg

These sit at the root of the repository. `index.html` must be top level
or Vercel returns 404 at the root.

## Adding an article

1. Copy any file in `stories/` and rename it, e.g. `stories/ferry.html`.
2. Replace the headline, byline, date and body text.
3. Add a cover image to `img/` and point the two `src` attributes at it,
   once in the hero and once nothing else. Paths from inside `stories/`
   start with `../img/`.
4. Add a card to the grid in `index.html` and `articles.html`.
   Copy an existing `<a class="card">` block and change the four values.
5. Update the previous and next links at the foot of the neighbouring
   articles.

## Editing the look

`style.css` is in numbered sections:

    1      colours, fonts, nav height, grid gap
    3      the dark fixed top bar
    4      the home page mosaic
    9-11   the article page
    12-16  interior pages, authors, about photo

Change the accent colour, logo size or tile spacing in section 1 only.

The mosaic repeats every 6 cards so rows always close at full width:

    8+4  |  6+6  |  6+6

Columns are twelfths. Edit the `nth-child(6n+...)` rules in section 4.

## Deploying

Push to GitHub. In Vercel, import the repository. No build command, no
framework preset. Every push to main redeploys.

## Still to do

- Publication dates are estimates. Replace with real ones.
- Author bios are empty on `authors.html`.
- Covers are generated graphics, not photographs. Swap in real images
  when students supply them.
