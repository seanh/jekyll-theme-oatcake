---
subtitle: Posts can have subtitles, which appear in large text beneath the title. "Lead" paragraphs also use the same large text style.
---

Subtitles and Lead Paragraphs
=============================

To give a post a subtitle by add a `subtitle` to its [YAML front matter](https://jekyllrb.com/docs/front-matter/):

```yaml
---
title: Subtitles and Lead Paragraphs
subtitle: Posts can have subtitles, which appear in large text beneath the title.
---
```

Subtitles appear beneath the title at the top of the page, in large text.

You can also use this large text style anywhere in a page by creating a
paragraph with the CSS class `lead`. For example this:

```html
<p class="lead">This is a "lead" paragraph. It stands out more than other
paragraphs. These can go anywhere on the page, not just at the top of
posts.</p>
```

Will render like this:

<p class="lead">This is a "lead" paragraph. It stands out more than other
paragraphs. These can go anywhere on the page, not just at the top of
posts.</p>

Inline elements like `<code>`, `<kbd>` and `<samp>` also work in subtitles and lead paragraphs:

<p class="lead" markdown="1">Lorem ipsum dolor sit amet, consectetur adipiscing
elit, sed do eiusmod tempor `incididunt` ut labore et <kbd>dolore</kbd> magna aliqua. Ut
enim ad minim veniam, `quis` nostrud <kbd>exercitation ullamco</kbd> laboris nisi ut aliquip
ex ea commodo consequat.  Duis aute irure dolor in reprehenderit in voluptate
velit <samp>esse</samp> cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat
<samp>cupidatat</samp> non proident, sunt in culpa qui officia deserunt mollit anim id est
laborum.</p>
