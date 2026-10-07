# Alexander Du — academic website

This site uses [al-folio](https://github.com/alshedivat/al-folio). Its source is separate from the [CV repository](https://github.com/alexanderzdu/cv), which is included at `cv/` as a Git submodule. The deployment workflow compiles `cv/cv.tex` and publishes the resulting PDF at `/assets/pdf/cv.pdf`.

## Publishing

The site will be available at https://alexanderzdu.github.io/ from the `alexanderzdu.github.io` repository. Set **Settings → Pages → Build and deployment → Source** to **GitHub Actions**. Push changes to `main` to run `.github/workflows/deploy.yml`, which builds and deploys the site.

To update the published CV after changing the CV repository, advance the submodule pointer in this repository and push the site commit. A push to the CV repository alone does not change the site's pinned CV version.

## Local build

```sh
git submodule update --init
latexmk -pdf -interaction=nonstopmode -halt-on-error -cd cv/cv.tex
cp cv/cv.pdf assets/pdf/cv.pdf
bundle install
npm ci
bundle exec jekyll serve
```

The PDF copy is ignored by Git. Jekyll and npm dependencies are defined by the upstream template's `Gemfile` and `package-lock.json`.
