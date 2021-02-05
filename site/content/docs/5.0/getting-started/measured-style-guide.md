---
layout: docs
title: Measured Style Guide
description: Become familiar with Measured's style guide. Measured uses Bootstrap, a framework for building responsive sites.
group: getting-started
aliases:
  - "/docs/5.0/getting-started/"
  - "/docs/getting-started/"
  - "/getting-started/"
toc: true
---

## Quick start

Looking to quickly add Measured's styling to your project? Grab the latest copy of bootstrap as well as the `_measured-style-guide.scss` file located in the `sites/assets/scss/` directory.

In detail, the process is as follows:

1. Install the Bootstrap npm module into your project:
```shell
npm install bootstrap@5.0.0-beta1
# or
yarn add bootstrap@5.0.0-beta1
```
2. grab the `_measured-style-guide.scss` file and reference it before Bootstrap in your main `style.scss` file, at the very top.
```scss
@import '/src/assets/measured-style-guide';
@import '../node_modules/bootstrap/scss/bootstrap';
```

## Brand

### Logotype

For the top navigation of a Measured Product, use this logotype. Do not modify the logos in any way. Do not use Measured's branding for your own open or closed source projects.

<div class="bd-brand-logos d-sm-flex text-center bg-light rounded-lg overflow-hidden w-100 mb-3">
  <div class="bd-brand-item w-100 px-2 py-5">
    <img src="/docs/{{< param docs_version >}}/assets/brand/measured-logotype.svg" alt="Measured" height="50" loading="lazy">
  </div>
</div>

The logo mark is also available in inverse with white text. All rules for our primary logotype apply to this as well.

<div class="bd-brand-logos d-sm-flex text-center bg-light rounded-lg overflow-hidden w-100 mb-3">
  <div class="bd-brand-item w-100 px-2 py-5 inverse">
    <img src="/docs/{{< param docs_version >}}/assets/brand/measured-logotype-white.svg" alt="Measured" height="50" loading="lazy">
  </div>
</div>

### Logo

When referencing Measured, use this logo mark. Do not modify the logos in any way. Do not use Measured's branding for your own open or closed source projects.

<div class="bd-brand-item px-2 py-5 mb-3 bg-light rounded-lg">
  <img class="d-block img-fluid mx-auto" src="/docs/{{< param docs_version >}}/assets/brand/measured-m.svg" alt="Measured" width="100" height="100">
</div>

Our logo mark is also available in black and white. All rules for our primary logo apply to these as well.

<div class="bd-brand-logos d-sm-flex text-center bg-light rounded-lg overflow-hidden w-100 mb-3">
  <div class="bd-brand-item w-100 px-2 py-5">
    <img src="/docs/{{< param docs_version >}}/assets/brand/measured-m-black.svg" alt="Measured" width="128" height="102" loading="lazy">
  </div>
  <div class="bd-brand-item w-100 px-2 py-5 inverse">
    <img src="/docs/{{< param docs_version >}}/assets/brand/measured-m-white.svg" alt="Measured" width="128" height="102" loading="lazy">
  </div>
</div>

### Name

Measured should always be referred to as just **Measured**. Nothing before or after it and no lowercase _m_.

<div class="bd-brand-logos d-sm-flex text-center bg-light rounded-lg overflow-hidden w-100 mb-3">
  <div class="bd-brand-item w-100 p-3">
    <div class="h3">Measured</div>
    <strong class="text-success">Correct</strong>
  </div>
  <div class="bd-brand-item w-100 p-3">
    <div class="h3 text-muted">measured</div>
    <strong class="text-danger">Incorrect</strong>
  </div>
  <div class="bd-brand-item w-100 p-3">
    <div class="h3 text-muted">Measured Inc.</div>
    <strong class="text-danger">Incorrect</strong>
  </div>
</div>

## Color

### Theme colors

We use a subset of all colors to create a smaller color palette for generating color schemes, also available as Sass variables and a Sass map in Bootstrap's `scss/_variables.scss` file.

<div class="row">
  {{< theme-colors.inline >}}
  {{- range (index $.Site.Data "theme-colors") }}
    <div class="col-md-4">
      <div class="p-3 mb-3 bg-{{ .name }} {{ if .contrast_color }}text-{{ .contrast_color }}{{ else }}text-white{{ end }}">{{ .name | title }}</div>
    </div>
  {{ end -}}
  {{< /theme-colors.inline >}}
</div>

All these colors are available as a Sass map, `$theme-colors`.

{{< scss-docs name="theme-colors-map" file="scss/_variables.scss" >}}

Check out [our Sass maps and loops docs]({{< docsref "/customize/sass#maps-and-loops" >}}) for how to modify these colors.

Check out [All our colors]({{< docsref "/customize/color#all-colors" >}}) for ranges that can be used for graphing.

## Typography

### Global settings

Measured sets basic global display, typography, and link styles. When more control is needed, check out the [textual utility classes]({{< docsref "/utilities/text" >}}).

