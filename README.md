# mkdocs-template

With [mkdocs-material](https://squidfunk.github.io/mkdocs-material/)

## Auto deploy to gh-pages branch with Github Action

References:

+ For full documentation visit [mkdocs.org](https://www.mkdocs.org).

+ mkdocs-material [https://squidfunk.github.io/mkdocs-material/](https://squidfunk.github.io/mkdocs-material/)

Create and add this code snippet to `YOU RPROJECT DIR/.github/workflows/main.yml`

``` yaml

# Create and add this to `YOU RPROJECT DIR/.github/workflows/main.yml`
# This code snippet is from (updated master -> main): https://squidfunk.github.io/mkdocs-material/publishing-your-site/

name: ci
on:
  push:
    branches:
      # - master does not work! as of 2020 it is renamed as main
      - main
jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - uses: actions/setup-python@v2
        with:
          python-version: 3.x
      - run: pip install mkdocs-material
      - run: mkdocs gh-deploy --force

```

> Remember to enable Github page for your project and choose gh-pages branch.

Your Github page will be something like:

 `https://your_github_username.github.io/project`

See live demo of this repo: [https://vpnry.github.io/mkdocs-template](https://vpnry.github.io/mkdocs-template)

