---
title: "Demo - Summary Rendering Test 8 (💀 Nightmare)"
date: 2024-04-25T1:54:19+08:00
draft: true
hidden: true
tags: [Hugo]
---
<!--<!--more-->
```c {linenos=table}
int main() {
    // Is your theme able to handle this? <!--<!--more-->
    // Are the content below rendered correctly? <!--more-->
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
