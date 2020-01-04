Edit Page and View Source Buttons
=================================

If you hover over the small `☰` menu in the bottom-right of every page it opens a
popup menu with a {% include view_source_link.html %} link to the
raw copy of the page's source code (e.g. the Markdown source) and
an {% include edit_page_link.html %} link for quickly editing the page on GitHub
(very handy for correcting typos for example).

To remove the Edit and View Source links set `view_source_link: false` and
`edit_page_link: false` in your `_config.yml`:

```yaml
view_source_link: false
edit_page_link: false
```

The same menu also contains a handy link for [easily creating a new post](2019-11-11-new-post-form.md).
