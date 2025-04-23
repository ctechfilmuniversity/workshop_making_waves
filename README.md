# Making Waves documentation repo

## How to add content

@tbd

## Local setup

It is not necessary to run this locally, but you can.

The entire page is built using the [Hugo](https://gohugo.io/installation/) static site generator. [Install Hugo for your operating system]() clone the repository, `cd` into it and run either

``` shell
$ hugo build
```

for a complete build of the page, to be found in the dist folder.

Or

``` shell
$ hugo serve
```

for a development server that auto-refreshes.

Make any changes you want and commit to master. From there the GitHub action will take over.


## GitHub Actions pipeline

Github offers a free CI/CD pipeline (continuous integration/ continuous deployment) that you can configure directly through files in your repository.

In `.github/workflows` you find the `publish.yml` which documents the steps. Basically it's running hugo build and commits to the gh-pages branch, from which the website is served.
