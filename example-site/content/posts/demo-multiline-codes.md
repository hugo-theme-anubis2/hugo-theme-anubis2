+++
author = "Junyi"
title = "Demo - Multiline Codes"
date = "2024-04-23"
description = "Codes, Codefences, and Syntax Highlighting."
tags = [
    "icons",
    "anubis2",
    "hugo"
]
+++

```c {linenos=table, hl_lines=[1,"3-4",8], linenostart=199}
int main() {
    int a = 1;
    if (a == 999)
        // This is a very long comment to test the `overflow` attribute defined in CSS. The `overflow` property in CSS deals with the content when it overflows the block-level container. It can take the following values: `visible` (default), `hidden`, `scroll`, `auto`, and `clip`.
        // If `visible` is specified, the content is not clipped and can render outside the container. If `hidden` is specified, the content is clipped and the rest of the content will be invisible. If `scroll` is specified, the browser should provide a scrolling mechanism for the user to access the clipped content.
    }
    return 0;
}
```

## Truth Table

| Item                     | Line Numbers | Highlight Lines | Anchor Lines | Wide CodeBlock Scroll | Supported |
| ------------------------ | ------------ | --------------- | ------------ | --------------------- | --------- |
| **Full Feature Support** | ture         | true            | true         | ✅                     | ✅         |
|                          | table        | true            | true         | ✅                     | ✅         |
|                          | table        | true            | false        | ✅                     | ✅         |
|                          | inline       |                 |              | ✅                     | ✅         |
|                          | ture         | true            | false        | ✅                     | ✅         |
|                          | ture         | false           | false        | ✅                     | ✅         |
|                          | false        | true            | /            | ✅                     | ✅         |
| Basic Support            | false        | false           | /            | ✅                     | ✅         |

Note: Anubis2 does not support `hl_inline=true`

<!--more-->

## Line Numbers, Highlight Lines

### Line Number (table) and Highlight Lines

`linenos=table` will give copy-and-paste friendly code blocks.

    ```c {linenos=table, hl_lines=[1,"3-4",8], linenostart=199}
    // codes ...
    ```

```c {linenos=table, hl_lines=[1,"3-4",8], linenostart=199}
int main() {
    int a = 1;
    if (a == 999)
        // This is a very long comment to test the `overflow` attribute defined in CSS. The `overflow` property in CSS deals with the content when it overflows the block-level container. It can take the following values: `visible` (default), `hidden`, `scroll`, `auto`, and `clip`.
        // If `visible` is specified, the content is not clipped and can render outside the container. If `hidden` is specified, the content is clipped and the rest of the content will be invisible. If `scroll` is specified, the browser should provide a scrolling mechanism for the user to access the clipped content.
    }
    return 0;
}
```

### Line Number (true) and Highlight Lines

    ```c {linenos=true, hl_lines=[1,"3-4",8], linenostart=1}
    // codes ...
    ```

```c {linenos=true, hl_lines=[1,"3-4",8], linenostart=1}
int main() {
    int a = 1;
    if (a == 999)
        // This is a very long comment to test the `overflow` attribute defined in CSS. The `overflow` property in CSS deals with the content when it overflows the block-level container. It can take the following values: `visible` (default), `hidden`, `scroll`, `auto`, and `clip`.
        // If `visible` is specified, the content is not clipped and can render outside the container. If `hidden` is specified, the content is clipped and the rest of the content will be invisible. If `scroll` is specified, the browser should provide a scrolling mechanism for the user to access the clipped content.
    }
    return 0;
}
```

### Line Number (inline) and Highlight Lines

    ```c {linenos=inline, hl_lines=[1,"3-4",8], linenostart=1}
    // codes ...
    ```

```c {linenos=inline, hl_lines=[1,"3-4",8], linenostart=1}
int main() {
    int a = 1;
    if (a == 999)
                // This is a very long comment to test the `overflow` attribute defined in CSS. The `overflow` property in CSS deals with the content when it overflows the block-level container. It can take the following values: `visible` (default), `hidden`, `scroll`, `auto`, and `clip`.
        // If `visible` is specified, the content is not clipped and can render outside the container. If `hidden` is specified, the content is clipped and the rest of the content will be invisible. If `scroll` is specified, the browser should provide a scrolling mechanism for the user to access the clipped content.
    }
    return 0;
}
```

### Line Number (false) and Highlight Lines

`linenos=false` will turn off line numbers if it’s configured to be on in site configuration.

    ```c {linenos=false, hl_lines=[1,"3-4",8]}
    // codes ...
    ```

