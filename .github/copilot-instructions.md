# Repository Instructions

## Project
- This is a Jekyll 4.3 site published with GitHub Pages.
- Page content lives in `index.md` and `pages/*.md`; navigation order and page labels live in `_data/navigation.yml`.
- `_layouts/default.html` and `_layouts/page.html` provide the shared page structure.
- Site styles are in `assets/css/style.css`; palette and typography settings are defined in its `:root` block.

## Content and links
- Write for non-technical audiences learning communication theory and its application to contemporary communication problems, especially AI.
- Pages use YAML front matter with `layout: page`, a title, a permalink, and an optional lead. Use Markdown headings without skipping levels; the layout supplies the page's `h1`.
- When adding a page, add its title and URL to `_data/navigation.yml` in the intended reading order.
- Use Jekyll's `relative_url` filter for internal links and image paths so project-site base paths work.
- Give informative images meaningful alt text; use empty alt text only for decorative images.

## Accessibility and styling
- Preserve the site's accessibility conventions: semantic landmarks, skip link, labelled navigation, visible focus indicators, reduced-motion support, and adequate text contrast.
- Follow the existing CSS variables and styles rather than introducing a separate styling system.

## Build and verification
- Install dependencies with `bundle install`.
- Verify changes with `bundle exec jekyll build --baseurl /comm-primer`, matching the GitHub Pages build step.
- Run the local site with `bundle exec jekyll serve --baseurl /comm-primer`.
- There is no separate test suite configured; the Jekyll build is the primary project check.