# My first 'git sourced' blog

Today I wanted to apply 'GitOps' to my blogs.
Would it be possible, easy and benificial to develop blogs and content with
Markdown in a git repository while still using Wordpress for publishing the content?
That was the quest of the day :smile:

So here's my first 'git sourced' blog!

Source file in a [GitHub repo](https://github.com/marcvanandel/marcvanandel.nl-bliki/blob/main/my-first-git-sourced-blog.md)
and published static page in Wordpress on [marcvanandel.nl](https://marcvanandel.nl/my-first-git-sourced-blog/).

And? Does that work? Yes! It does! :smiley:

## Set up

The source of this page is a Markdown file in a public git repository.
This could be a private repository as well.
So first thing to do is preparing a git repository somewhere.
I'm just using GitHub for this one: [github.com/marcvanandel/marcvanandel.nl-bliki/](https://github.com/marcvanandel/marcvanandel.nl-bliki/).

Secondly you'll need a Wordpress site.
As you can see I'm using my [marcvanandel.nl](https://marcvanandel.nl) website for that :cool:
I have installed the [Documents from Git](https://wordpress.org/plugins/documents-from-git/) Wordpress plugin.
Source code and documentation is available in [GitHub](https://github.com/gis-ops/wordpress-markdown-git).

The last step is to apply the Wordpress plugin inside a page in your Wordpress site.
To have a 1-on-1 mapping between a Wordpress page and a Markdown file,
you create a new page inside your Wordpress site.
On this page you'll apply a 'shortcode' (DuckDuck is your friend :wink: ):

```
[git-github-markdown url="https://github.com/marcvanandel/marcvanandel.nl-bliki/blob/main/my-first-git-sourced-blog.md"]
```

Many other options to use and configure: see the official [documentation](https://github.com/gis-ops/wordpress-markdown-git).
