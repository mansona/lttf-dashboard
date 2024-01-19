# lttf-dashboard

This action is designed to quickly and easily setup your [lint-to-the-future](https://github.com/mansona/lint-to-the-future) dashboard on github pages.

To get started create a file `.github/workflows/lint-to-the-future.yml` and add the following to it: 

```yaml
name: Lint to the Future Dashboard

on:
  push:
    branches:
      - master
      - main

jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: mansona/lttf-dashboard@v2
        with:
          token: ${{secrets.GITHUB_TOKEN}}
```

**Note:** you need to provide the token so that the action is able to publish to github-pages.

The above workflow will automatically deploy your dashboard to `https://your-org-name.github.io/your-repo-name/` whenever a commit is pushed to `main` or `master`.


## Subfolder

If you are already using your github-pages deployment for your docs site and you want to publish the LTTF Dashboard in a subfolder you can pass `folder` in the options: 


```yaml
name: Lint to the Future Dashboard

on:
  push:
    branches:
      - master
      - main

jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: mansona/lttf-dashboard@restructure
        with:
          folder: '/lint-to-the-future'
          token: ${{secrets.GITHUB_TOKEN}}
```

**Note:** you must start your folder definition with a `/` or you will get a series of `404 Not Found` errors when you try to load your dashboard.
