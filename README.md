# Alexander Du

This is my personal website, built with [al-folio](https://github.com/alshedivat/al-folio). [Visit the site](https://alexanderzdu.github.io/).

The homepage is in [`_pages/about.md`](_pages/about.md), and the publications are in [`_bibliography/papers.bib`](_bibliography/papers.bib). My CV lives in a [separate repository](https://github.com/alexanderzdu/cv) included here as a Git submodule at `cv/`.

## Preview locally

```sh
git submodule update --init
docker compose up
```

Open http://localhost:8080/. To preview the CV link locally, build and copy the PDF:

```sh
latexmk -pdf -interaction=nonstopmode -halt-on-error -cd cv/cv.tex
cp cv/cv.pdf assets/pdf/cv.pdf
```

## Deployment

Set **Settings → Pages → Build and deployment → Source** to **GitHub Actions**. Each push to `main` runs [the deployment workflow](.github/workflows/deploy.yml), which builds the CV PDF and site. If the first run starts before Pages is enabled, rerun it after changing the setting.

After updating the CV repository, run `git submodule update --remote cv`, then commit and push the changed submodule pointer here.
