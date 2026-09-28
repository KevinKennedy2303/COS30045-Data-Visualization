# Appliance Energy Consumption Website

A small 3-page website about appliance energy consumption in the Australian
market, built with plain HTML, CSS, and vanilla JavaScript (no frameworks).

## Data story

**Audience.** The Televisions page is written for two groups who both land
on it for a practical reason rather than to study a chart:

- **Australian households shopping for a new TV**, who want a straight
  answer before they buy — will a bigger screen actually cost more to run,
  and by how much?
- **Retail sales staff and appliance buyers**, who need to know which of the
  76 registered TV brands genuinely reflect what customers buy, so floor
  space, stock and recommendations line up with real demand rather than
  brand count.

Neither group is a data analyst. Both are comfortable with everyday numbers
— dollars, screen inches, "roughly how many times more" — but not with
statistical language, so the page favours plain comparisons (percent share,
average kWh per year, "7x more") over raw chart axes.

**Their interest in the visualisation.** Each group asks a different
question of the same dataset:

- Shoppers want the size-vs-energy story: is the jump from a 55" to an 85"
  screen small and forgettable, or big enough to change what they buy? The
  screen-size bar chart and the "7x" callout on the Televisions page answer
  this directly, and the calculator lets them plug in a specific model.
- Buyers and sales staff want the brand-share story: out of 76 brands, which
  ones actually match demand? The brand bar chart answers this by showing
  that Samsung, Kogan and LG alone cover 57% of all registered models,
  while the remaining 71 brands share the rest.

## About the data

- **Data source.** All figures come from the Australian Government's
  Energy Rating product registration database (the national scheme
  established under the *Greenhouse and Energy Minimum Standards
  (Televisions) Determination 2013*). The specific extract used here is a
  snapshot of 4,724 registered television models taken on 15 February 2026,
  pulled and cleaned via a KNIME workflow (`2026_TV_Data.knwf`).
- **Data processing.** Brand names were standardised (e.g. `SAMSUNG
  ELECTRONICS` and `Samsung` merged into one brand) before counting
  registrations per brand. Screen sizes were rounded and grouped into
  Small (&lt;50"), Medium (50–70") and Large (&gt;70") bands. Average yearly
  labelled energy consumption (kWh/year) was then calculated per band and
  per brand using KNIME's GroupBy/Pivot nodes and cross-checked in pandas.
  No individual data points were removed or altered beyond this cleaning
  and aggregation.
- **Privacy.** The dataset contains no personal or household information.
  It records manufacturer product registrations — brand, model number,
  screen size, technical specifications — which manufacturers are legally
  required to publish; there is no way to identify an individual owner or
  household from it.
- **Accuracy and limitations.** The data reflects *models registered for
  sale*, not actual retail sales volumes or real households' viewing hours,
  so "brand share" here means share of registered models, not share of
  units sold or market revenue. It's a single snapshot (15 Feb 2026), so
  it excludes anything registered after that date. Labelled energy figures
  are self-reported by manufacturers under a standard test procedure
  (AS/NZS 62087.1:2010) rather than measured independently, and real-world
  household energy use will vary with viewing hours, brightness settings
  and picture mode.
- **Ethics.** The dataset is drawn from a public government register that
  exists specifically for consumer transparency, so using it for consumer
  education matches its intended purpose. Comparisons are presented at the
  aggregate level (brand share, size-band averages) rather than singling
  out individual models, to avoid implying a quality judgement about any
  one product. No figures were reweighted or selectively filtered to
  favour a particular brand or narrative.

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

## AI Declaration

Generative AI (Claude, Anthropic) was used during this project for:

- Drafting the initial site structure, layout and CSS (HTML/CSS/JS scaffolding).
- Analysing the TV registration dataset (via a KNIME workflow and Python) to
  produce the brand-share and screen-size-vs-energy figures used in the
  Data story section and on the Televisions page.
- Drafting the storyboards, the Data story narrative above, and the
  contextual copy added to the Televisions and About pages.

All AI-assisted content and code was reviewed, and where noted, edited by
the author before submission. Update this declaration to accurately
reflect your own use of AI tools.

## Things to personalise before submitting

- Replace "Your Name" in each page's footer and in `about.html`.
- Replace placeholder statistics/content with real, sourced data if your
  assignment requires citations.
- Swap in the real `PowerIcon.png` if one was provided separately.
- Update or remove the GenAI acknowledgement wording to accurately reflect
  how you used AI assistance.
