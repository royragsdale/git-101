# Git 101

An introduction to `git` for SIGSAC.

## Slides

This repository contains the slides for a `git` presentation to SIGSAC. The
slides are generated with [hugo][h] static site generator using the
[reveal-hugo][t] theme which nicely wraps the [reveal.js][r] library.

[h]:https://gohugo.io/
[t]:https://themes.gohugo.io/reveal-hugo/
[r]:https://revealjs.com/#/

All the slides content is in plain text [Markdown][m] files that you can browse
[here][s].

If you have `hugo` installed you can locally present with

```
cd slides
hugo server
```

Then just visit <http://127.0.0.1:1313> in your browser.

[m]:https://daringfireball.net/projects/markdown/
[s]:.slides/content/home/

The slides were exported to pdf using the [decktape][d] docker container with
the following command.

```
docker run --rm --net=host -v $(pwd):/slides:rw,Z --shm-size 2G \
astefanutti/decktape:2.8.6 -s 1600x1200 \
http://localhost:1313 slides.pdf
```
