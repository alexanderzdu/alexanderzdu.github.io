# Alexander Du

Personal academic website for Alexander Du, a Ph.D. student in Computer Science at Duke University. My work spans machine learning systems, with a current focus on fine-grained GPU resource management.

**Website:** https://alexanderzdu.github.io/

The site uses [al-folio](https://github.com/alshedivat/al-folio), a Jekyll starter. It is a single page with an introduction and publications.

## Site content

| Path | Purpose |
| --- | --- |
| [`_pages/about.md`](_pages/about.md) | Homepage text, profile links, and page-specific styling |
| [`_bibliography/papers.bib`](_bibliography/papers.bib) | Publications and their links |
| [`_config.yml`](_config.yml) | Site settings |
| [`assets/img/`](assets/img/) and [`assets/pdf/`](assets/pdf/) | Profile photo, favicon, and slides |
| [`cv/`](cv/) | Git submodule pointing to the separate [CV repository](https://github.com/alexanderzdu/cv) |

The deployment workflow compiles `cv/cv.tex` and publishes the resulting PDF at `/assets/pdf/cv.pdf`. That generated PDF is ignored by Git.

## Preview locally

```sh
git submodule update --init
docker compose up
```

Open http://localhost:8080/. To preview the CV link locally, run `latexmk -pdf -interaction=nonstopmode -halt-on-error -cd cv/cv.tex` and copy `cv/cv.pdf` to `assets/pdf/cv.pdf`.

## Deployment

In the `alexanderzdu.github.io` repository, set **Settings → Pages → Build and deployment → Source** to **GitHub Actions**. Pushing to `main` runs [the deployment workflow](.github/workflows/deploy.yml), which builds the CV and site, then deploys the generated pages. If the first run starts before Pages is enabled, rerun it after changing the setting.

After updating the separate CV repository, run `git submodule update --remote cv`, commit the changed submodule pointer here, and push this repository. The site uses the CV revision pinned by that pointer.

The al-folio starter documentation and tooling remain in this repository. The original MIT license is retained in [LICENSE](LICENSE).
