# Anubis2 configuration reference

Theme options belong under `[params.anubis2]` in `hugo.toml` (or the equivalent YAML/JSON namespace). Hugo normalizes keys in `params`: `colorTheme` and `colortheme`, for example, refer to the same option. These docs and the example configurations use lowercase theme keys for consistency. CamelCase does not require a case-only migration.

The defaults below come from [params-helper.html](layouts/_partials/params-helper.html). The minimal example explicitly chooses `colortheme = "auto"`; the theme's fallback when the setting is omitted is `"light"`.

## Theme options

| Key | Default | Meaning |
| --- | --- | --- |
| `colortheme` | `"light"` | `"auto"`, `"light"`, or `"dark"`; auto follows the system until the reader chooses a mode. |
| `enablecolorthemeswitcher` | `true` | Show the manual color-mode button. |
| `enablecopycodebutton` | `true` | Show the copy button for highlighted code. |
| `enablesummary` | `true` | Show article summaries in post lists. |
| `enablereadmorebutton` | `false` | Show a read-more link for truncated summaries. |
| `enablerssicon` | `true` | Show the RSS icon when the home page has an RSS output. |
| `hidefooterattribution` | `false` | Hide the Hugo/theme attribution. |
| `readnextposts` | `0` | Number of related posts to show; `0` disables the section. |
| `tocwordcount` | `200` | Show a nonempty table of contents at or above this word count; `0` disables automatic display. |
| `openinnewtab` | `true` | Open Markdown links in a new tab, including internal links; does not affect site navigation. |
| `enablemathglobally` | `false` | Load MathJax globally instead of opting in per page. |
| `socialicons` | `[]` | Social links using `{ id, url }`; see below. |
| `customcss` | `[]` | CSS/Sass paths relative to `assets/`, or remote stylesheet URLs. Loaded after theme styles. |
| `customjs` | `[]` | JavaScript paths relative to `assets/`, or remote script URLs. |
| `csstranspiler` | `"libsass"` | Custom Sass compiler: `"libsass"` or `"dartsass"`. Plain CSS does not invoke a compiler. |
| `police` | `false` | Optional Chinese public-security registration text. |
| `icp` | `false` | Optional Chinese ICP registration text. |
| `services` | none | Comment and analytics service tables; see below. |

For Sass, use `csstranspiler = "dartsass"` after installing [Dart Sass](https://gohugo.io/functions/css/sass/#dart-sass) on the build host. The compatibility default `libsass` requires Hugo extended and is deprecated by Hugo. No Sass installation is needed for built-in or custom plain CSS.

## Social icons

Use an icon `id` and an explicit URL:

```toml
[params.anubis2]
socialicons = [
  { id = "github", url = "https://github.com/your-name" },
  { id = "email", url = "mailto:you@example.org" }
]
```

Known IDs are listed in [data/social.yaml](data/social.yaml). Known providers also accept `{ id, name }`, where `name` is substituted into the provider's URL template; explicit URLs are preferable. Custom IDs use SVG files at `static/tabler-icons/<id>.svg`. The `docs` icon is built into the icon renderer. Check [the icon renderer](layouts/_partials/features/font-awesome.html) when adding an icon.

## Page options

These belong in a page's front matter, not in `[params.anubis2]`:

- `math: true` opts a page into MathJax.
- `toc: true` or `toc: false` overrides the automatic word-count threshold. A page still needs headings to produce a table of contents.
- `humanDeclared: true` displays the human-written declaration badge.
- `draft: true` requires `hugo server -D` for local preview and excludes the page from a normal production build.

Mermaid diagrams use fenced code blocks with the `mermaid` language; there is no theme parameter to enable them.

## Services

Adding a table under `params.anubis2.services.<name>` enables that service. Remove the whole table to disable it; an empty table still enables validation. Required fields are checked during rendering, including in development builds.

The built-in comment integrations are **Giscus, Disqus, and Utterances**. Configure the one you intend to use. Analytics integrations are **Google Analytics and Umami**.

### Giscus

```toml
[params.anubis2.services.giscus]
repo = "owner/repository"
repoid = "YOUR_REPOSITORY_ID"
category = "General"
categoryid = "YOUR_CATEGORY_ID"
datamapping = "pathname"
language = "en"
```

Obtain the repository/category values from [giscus.app](https://giscus.app/). `repo`, `repoid`, `category`, and `categoryid` are required. `datamapping` defaults to `"og:title"`, and `language` defaults to `"en"`. The widget follows the site's color mode.

`lazyload` defaults to `false`. The current implementation passes it as a script attribute; it does not implement viewport-based deferred loading.

### Disqus

```toml
[params.anubis2.services.disqus]
shortname = "YOUR_DISQUS_SHORTNAME"
```

`shortname` is required.

### Utterances

```toml
[params.anubis2.services.utterances]
repo = "owner/repository"
theme = "preferred-color-scheme"
issueterm = "pathname"
```

All three fields are required. `issueterm` accepts `pathname`, `url`, `title`, or `og:title`. An optional `label` is applied to the discussion issue. Supported themes are `github-light`, `github-dark`, `preferred-color-scheme`, `github-dark-orange`, `icy-dark`, `dark-blue`, `photon-dark`, `boxy-light`, and `gruvbox-dark`.

### Google Analytics

```toml
[params.anubis2.services.googleanalytics]
gtag = "G-YOUR_MEASUREMENT_ID"
```

`gtag` is required.

### Umami

```toml
[params.anubis2.services.umami]
id = "YOUR_WEBSITE_ID"
url = "https://umami.example.org/script.js"
datacache = false
dnt = false
# shareurl = "https://umami.example.org/share/YOUR_SHARE_ID"
```

`id` and `url` are required. `datacache` and `dnt` default to `false`. Optional `shareurl` adds a statistics link in the footer.

Analytics scripts are injected only when `hugo.IsProduction` is true. A normal `hugo` build uses production; `hugo server` uses development. Use `hugo --environment production` when explicitly checking the production output.

## Migrating older configurations

The important migration is the namespace and, for some options, the option name. Changing capitalization alone is unnecessary.

| Old setting under `params` | Current setting under `params.anubis2` |
| --- | --- |
| `colorTheme` | `colortheme` |
| `colorThemeSwitcher` | `enablecolorthemeswitcher` |
| `readMore` | `enablereadmorebutton` |
| `rssIcon` or `rssAsSocialIcon` | `enablerssicon` |
| `social` | `socialicons` using `{ id, url }` entries |
| `math` | `enablemathglobally` |
| `customCSS` / `customJS` | `customcss` / `customjs` |
| `disableSummary` | `enablesummary` with the boolean inverted |

Other theme settings such as `hidefooterattribution`, `readnextposts`, `police`, and `icp` also belong inside `params.anubis2`. See the [full example](example-site/hugo.full.toml) when merging configuration changes; replace demo service accounts before publishing your own site.
