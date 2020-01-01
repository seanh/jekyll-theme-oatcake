---
tag: [Favorite Recipes, Dinosaurs, foo]
category: [programming, web-design, bar]
---

Categories and Tags
===================

The theme has builtin support for Jekyll
[categories and tags](https://jekyllrb.com/docs/posts/#categories-and-tags).

Categories and tags in post footers
-----------------------------------

If a post has any categories or tags they'll be listed at the bottom of
the post, beneath the article footer. For each category or tag, all posts with
that category or tag are listed at the bottom of the post. See the bottom of
this post for an example.

These lists only appear if the category or tag has more than one post.

You can create category and tag pages
-------------------------------------

If your site has a page with the URL `/example-category/` then the `example-category` category will link to that
page, whenever the `example-category` category appears in a post's footer.
You can create such a page by creating a `example-category.md` or
`example-category/index.md` file.
You might use this page to [list all posts in the category](./2019-12-22-post-lists.md#listing-posts-in-a-category).

The `/example-category/` URL is nice:
if your [`permalink` setting](https://jekyllrb.com/docs/permalinks/) starts with `/:categories/`
(all of Jekyll's [built-in permalink formats](https://jekyllrb.com/docs/permalinks/#built-in-formats) do)
then the permalinks of posts in `example-category` will start with `/example-category/`,
so they'll be sub-URLs of the category's page.

If a category page exists then that page's title will be used, instead of the
category name itself, as the label for the category when listing it at the
bottoms of posts.

For an example category page see this site's
[`web-design.md`]({{ site.github.repository_url }}/blob/master/web-design.md) file,
with renders this [page for the Web Design category](../web-design.md).

Creating tag pages works similarly, except that they all go in a `tags` folder:

* To create a page for the `Example Tag` tag, create either a `tags/example-tag.md` or
  `tags/example-tag/index.md` file.
  Whenever the `Example Tag` tag appears in a post's footer it'll be linked to the tag page.

  The tag page's URL must be equal to the name of the tag with spaces
  replaced by `-`'s and uppercase letters downcased. For example a tag named
  `Example tag` would match a page with a `/example-tag/` URL.

* You can use the tag page to [list all posts with the tag](./2019-12-22-post-lists.md#listing-posts-with-a-tag).

  For an example tag page see this site's
  [`tags/favorite-recipes.md`]({{ site.github.repository_url }}/blob/master/tags/favorite-recipes.md) file,
  with renders this [page for the Favorite Recipes tag](../tags/favorite-recipes.md).

Adding categories and tags to posts
-----------------------------------

You can assign categories to a page or post in Jekyll by adding either a `category` or a `categories`
variable to the page or post's [YAML front matter](https://jekyllrb.com/docs/front-matter/).
For example:

```yaml
---
category: example-category
---
```

To assign more than one category to a post use `categories` instead of `category`.
`categories` can be either a space-separated string or a [YAML list](https://en.wikipedia.org/wiki/YAML#Basic_components).
For example:

```yaml
---
categories: [programming, web-design, bar]
---
```

Assigning tags to posts works the same: use either a `tag` (single tag) or `tags`
(space-separated string or list) variable:

```yaml
---
tags: [Favorite Recipes, Dinosaurs, foo]
---
```

The differences between categories and tags are:

1. Categories can appear in post URLs, tags can't.

   If your [`permalink` setting](https://jekyllrb.com/docs/permalinks/) contains
   `:categories` (which all of the [built-in permalink formats](https://jekyllrb.com/docs/permalinks/#built-in-formats)
   do) then a post's categories will appear in the post's permalink URL.

2. Categories can come from the filesystem, tags can't.

   You can set a post's categories using either the `category` or `categories` variable
   in the post's front matter, or by putting the post in a subdir.

   For example if you put a post's source file in a `foo/_posts/` dir rather
   than in the default `_posts/` dir, that post will have the `foo` category. A
   post in a `foo/bar/_posts/` dir will have both the `foo` and `bar`
   categories.

   Tags can only be set in a post's frontmatter.

### Categories aren't hierarchical

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

