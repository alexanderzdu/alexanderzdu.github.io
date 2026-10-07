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
