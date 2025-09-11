# Parameters of Anubis2

This theme uses lowercase keys for all configuration under `params.anubis2`.
CamelCase keys from prior versions are no longer read; use the lowercase
forms listed below. The helper will emit warnings when legacy keys are found.

Top-level keys under `params.anubis2` (all lowercase):

- colortheme: "auto" | "light" | "dark"
- enablecolorthemeswitcher: boolean
- enablecopycodebutton: boolean
- enablereadmorebutton: boolean
- hidefooterattribution: boolean
- enablerssicon: boolean
- readnextposts: integer (>= 0)
- socialicons: array of `{ name, url }`
- enablemathglobally: boolean
- customcss: array of asset paths (e.g. "css/foo.css")
- customjs: array of asset paths (e.g. "js/bar.js")
- enablesummary: boolean
- tocwordcount: integer (words threshold to show ToC)
- openinnewtab: boolean
- services: service-specific config (see below)

Services configuration (all lowercase keys):

- googleanalytics
  - gtag: string (required in production when enabled)

- umami
  - id: string (required)
  - url: string (required)
  - datacache: boolean
  - dnt: boolean
  - shareurl: string (optional; shows a stats link in footer when set)

- giscus
  - repo: string (required)
  - repoid: string (required)
  - category: string (required)
  - categoryid: string (required)
  - datamapping: string (default: "og:title")
  - language: string (default: "en")
  - lazyload: boolean (default: false)

- utterances
  - repo: string (required)
  - theme: string (required; one of: github-light, github-dark, preferred-color-scheme, github-dark-orange, icy-dark, dark-blue, photon-dark, boxy-light, gruvbox-dark)
  - issueterm: string (required; one of: pathname, url, title, og:title)
  - label: string (optional)

- disqus
  - shortname: string (required)

Enabling a service

To enable a service, add a table under `params.anubis2.services.<servicename>`.
The theme treats presence of the service table as enabled. Example (TOML):

```toml
[params.anubis2.services.googleanalytics]
gtag = "G-XXXX"

[params.anubis2.services.umami]
id = "<uuid>"
url = "https://umami.example.com/script.js"
shareurl = "https://cloud.umami.is/share/..."
```

Production guards

Analytics partials are only injected when `hugo.IsProduction` is true. Use
`hugo --environment production` or set `HUGO_ENV=production` for deployment.
