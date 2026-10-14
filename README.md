# bjornthorarnarson.com

Personal academic website, built with [Quarto](https://quarto.org) and hosted on GitHub Pages.
The built site is in `docs/`; everything else is the source you edit.

## Everyday updates

All of these are plain text files. Edit, save, then build (next section).

| To change… | Edit |
|---|---|
| A news item (submission, revision, talk, publication) | Add a file in `news/`: copy an existing one, change `title`, `date`, `datelabel`, `categories`, `description`. It appears on Home, News and in the RSS feed. |
| Any paper: title, status, abstract, coauthor links, PDFs, media, citation | `data/papers.yml`. `type:` decides the group (`publication`, `working-paper`, `wip`); when a paper is accepted, change its `type` and `venue`. |
| Topic filters on the Research page | The `topics:` list of each paper (the buttons are in `research.qmd`) |
| Talks | `data/talks.yml`. Give a talk an `iso:` date and it shows as upcoming, with a countdown, until that day passes; `paper:` links it to a paper id. |
| A paper's own page (plain-language summary, slides, citation) | `papers/<name>.qmd`; copy `papers/growing-together.qmd` for a new one and set `page:` in the `.yml` |
| About and Teaching page text | `about.qmd`, `teaching.qmd` (the CV is only the PDF, see below) |
| Swedish / Icelandic pages | `sv/index.qmd`, `is/index.qmd` |
| CV PDF | Replace `files/Arnarson_CV.pdf` |
| Photo | Replace `images/bjorn.jpg` |
| Colours, fonts, spacing | `styles/site.scss` |
| What AI tools read about you | `llms.txt` (and the profile block in `_includes/head.html`) |

A status beginning with `R&R` gets the gold tag automatically; any other status gets a grey tag.
Interactive parts (filters, search, abstract/cite toggles, countdowns) live in `_includes/site.html`.

## Build and preview

In the VS Code terminal, from this folder:

```
quarto preview      # live preview in the browser while you edit
quarto render       # build the final site into docs/
```

## Publish

After `quarto render`, open the Source Control panel in VS Code, write a one-line message
(e.g. "Add JPE news item"), click **Commit**, then **Sync Changes**. GitHub Pages rebuilds the
live site within a minute or two. Nothing else is needed.

## Address and domain

The site is live at https://www.bjornthorarnarson.com (repository `Bjorci/Bjorci.github.io`, GitHub Pages
serving `main` / `docs`; https://bjorci.github.io forwards there). The domain is registered and its DNS is
managed at Bluehost: the bare domain has four A records (185.199.108.153 to 185.199.111.153) and `www` is a
CNAME to `bjorci.github.io`. The `CNAME` file in this folder holds the custom domain and must stay listed under
`resources` in `_quarto.yml`, or a rebuild drops it and the site falls back to bjorci.github.io. The domain
is verified in the Bjorci account's Pages settings (TXT record `_github-pages-challenge-Bjorci`); keep that
record. The email (MX) records at Bluehost are unrelated to the site and must be left alone.

## Things still to fill in

Search the source for `[` placeholders and `TODO` comments: abstracts, plain-language summaries,
exact dates for some news items, talk dates, supervision counts, the Google Scholar / RePEc /
LinkedIn / ORCID links (also add them to `sameAs` in `_includes/head.html`).
