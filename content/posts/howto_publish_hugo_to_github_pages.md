---
title: "Setup Github Pages with Hugo static site generator and Visual Studio Code"
date: 2022-06-28T13:37:00+02:00
draft: false
---

# Setup Github Pages with Hugo static site generator and Visual Studio Code

- Create special GitHub repo for GitHub-Pages and clone it in VSC workspace
- Go to repo folder on local machine and create Hugo site. Use --force since the .git files are already there
    - `hugo new site . --force`
- add theme Ananke
    - `git submodule add https://github.com/theNewDynamic/gohugo-theme-ananke.git themes/ananke`
    - `echo theme = \"ananke\" >> config.toml`
- change publication directory to "docs" to align with settings in GitHub pages
    - `echo publishDir = \"docs\" >> config.toml`
- test Hugo
    - `hugo new posts/hello-world.md`
- preview on localhost
    - `hugo server -D`
- publish on localhost
    - `hugo` or `hugo -D`
- setup github pages
    - on github.com in your repository: Settings > Pages:
    - Source: Branch master, Folder docs
- in the docs folder, create an empty `.nojekyll` file to prevent jekyll workflow on github pages
    - `cd docs`
    - `touch .nojekyll`
- committing changes
    - `git add -A`
    - `git commit -am "Hello World and .nojekyll"`
    - `git push`

## Workflow new page
`hugo new posts/name.md`
- edit content
- publish
    - `git add -A`
    - `git commit -am "message"`
    - `git push`

## Workflow new publication
- publish current version: 
    - `hugo`
    - `git add -A`
    - `git commit -am "message"`
    - `git push`
