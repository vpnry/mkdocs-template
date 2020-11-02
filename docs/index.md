# Git page with mkdocs-material

You are viewing a demo of this repository:

[https://github.com/vpnry/mkdocs-template](https://github.com/vpnry/mkdocs-template)

`mkdocs-material` ++ctrl+shift+m+k+d+o+c+s++ 

## Auto deploy to gh-pages branch with Github Action

References:

+ For full documentation visit [mkdocs.org](https://www.mkdocs.org).

+ mkdocs-material [https://squidfunk.github.io/mkdocs-material/](https://squidfunk.github.io/)

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

Like the one you are viewing now:

[https://vpnry.github.io/mkdocs-template](https://vpnry.github.io/mkdocs-template)


# Code highlight with `pymdownx`

- Javascript highlight line number 3 only

``` javascript hl_lines="3"

function hightLightWith(pymdownx) {
  let javascript = "Code highlight with pymdownx"
  const str = javascript + " and extra css docs/stylesheets/extra.css"
  return str
}

```

- Python and highlight ranges, line: 1-2 5-6

``` python hl_lines="1-2 5-6"

import os
print("This line is not highlighted")
print("This line is highlighted by adding python hl_lines='2'")
def returnYes:
  return "yes"
# This line is a comment.
  
```

- keyboard keys

++ctrl+alt+shift+del++

- mermaid graph

** You ned to enable mermaid first in `mkdocs.yml` **

```
References:

https://github.com/mermaid-js/mermaid/
https://github.com/squidfunk/mkdocs-material/issues/693#issuecomment-411885426
```


``` mermaid

graph TD
    A[Hard] -->|Text| B(Round)
    B --> C{Decision}
    C -->|One| D[Result 1]
    C -->|Two| E[Result 2]
    
```
