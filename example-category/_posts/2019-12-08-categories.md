---
tags: [example-tag, another-tag]
---
Categories and Tags
===================

Jekyll supports both [categories and
tags](https://jekyllrb.com/docs/posts/#categories-and-tags) for organizing your
posts.

Categories vs Tags
------------------

The differences between categories and tags are:

**A post's category can come from the subdirectory that the post's file is in.**

For example if a post is in `bar/_posts/` rather than just `_posts/`,
then the post will be in the `bar` category.
You can also set a post's category by putting `category: bar` in the post's YAML frontmatter.

Tags, on the other hand, can only be added to a post by putting
`tags: [hot, summer]` in its YAML frontmatter. Tags can't come from the
filesystem.

**Categories can appear in post's URLs, tags can't.**

If you have `:categories` in your [`permalink` setting](https://jekyllrb.com/docs/permalinks/)
(all of Jekyll's [built-in permalink formats](https://jekyllrb.com/docs/permalinks/#built-in-formats) do)
then if a post has a category the category will form part of the post's URL.

**Categories can appear in breadcrumbs, tags can't.**

Since [breadcrumbs](./2019-12-08-breadcrumbs.md) are based on the post's URL,
if you have categories in the URLs they'll appear in the breadcrumbs as well.
If the category has a page (see below) then the breadcrumb will link to the
category's page. For example here are this page's breadcrumbs:

<p>
  {% include breadcrumbs.html %}
</p>

**Tags appear as pills next to the post in post listings and on the post's own page, categories don't.**

If a tag has a page (see below) then its pill will be linked to its page.
For example, here as this post's tags:

<p>
  {% include post_tags.html page=page %}
</p>

Categories aren't hierarchical
------------------------------

The fact that categories can appear in the filesystem and in URLs might imply
that there's a hierarchical ordering of categories. For example you might think
that a `foo/bar/` dir `gar/bar/` dir are two different categories:

    foo/
      bar/
        _posts/
          2019-12-09-first-post.md
    gar/
      bar/
        _posts/
          2019-12-09-second-post.md

You might think that, as with directories in a filesystem, `foo/bar/` and
`gar/bar/` are two different categories. But that isn't how it works in Jekyll:
there's just a single `"bar"` category and both posts belong to it.
There's no hierarchical ordering between the `"bar"`, `"foo"` and `"gar"` categories.
The two directories `foo/bar/` and `gar/bar/` are just two different ways of putting posts in the `"bar"` category.
`foo/bar/` also puts the post in the `"foo"` category, and `gar/bar/` also puts the post in the `"gar"` category.
The first post belongs to two separate categories `"foo"` and `"bar"`, and the
second post belongs to `"gar"` and `"bar"`:

* Categories:
  * foo:
    * 2019-12-09-first-post.md
  * bar:
    * 2019-12-09-first-post.md
    * 2019-12-09-second-post.md
  * gar:
    * 2019-12-09-second-post.md

You can create a page for a category
------------------------------------

You can create a page for a category, and breadcrumbs will link to that
category page whenever the category appears in a breadcrumb.

For example one of this post's categories is `"example-category"`.
To create a category page for `"example-category"` you can either
create an `example-category.md` file or an `example-category/index.md` file.

I've created an [`example-category/index.md`]({{ site.github.repository_url }}/blob/master/example-category/index.md) file
in order to create a [page for the example category]({{ "/example-category/" | relative_url }}),
and used a [Post List](../../_posts/2019-12-22-post-lists.md) to list all of
the category's posts.

You can create a page for a tag
-------------------------------

You can create a page for a tag, and tag pills will link to that tag page
whenever the tag appears in a pill.

For example one of this post's tags is `"example-tag"`.
To create a tag page for `"example-tag"` you can either
create an `example-tag.md` file or an `example-tag/index.md` file.

I've created an [`example-tag.md`]({{ site.github.repository_url }}/blob/master/example-tag.md) file
in order to create a [page for the example tag]({{ "/example-tag/" | relative_url }}),
and used a [Post List](../../_posts/2019-12-22-post-lists.md) to list all of
the tag's posts.
