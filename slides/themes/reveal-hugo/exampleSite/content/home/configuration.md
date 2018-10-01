+++
weight = 21
+++

# Configuration

Place configuration values in `config.toml` or a presentation's front matter (`_index.md`).

---

## Reveal.js themes

Themes control the look and feel of your presentation. Set the `theme` param to any [valid Reveal.js theme](https://github.com/hakimel/reveal.js/#theming).

```toml
[params.reveal_hugo]
theme = "moon"
```

---

## Use a custom theme

To use a custom Reveal.js theme, place the CSS file in the `static` directory and set the `custom_theme` param.

```toml
[params.reveal_hugo]
custom_theme = "reveal-hugo/themes/robot-lung.css"
```

---

## Bundled themes

reveal-hugo comes with 2 extra Reveal.js themes:

- [robot-lung](https://github.com/dzello/revealjs-themes#robot-lung) (this one)
- [sunblind](https://github.com/dzello/revealjs-themes#sunblind)

<br>
<small>
They live in the `static/reveal-hugo/themes` folder and also [on Github](https://github.com/dzello/revealjs-themes).
</small>

---

## Reveal.js params

Set **snakecase** versions of Reveal.js params, which will be camelized and passed to `Reveal.initialize`.

```toml
[params.reveal_hugo]
history = true
slide_number = true
transition = 'zoom'
transition_speed = 'fast'
```

[Full list of params](https://github.com/hakimel/reveal.js/#configuration)

---

## highlight.js themes

To change the syntax highlighting theme, set the `highlight_theme`
to a valid [highlight.js theme name](https://highlightjs.org/static/demo/).

```toml
[params.reveal_hugo]
highlight_theme = "zenburn"
```

---

## Extending the layout

Use partials to add HTML to the page for one or all presentations at a time.

<small>
💡 This is the recommended way to add script and style tags to customize your presentations.
</small>

---

Here is where partials go for different presentations and places on the page.
<br><br>

| Presentation | Before &lt;/head&gt;            | Before &lt;/body&gt;            |
|--------------|---------------------------------|---------------------------------|
| All          | reveal-hugo/head.html           | reveal-hugo/body.html           |
| Root         | home/reveal-hugo/head.html      | home/reveal-hugo/body.html      |
| Section      | {section}/reveal-hugo/head.html | {section}/reveal-hugo/body.html |

---

## Custom CSS Example

In `home/reveal-hugo/head.html`:

```html
<style>
.reveal section h1 {
  color: blue;
}
</style>
```

---

## Custom JS Example

In `home/reveal-hugo/body.html`:

```html
<script type="text/javascript">
Reveal.addEventListener('slidechanged', function(event) {
  console.log("🎞️ Slide is now " + event.indexh);
});
</script>
```
