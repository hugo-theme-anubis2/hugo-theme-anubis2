---
title: "Demo - Summary Rendering Test 5 (😥 Medium)"
date: 2024-04-25T1:54:16+08:00
draft: true
hidden: true
tags: [Hugo]
---

```c
int main() {
    return 0; // <!--more--> Only see this in the summary view
}
```



<mark>You MUST NOT see me in the preview</mark>

## Test Heading

The content below should also be hidden in the summary view.

<!--more-->

```html
Will <!--<!--more--> cause a rendering issue?
```
