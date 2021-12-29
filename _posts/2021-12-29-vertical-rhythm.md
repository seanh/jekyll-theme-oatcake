---
lines: true
---

Vertical Rhythm
===============

Oatcake aligns everything to a consistent vertical rhythm for a more harmonious reading experience:
like writing to the lines on a sheet of lined paper.

You can view any page with lines added for debugging the vertical rhythm by adding
a `?lines` query param to the end of the page's URL.
For example here's a link to the
[front page with lines drawn](/jekyll-theme-oatcake/?lines).

You can also turn on the lines all the time for any page or post by adding
`lines: true` to the YAML frontmatter:

```yaml
---
lines: true
---

My Post
=======

...
```

I've taken a lot of care to make sure that the vertical rhythm works correctly
with all the HTML elements and CSS classes that the theme supports, in all
their combinations. But getting the vertical rhythm right for every single edge
case is very difficult and not worth the effort. Here are some things that I
know break the vertical rhythm, causing all the text that follows to be
mis-aligned from the debugging lines:

* Images, videos, iframes and other media embeds.

  You have to scale your images to be a multiple of 28px in height if you don't
  want them to disturb the vertical rhythm. Even then if the user zooms in
  their browser the rhythm might still become upset.  I recommend not
  worrying about it.

* Code blocks that get a horizontal scrollbar because they're too wide.

  The horizontal scrollbar upsets the vertical rhythm.

* [Embedded GitHub Gists](/jekyll-theme-oatcake/{% post_url 2019-08-14-gists %})

* [Code figures](/jekyll-theme-oatcake/{% post_url 2019-08-03-code-blocks %})
  created using Jekyll's {% raw %}`{% highlight %}`{% endraw %} tag.
  I couldn't figure out what's going wrong here.
  Other code blocks (creating using Markdown indentation or triple backticks) work fine
  (including with syntax highlighting).