- Use the [font stack]({{< docsref "#font--font-stack" >}}) that is defined below.
- For a more inclusive and accessible type scale, we use the browser's default root `font-size` (typically 16px) so visitors can customize their browser defaults as needed.
- Use the `$font-family-base`, `$font-size-base`, and `$line-height-base` attributes as our typographic base applied to the `<body>`.
- Set the global link color via `$link-color`.
- Use `$body-bg` to set a `background-color` on the `<body>` (`#fff` by default).
- __Set `$font-size-base` in `rem`.__

These styles can be found within `_reboot.scss`, and the global variables are defined in `_custom_variables.scss`, and are defaulted in `_variables.scss`.

### Font & Font Stack

Measured uses __Inter__ for in-house products. If Inter is not available, fallback to __Roboto__.

Measured uses a sans-serif font stack for most use-cases:

- `$font-family-sans-serif: Inter, Roboto, system-ui, -apple-system, "Segoe UI", "Helvetica Neue", Arial, "Noto Sans", "Liberation Sans", sans-serif, "Apple Color Emoji", "Segoe UI Emoji", "Segoe UI Symbol", "Noto Color Emoji";`

For Monospace fonts (such as formatted code), use the following font stack:

- `$font-family-monospace: SFMono-Regular, Menlo, Monaco, Consolas, "Liberation Mono", "Courier New", monospace;`

## JS

A few components require the use of JavaScript to function. These can be loaded by using the `ng-bootstrap` package.

### Modules

If you use `<script type="module">`, please refer to our [using Bootstrap as a module]({{< docsref "/getting-started/javascript#using-bootstrap-as-a-module" >}}) section.

### Components

Curious which components explicitly require our JavaScript and Popper? Click the show components link below. If you're at all unsure about the general page structure, keep reading for an example page template.

<details>
<summary class="text-primary mb-3">Show components requiring JavaScript</summary>
{{< markdown >}}
- Alerts for dismissing
- Buttons for toggling states and checkbox/radio functionality
- Carousel for all slide behaviors, controls, and indicators
- Collapse for toggling visibility of content
- Dropdowns for displaying and positioning (also requires [Popper](https://popper.js.org/))
- Modals for displaying, positioning, and scroll behavior
- Navbar for extending our Collapse plugin to implement responsive behavior
- Toasts for displaying and dismissing
- Tooltips and popovers for displaying and positioning (also requires [Popper](https://popper.js.org/))
- Scrollspy for scroll behavior and navigation updates
{{< /markdown >}}
</details>

## Important globals

Bootstrap employs a handful of important global styles and settings that you'll need to be aware of when using it, all of which are almost exclusively geared towards the *normalization* of cross browser styles. Let's dive in.

### HTML5 doctype

Bootstrap requires the use of the HTML5 doctype. Without it, you'll see some funky incomplete styling, but including it shouldn't cause any considerable hiccups.

```html
<!doctype html>
<html lang="en">
  ...
</html>
```

### Responsive meta tag

Bootstrap is developed *mobile first*, a strategy in which we optimize code for mobile devices first and then scale up components as necessary using CSS media queries. To ensure proper rendering and touch zooming for all devices, **add the responsive viewport meta tag** to your `<head>`.

```html
<meta name="viewport" content="width=device-width, initial-scale=1">
```

You can see an example of this in action in the [starter template](#starter-template).

### Box-sizing

For more straightforward sizing in CSS, we switch the global `box-sizing` value from `content-box` to `border-box`. This ensures `padding` does not affect the final computed width of an element, but it can cause problems with some third party software like Google Maps and Google Custom Search Engine.

On the rare occasion you need to override it, use something like the following:

```css
.selector-for-some-widget {
  box-sizing: content-box;
}
```

With the above snippet, nested elements—including generated content via `::before` and `::after`—will all inherit the specified `box-sizing` for that `.selector-for-some-widget`.

Learn more about [box model and sizing at CSS Tricks](https://css-tricks.com/box-sizing/).

### Reboot

For improved cross-browser rendering, we use [Reboot]({{< docsref "/content/reboot" >}}) to correct inconsistencies across browsers and devices while providing slightly more opinionated resets to common HTML elements.

## Community

Stay up to date on the development of Bootstrap and reach out to the community with these helpful resources.

- Read and subscribe to [The Official Bootstrap Blog]({{< param blog >}}).
- Join [the official Slack room]({{< param slack >}}).
- Chat with fellow Bootstrappers in IRC. On the `irc.freenode.net` server, in the `##bootstrap` channel.
- Implementation help may be found at Stack Overflow (tagged [`bootstrap-5`](https://stackoverflow.com/questions/tagged/bootstrap-5)).
- Developers should use the keyword `bootstrap` on packages which modify or add to the functionality of Bootstrap when distributing through [npm](https://www.npmjs.com/search?q=keywords:bootstrap) or similar delivery mechanisms for maximum discoverability.

You can also follow [@getbootstrap on Twitter](https://twitter.com/{{< param twitter >}}) for the latest gossip and awesome music videos.
