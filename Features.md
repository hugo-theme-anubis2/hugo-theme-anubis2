# Anubis2 features

See the [README](README.md) for installation and [PARAMS.md](PARAMS.md) for configuration and defaults.

## Reading and navigation

- Light, dark, and system-following color modes with a manual switcher.
- Multilingual pages and language switching.
- Collapsible table of contents, post summaries, related posts, and RSS.
- Mobile navigation stays on one line and scrolls horizontally when needed.
- Mobile article titles and language links occupy separate lines; metadata wraps naturally.
- Wide data tables and code blocks scroll within the reading column.
- Figure captions, smaller muted footnotes, and decorative article link icons.

The mobile and article styling above was added in [d1e038d](https://github.com/hugo-theme-anubis2/hugo-theme-anubis2/commit/d1e038d), after `v1.8.0`. It is available on `main` and revisions containing that commit.

## Technical writing

- Syntax highlighting, line numbers, highlighted lines, and code copying.
- Mermaid fenced code blocks with light/dark theme handling.
- MathJax, enabled with page front matter `math: true` or the global `enablemathglobally` option.
- Styled inline code, keyboard shortcuts, blockquotes, and callout shortcodes.
- Optional human-written declaration badge via `humanDeclared: true`.

## Integrations and customization

- Comments: Giscus, Disqus, and Utterances. Giscus follows the site's color mode.
- Analytics: Google Analytics and Umami, included only in production builds.
- Social icons, including custom SVG icons.
- Custom CSS, optional Sass/SCSS, and custom JavaScript.
- Canonical URLs, translated-page alternate links, and structured data.

## Example content

The [example site](example-site/content/posts/) includes Markdown, code, math, diagram, and summary-rendering examples. These are demonstration fixtures, not a claim of automated test coverage.
