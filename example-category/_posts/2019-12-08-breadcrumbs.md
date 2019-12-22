Breadcrumbs
===========

Each post and page has a line of navigation breadcrumbs in the page footer. For
example, here are the breadcrumbs for this page:

<p>
{% include breadcrumbs.html %}
</p>

Breadcrumbs help users figure out the hierarchical organization of your site
and find their way around.
While the [header links](../../_posts/2019-11-25-header-and-footer-links.md)
act as the site's primary navigation and link to the main sections of the site,
the breadcrumbs show the user exactly where they currently are. They show the
path from the home page to the current page and provide links for moving back
up the hierarchy.

The breadcrumbs are taken from the `/`-separated parts of the page's URL,
so depending on your site's [permalink settings](https://jekyllrb.com/docs/permalinks/)
the URL and breadcrumbs might contain the page's categories, its year, month
and day, or other arbitrary parts.

## Omitting dates from breadcrumbs

If you have the year, month and day in your permalink URLs (e.g. `2019/12/08`)
you can optionally omit these from the breadcrumbs by putting
`breadcrumbs_omit_dates=true` in your `_config.yml` file:

```yaml
breadcrumbs_omit_dates: true
```

## Creating pages for breadcrumbs to link to

For each individual breadcrumb, if your site has a page at that breadcrumb's
URL, the breadcrumb will link to that page. For example one of this post's
breadcrumbs is `2019`.
By creating a `2019.md` or `2019/index.md` file you create a page for the `2019`
breadcrumb, and the breadcrumb will automatically link to the page.
(You might use this page to list all of your posts from 2019, for example.)

The [categories post](./2019-12-08-categories.md) has tips for creating pages
for categories, that breadcrumbs will then link to.

## Changing the breadcrumb text for a page

When there's a page for a breadcrumb, if the page has a title then the page
title will be used as the breadcrumb text rather than the text from the
breadcrumb's URL segment. If the page has a `breadcrumb_text` variable in its
[YAML Front Matter](https://jekyllrb.com/docs/front-matter/) that will be used
instead of the page title:

```yaml
---
breadcrumb_text: foo
---
```
