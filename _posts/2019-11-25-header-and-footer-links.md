---
category: example-category
---

Header and Footer Links
=======================

You can use Jekyll [Data Files](https://jekyllrb.com/docs/datafiles/) to add
links to the header and footer.
Create a `_data/header_links.yaml` file to specify your header links and `_data/footer_links.yaml` for the footer links.
For examples see
[this site's `header_links.yaml`](https://raw.githubusercontent.com/{{ site.github.repository_nwo }}/master/_data/header_links.yaml)
and [this site's `footer_links.yaml`](https://raw.githubusercontent.com/{{ site.github.repository_nwo }}/master/_data/footer_links.yaml).

The footer contains View Source and Edit Page links by default. To remove these
set `view_source_link: false` and `edit_page_link: false` in your `_config.yml`:

```yaml
view_source_link: false
edit_page_link: false
```
