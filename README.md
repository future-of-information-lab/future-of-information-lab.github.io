# FOiL website

The website for the Future of Information Lab (FOiL), School of Information Sciences, University of Illinois Urbana-Champaign.

Plain HTML and CSS with no build step, ready for GitHub Pages.

## Pages

| File | Page |
| --- | --- |
| `index.html` | About: lab intro, the three research directions in brief, news |
| `research.html` | The three research directions, with current themes and example papers |
| `members.html` | Lab members |
| `join.html` | How to join as a PhD student, or as an undergraduate or MS student |

Shared styles live in `assets/css/foil.css`. The logo mark is in `assets/logo/`: `foil-mark.png` for day mode and `foil-mark-night.png` (plum swapped for blush) for night mode. The lab name beside it is live text in Newsreader. `favicon.png` and `apple-touch-icon.png` sit at the root. Member photos are in `assets/people/`.

## Editing

- **Header and footer** are repeated on every page. If you change one, change all four.
- **Sticky header**: the top band shows the full lab name. Once it scrolls away, the menu bar pins to the top and a small logo with "FOiL" slides in (a short script at the bottom of each page adds the `is-stuck` class). On phones the day/night button sits in the top band so the pinned bar has room for the menu. On narrow phones (420 px and below) the pinned bar shows the logo mark without the "FOiL" text, so all four menu items fit.
- **News items** go at the top of the `<ul class="news">` list in `index.html`, newest first.
- **New members**: copy a `<li class="person">` block in `members.html`. Add a square photo (at least 400 × 400 px) to `assets/people/`.
- **Example papers** on the Research page are `<li class="paper">` cards: title, venue, a one- or two-sentence summary, and a "Read the paper" button.
- **Day/night mode**: the toggle in the header sets `data-theme` on the page and remembers the choice in the visitor's browser. Until someone clicks it, the site follows their system setting.
- **After editing `foil.css`**, change the `?v=` value in the stylesheet link on all four pages (any new value works, e.g. today's date). Browsers keep the stylesheet for up to 10 minutes, so without a new value, returning visitors can see new pages with old styles.
- **Colours** are tokens at the top of `foil.css`. Components use the tokens, never hex values, so a colourway change only touches the `:root` block.

## Publishing on GitHub Pages

1. Push this folder to the root of a GitHub repository.
2. In the repository, go to **Settings → Pages**, choose **Deploy from a branch**, and pick `main` with the `/ (root)` folder.
3. The site appears at `https://<org-or-user>.github.io/<repo>/` within a minute or two.

The empty `.nojekyll` file tells GitHub Pages to serve the files as they are.

## Preview locally

```bash
python3 -m http.server 8000
```

Then open http://localhost:8000.
