---
title: My first 'Git sourced' blog post
post_date: 2023-09-04
---
Today I wanted to apply 'GitOps' to my blogs. Would it be possible, easy and benificial to develop blogs and content with Markdown in a git repository while still using Wordpress for publishing the content? That was the quest of the day :smile:

So here's my first 'git sourced' blog!

Source file in a [GitHub repo](https://github.com/marcvanandel/marcvanandel.nl-bliki/blob/main/my-first-git-sourced-blog.md) and published static page in Wordpress on [marcvanandel.nl](https://marcvanandel.nl/my-first-git-sourced-blog/).

And? Does that work? Yes! It does! :smiley:

## Set up

The source of this page is a Markdown file in a public git repository. This could be a private repository as well. So first thing to do is preparing a git repository somewhere. I'm just using GitHub for this one: [github.com/marcvanandel/marcvanandel.nl-bliki/](https://github.com/marcvanandel/marcvanandel.nl-bliki/).

Secondly you'll need a Wordpress site. As you can see I'm using my [marcvanandel.nl](https://marcvanandel.nl) website for that 😎

My first try was with the [Documents from Git](https://wordpress.org/plugins/documents-from-git/) Wordpress plugin. Source code and documentation is available in [GitHub](https://github.com/gis-ops/wordpress-markdown-git). This worked fine ... for single blog posts, 'cause this plugin requires a 1-on-1 mapping between a Wordpress page and a Markdown file. You had to create a Wordpress page and apply `shortcode`s (DuckDuck is your friend :wink: ). This resulted into a published page, showing the Markdown content out of a GitHub file ... but nothing more.

Some time later I discovered the [Git it right](https://www.aakashweb.com/docs/git-it-write/) plugin. This is what I wanted in the first place!! This plugin even has a GitHub webhook feature which triggers an update in Wordpress to pull the changes of the configured set of Markdown pages and actually _creates_ these pages _inside_ Wordpress. Searching through the content of the GitHub managed Markdown files is now supported! Awesome :sunglasses:
