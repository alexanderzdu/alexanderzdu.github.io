# Build locally

```sh
git submodule update --init
latexmk -pdf -interaction=nonstopmode -halt-on-error -cd cv/cv.tex
cp cv/cv.pdf assets/pdf/cv.pdf
docker compose run --rm jekyll bundle exec jekyll build
```

To preview the site at http://localhost:8080/:

```sh
docker compose up
```

## Deploy

Create and push the `alexanderzdu.github.io` repository:

```sh
gh repo create alexanderzdu.github.io --public --source=. --remote=origin --push
```

GitHub Free requires a public repository for Pages. With GitHub Pro, replace `--public` with `--private` if you prefer. In the repository, set **Settings → Pages → Build and deployment → Source** to **GitHub Actions**. If the first workflow run fails before Pages is enabled, rerun **Deploy site** from the Actions tab.

The site will be at https://alexanderzdu.github.io/. Later pushes to `main` deploy automatically.
