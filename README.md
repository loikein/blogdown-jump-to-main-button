# Blogdown Jump-to-Main Button

For more inclusive and accessible Internet.

## Usage

1. Add `jump-after-toc.js` to `/static/js`
1. Add `jump-after-toc.css` to `/static/css`
1. Use your preferred way to refer to these two files
1. Add the following code directly under `<body>`:

```html
<section class="a11y-links">
<button class="a11y-links__link" tabindex="0" onclick="jumpAfterTOC()">Skip to main content</button>
</section>
```

## How to Refer to the Static Files

This is what I use (all reference files are in this repo):

In `baseof.html`, after `<footer>`, add:

```html
{{ range .Site.Params.customJS }}
<script async src="{{ . | relURL }}"></script>
{{ end }}
```

In the end of `head.html`, add:

```html
{{ range .Site.Params.customCSS }}
<link rel="stylesheet" href="{{ . | relURL }}">
{{ end }}
```

In `config.yaml`, under `params`, add:

```yaml
params:
  customCSS: ["/css/jump-after-toc.css"]
  customJS: ["js/jump-after-toc.js"]

  … (other params)
```
