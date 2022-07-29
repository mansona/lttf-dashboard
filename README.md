# lint-to-the-future-dashboard-action

The only parameter this action requries is the `folder` parameter. This is to specify a subdirectory for you gh-pages branch if required.

``` YAML
name: github pages
on:
  push:
    branches:
      - main

jobs:
  deploy:
    uses: mansona/lint-to-the-future-dashboard-action/.github/workflows/dashboard.yml@main
    with:
      folder: ''
```
