# Making Waves documentation repo

## How to add content

The page is setup as a blog where each workshop is represented as a blog post.

In `content/posts/` are all the posts documenting past workshops or performances named for their semester or event name. (Other files in `content` are used for other pages, such as about or other, future pages.)

They are simple Markdown files with a bit of extra info at the top used for sorting and permalink creation.

To create a new post, feel free to copy and adjust this snippet (yes, the +++ are part of it):

``` text
+++
title = "The title used, automatically added to the page"
date = "2025-04-23"
author = "Author name"
+++

```

Then just write the documentation in Markdown underneath it.

You can add images and videos and other media that you want to directly include in the post in two places:
- `/content/posts/` just alongside the post itself or in an extra folder
- `/static/` and then also a folder to organize material

To just store files that you want to link to but not include, you can add them to `/data/`.

When you're done, commit all your changes and push to master. (Or just do everything in the web interface.) Then you're done.

Then the GitHub action pipline will automatically re-build and publish the website after a few minutes.



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

You can follow the progress of the [Actions here](https://github.com/ctechfilmuniversity/making-waves/actions).
