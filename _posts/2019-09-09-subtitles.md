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
