+++
author = "Hugo Authors"
title = "Demo - Support for code, pre, kbd, mark"
date = "2024-04-30"
description = "Guide to advanced usage of Anubis2"
tags = [
    "emoji",
]
+++

## Individual support for code, pre, kbd, mark

`code` <pre>pre</pre>

<kbd>CRTL</kbd> + <kbd>K</kbd> + <kbd>B</kbd> + <kbd>D</kbd>

<!--more-->

Feel free to switch between the light and dark themes to see the rendering differences.

### Support for \<code\> tag

<code>Direct Code</code>

`A verrrrrryyyyy llloooonnnggg coooodeeee`

`code` `is` `here`

```plain
multiline
code
here
```

```typescript
// ```typescript
interface User {
  id: number
  firstName: string
  lastName: string
  role: string
}
```

```typescript {linenos=inline}
// ```typescript {linenos=inline}
function updateUser(id: number, update: Partial<User>) {
  const user = getUser(id)
  const newUser = { ...user, ...update }
  saveUser(id, newUser)
}
```

```typescript {linenos=true}
// ```typescript {linenos=true}
function updateUser(id: number, update: Partial<User>) {
  const user = getUser(id)
  const newUser = { ...user, ...update }
  saveUser(id, newUser)
}
```

### Support for \<pre\> tag

<pre>pre text</pre>
<pre>pre text</pre>
<pre>pre text</pre>

### Support for \<kbd\> tag


<p>Press <kbd>CTRL</kbd> + <kbd>C</kbd> to copy text (Windows).</p>

<p>Press <kbd>CMD</kbd> + <kbd>C</kbd> to copy text (Mac OS).</p>

Press <kbd>CTRL</kbd>+<kbd>ALT</kbd>+<kbd>Delete</kbd> to end the session.


### Support for \<mark\> tag

Most <mark>salamanders</mark> are nocturnal, and hunt for insects, worms, and other small creatures.
Most <mark>salamanders</mark> are nocturnal, and hunt for insects, worms, and other small creatures.

Most <mark>salamanders</mark> are nocturnal, and hunt for insects, worms, and other small creatures.

### Support for \<kbd\> in \<pre\>

<pre>This is a <kbd>KBD</kbd> inside a pre. </pre>

### Support for \<kbd\> in \<code\> (❌ Should not be used)

<code>This is a <kbd>KBD</kbd> inside a code. </code>

### Support for \<code\> in \<pre\> (❌ Should not be used)

<pre>This is a <code>CODE</code> inside a pre. </pre>

### Support for \<code\> in \<kbd\> (❌ Should not be used)

<kbd>This is a <code>CODE</code> inside a kbd. </kbd>

### Support for \<pre\> in \<kbd\> (❌ Should not be used)

<kbd>This is a <pre>PRE</pre> inside a kbd. </kbd>

### Support for \<pre\> in \<code\> (❌ Should not be used)

<code>This is a <pre>PRE</pre> inside a code. </code>

### Support for \<mark\> in \<kbd\>

<kbd>This is a <mark>MARK</mark> inside a kbd. </kbd>

### Support for \<mark\> in \<code\>

<code>This is a <mark>MARK</mark> inside a code. </code>

### Support for \<mark\> in \<pre\>

<pre>This is a <mark>MARK</mark> inside a pre. </pre>