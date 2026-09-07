# Appliance Energy Consumption Website

A small 3-page website about appliance energy consumption in the Australian
market, built with plain HTML, CSS, and vanilla JavaScript (no frameworks).

## Folder structure

```
/
  index.html            Home page (overview + FAQ accordion)
  televisions.html       Televisions page (dataset table + energy calculator)
  about.html              About Us page
  assets/
    css/style.css        All site styling (external stylesheet)
    js/main.js            Footer year + FAQ accordion logic
    js/calculator.js      Interactive appliance energy calculator logic
    img/PowerIcon.png     Site logo (placeholder — see note below)
  README.md
```

## Running the site

No build step or server is required.

1. Open the `appliance-energy-site` folder in VS Code.
2. Open `index.html` directly in a browser, **or** install the VS Code
   "Live Server" extension, right-click `index.html`, and choose
   **Open with Live Server** (recommended — some browsers restrict
   JavaScript `fetch`/module features on `file://` URLs, though this
   project doesn't use any, so opening the file directly also works fine).
3. Use the navigation bar to move between **Home**, **Televisions**, and
   **About Us**. Clicking the logo always returns you to Home.

## About the logo

`assets/img/PowerIcon.png` in this project is a **placeholder** power-symbol
icon generated to match the site's navy/amber colour palette. If your
assignment provided an actual `PowerIcon.png` file to download, replace the
placeholder file at `assets/img/PowerIcon.png` with that file (keep the same
filename, or update the `<img src="...">` references in each HTML page).

## Notes on requirements coverage

- **3 HTML pages** — `index.html`, `televisions.html`, `about.html`.
- **Top navigation on every page** — logo (top-left, links home), hover
  effect, and an `active` class marking the current page.
- **Home page FAQ accordion** — hidden by default, toggled via
  `assets/js/main.js`, one JS file shared across pages.
- **External CSS only** — all styling lives in `assets/css/style.css`;
  no inline `style="..."` is used for visual styling (a couple of
  one-off inline `padding` overrides on the About page can be moved into
  the stylesheet as utility classes if you'd like to be strict about it).
- **Footer on every page** — current year (via JavaScript), author name
  placeholder, and a Generative AI acknowledgement.
- **Optional JS challenge — Appliance Energy Calculator** (on the
  Televisions page): appliance model dropdown or manual wattage, hours/day,
  and price (c/kWh) as inputs; computes daily, monthly, and yearly kWh plus
  yearly cost; results panel updates in place (no `alert()`); inputs are
  validated with inline error messages; works correctly after a page
  refresh since it recalculates fresh from the form each time.

## Things to personalise before submitting

- Replace "Your Name" in each page's footer and in `about.html`.
- Replace placeholder statistics/content with real, sourced data if your
  assignment requires citations.
- Swap in the real `PowerIcon.png` if one was provided separately.
- Update or remove the GenAI acknowledgement wording to accurately reflect
  how you used AI assistance.