```c {linenos=false, hl_lines=[1,"3-4",8]}
int main() {
    int a = 1;
    if (a == 999)
                // This is a very long comment to test the `overflow` attribute defined in CSS. The `overflow` property in CSS deals with the content when it overflows the block-level container. It can take the following values: `visible` (default), `hidden`, `scroll`, `auto`, and `clip`.
        // If `visible` is specified, the content is not clipped and can render outside the container. If `hidden` is specified, the content is clipped and the rest of the content will be invisible. If `scroll` is specified, the browser should provide a scrolling mechanism for the user to access the clipped content.
    }
    return 0;
}
```

## Anchor, Inline, Shortcode

### Line Number (table) and Highlight Lines and Anchor

Now you can click on the line number to get a link to that line.

    ```c {linenos=table, hl_lines=[1,"3-4",8], linenostart=199, anchorlinenos=true}
    // codes ...
    ```

```c {linenos=table, hl_lines=[1,"3-4",8], linenostart=199, anchorlinenos=true}
int main() {
    int a = 1;
    if (a == 999)
        // This is a very long comment to test the `overflow` attribute defined in CSS. The `overflow` property in CSS deals with the content when it overflows the block-level container. It can take the following values: `visible` (default), `hidden`, `scroll`, `auto`, and `clip`.
        // If `visible` is specified, the content is not clipped and can render outside the container. If `hidden` is specified, the content is clipped and the rest of the content will be invisible. If `scroll` is specified, the browser should provide a scrolling mechanism for the user to access the clipped content.
    }
    return 0;
}
```

### Highlight Inline are not supported by Anubis2 ❌

    ```c {linenos=true,hl_lines=[1,3,5], hl_inline=true}
    // codes ...
    ```

```c {linenos=true,hl_lines=[1,3,5], hl_inline=true}
int main() {
    int a = 1;
    if (a == 999)
        // If `visible` is specified, the content is not clipped and can render outside the container. If `hidden` is specified, the content is clipped and the rest of the content will be invisible. If `scroll` is specified, the browser should provide a scrolling mechanism for the user to access the clipped content.
    }
    return 0;
}
```


<!-- 

Those are trash codes.

### Highlight shortcode, with Line Number (table), with Highlight Lines and Anchor

    {{</* highlight c "linenos=table,hl_lines=1 3-4 8, anchorlinenos=true" */>}}
    // codes
    {{</* /highlight */>}}

{{< highlight c "linenos=table,hl_lines=1 3-4 8, anchorlinenos=true" >}}
int main() {
int a = 1;
if (a == 999)
// This is a very long comment to test the `overflow` attribute defined in CSS. The `overflow` property in CSS deals with the content when it overflows the block-level container. It can take the following values: `visible` (default), `hidden`, `scroll`, `auto`, and `clip`.
// If `visible` is specified, the content is not clipped and can render outside the container. If `hidden` is specified, the content is clipped and the rest of the content will be invisible. If `scroll` is specified, the browser should provide a scrolling mechanism for the user to access the clipped content.
}
return 0;
}
{{< / highlight >}}

### Highlight shortcode, with Line Number (inline), with Highlight Lines and Anchor

    {{</* highlight c "linenos=inline,hl_lines=1 3-4 8, anchorlinenos=true" */>}}
    // codes
    {{</* /highlight */>}}

{{< highlight c "linenos=inline,hl_lines=1 3-4 8, anchorlinenos=true" >}}
int main() {
int a = 1;
if (a == 999)
// This is a very long comment to test the `overflow` attribute defined in CSS. The `overflow` property in CSS deals with the content when it overflows the block-level container. It can take the following values: `visible` (default), `hidden`, `scroll`, `auto`, and `clip`.
// If `visible` is specified, the content is not clipped and can render outside the container. If `hidden` is specified, the content is clipped and the rest of the content will be invisible. If `scroll` is specified, the browser should provide a scrolling mechanism for the user to access the clipped content.
}
return 0;
}
{{< / highlight >}}

### Highlight shortcode, No Line Number, With Highlight Lines and Anchor

    {{</* highlight c "linenos=false,hl_lines=1 3-4 8, anchorlinenos=true" */>}}
    // codes
    {{</* /highlight */>}}

{{< highlight c "linenos=false,hl_lines=1 3-4 8, anchorlinenos=true" >}}
int main() {
int a = 1;
if (a == 999)
// This is a very long comment to test the `overflow` attribute defined in CSS. The `overflow` property in CSS deals with the content when it overflows the block-level container. It can take the following values: `visible` (default), `hidden`, `scroll`, `auto`, and `clip`.
// If `visible` is specified, the content is not clipped and can render outside the container. If `hidden` is specified, the content is clipped and the rest of the content will be invisible. If `scroll` is specified, the browser should provide a scrolling mechanism for the user to access the clipped content.
}
return 0;
}
{{< / highlight >}} -->
