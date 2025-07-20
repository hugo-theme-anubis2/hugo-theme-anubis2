+++
author = "Hugo Authors"
title = "Advanced Style"
date = "2024-04-09"
description = "Guide to advanced usage of Anubis2"
tags = [
    "emoji",
]
+++

There are examples of how to use custom `global-wise style` or `page-wise style`.

<!--more-->

<div class="anubis-custom-style">
The custom <code>.css</code> <code>.scss</code> <code>.sass</code> file should be placed in <code>assets/</code> folder. (instead of <code>static/</code>)
</div>

<junyi>
This page is affected by <code>assets/css/custom1.scss</code> and <code>assets/css/custom2.css</code> and <code>advanced-style/style.css</code>
</junyi>

<junyi><code>advanced-style/style.css</code> affects only the current page.</junyi>

```html
<style>
  @import 'style.css';
</style>
```

<style>
  @import 'style.css';
</style>

<junyi><code>assets/css/custom1.scss</code> and <code>assets/css/custom2.scss</code> will have global effect.

```scss
// assets/css/custom2.css
.anubis-custom-style {
    background-color: pink;
    color: black;
    padding: 1em;
    border-radius: 0.3em;
    border: 1px solid black;
}
```

```scss
// assets/css/foundation/_vars.scss
$font-stack: Helvetica, sans-serif;
$primary-color: rgb(255, 255, 168);
$background-color: rgb(85, 85, 85);
```

```scss
// assets/css/custom1.scss
@import 'foundation/vars';

junyi {
    display: block;
    font: 100% $font-stack;
    color: $primary-color;
    background-color: $background-color;
    margin-top: 1em;
}
```