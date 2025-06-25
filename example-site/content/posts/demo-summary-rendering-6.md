---
title: "Demo - Summary Rendering Test 6 (🤯 Hard)"
date: 2024-04-25T1:54:17+08:00
draft: true
hidden: true
tags: [Hugo]
---

```c {linenos=inline}
int main() {
    // Is your theme able to handle this?
    // Are the content below rendered correctly?
    return 0; // Only see this in the summary view
}
```

<!--<!--more-->

<mark>You MUST NOT see me in the preview</mark>

## Test Heading

The content below should also be hidden in the summary view.

<!--more-->

```html
Will <!--<!--more--> cause a rendering issue?
```
