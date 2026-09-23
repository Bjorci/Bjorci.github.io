# bjornthorarnarson.com

Personal academic website, built with [Quarto](https://quarto.org) and hosted on GitHub Pages.
The built site is in `docs/`; everything else is the source you edit.

## Everyday updates

All of these are plain text files. Edit, save, then build (next section).

| To change… | Edit |
|---|---|
| A news item (submission, revision, talk, publication) | Add a file in `news/`: copy an existing one, change `title`, `date`, `datelabel`, `categories`, `description`. It appears on Home, News and in the RSS feed. |
| A working paper or its status (e.g. R&R → accepted) | `data/working-papers.yml` |
| A published article | `data/publications.yml` (move the paper here from working papers when it is accepted) |
| What shows under "Selected research" on Home | Add or remove `featured: true` on a paper |
| An abstract | The `abstract:` line of the paper in the `.yml` file |
| Upcoming or past talks | `data/talks.yml` |
| A paper's own page (plain-language summary, slides, citation) | `papers/<name>.qmd`; copy `papers/growing-together.qmd` for a new one and set `page:` in the `.yml` |
| About, Teaching, CV page text | `about.qmd`, `teaching.qmd`, `cv.qmd` |
| Swedish / Icelandic pages | `sv/index.qmd`, `is/index.qmd` |
| CV PDF | Replace `files/Arnarson_CV.pdf` |
| Photo | Replace `images/bjorn.jpg` |
| Colours, fonts, spacing | `styles/site.scss` |
| What AI tools read about you | `llms.txt` (and the profile block in `_includes/head.html`) |

A status beginning with `R&R` gets the gold tag automatically; any other status gets a grey tag.

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

## Moving bjornthorarnarson.com here

The site is live at https://bjorci.github.io (repository `Bjorci/Bjorci.github.io`, GitHub Pages
serving `main` / `docs`). To move the domain from Weebly: add the domain under the repository's
Settings → Pages → Custom domain, point the domain's DNS at GitHub Pages as GitHub instructs, then
replace `https://bjorci.github.io` with `https://www.bjornthorarnarson.com` in `_quarto.yml`,
`_includes/head.html`, `llms.txt`, `robots.txt` and `papers/*.qmd`, and render again.

## Things still to fill in

Search the source for `[` placeholders and `TODO` comments: abstracts, plain-language summaries,
exact dates for some news items, talk dates, supervision counts, the Google Scholar / RePEc /
LinkedIn / ORCID links (also add them to `sameAs` in `_includes/head.html`).
