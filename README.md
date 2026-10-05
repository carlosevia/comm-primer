# Comm Primer

A Jekyll website that introduces non-technical audiences to schools of communication theory and applies them to 21st-century communication problems, particularly involving AI. Published with GitHub Pages at <https://carlosevia.github.io/comm-primer/>.

## Structure

| Path | Purpose |
|---|---|
| `_config.yml` | Site settings (`url`, `baseurl`, `github_username`, `repository`) |
| `index.md` | Home page |
| `pages/*.md` | The six subpages |
| `_data/navigation.yml` | Menu and previous/next order |
| `_layouts/` | HTML templates (`default.html`, `page.html`) |
| `assets/css/style.css` | Styles; palette variables at top |
| `assets/images/` | Put your images here |

## Deployment

1. In the GitHub repo go to **Settings → Pages → Source** and choose **GitHub Actions**.
2. Every push to `main` runs `.github/workflows/jekyll.yml`, which builds and deploys the site.
3. If you rename the repo or change username, update `url`, `baseurl`, `github_username` and `repository` in `_config.yml`. `baseurl` must be `/<repository-name>`.

## Writing content

Edit the Markdown files in `pages/` (and `index.md`). The top block ("front matter") holds:

```yaml
---
layout: page
title: "Page title"          # shown as the h1
permalink: /my-page/         # URL
lead: "Intro sentence."      # optional large opening line
---
```

Below it, write Markdown: `##` for sections (the page title is already `h1`; don't skip heading levels), `*italics*`, `**bold**`, `[link](https://example.com)`.

### Adding a page
1. Create `pages/new-page.md` with the front matter above.
2. Add an entry (`title`, `url`) to `_data/navigation.yml`. Order there is menu order.

### Adding images
1. Copy the file to `assets/images/`.
2. Insert it, **always with meaningful alt text** (use `alt=""` only for purely decorative images):

```html
<figure>
  <img src="{{ '/assets/images/photo.jpg' | relative_url }}" alt="What the image shows">
  <figcaption>Optional caption.</figcaption>
</figure>
```

Use `relative_url` for all internal links and images so they work under the `/comm-primer` base path.

## Customizing the CSS

Edit the variables in the `:root` block at the top of `assets/css/style.css`: `--color-primary`, `--color-accent`, `--color-link`, `--color-bg`, `--color-text`, `--font-body`, `--font-heading`, `--max-width`, `--base-size`. Keep text/background contrast at least 4.5:1 (WCAG AA).

## Accessibility features

Skip link, landmarks (`banner`, `main`, `contentinfo`), labelled `nav`, `aria-current="page"`, visible focus outlines, reduced-motion support, relative font sizes, `lang` attribute.

## Running locally

```bash
bundle install
bundle exec jekyll serve --baseurl /comm-primer
```
Open <http://127.0.0.1:4000/comm-primer/>.
