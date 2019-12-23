Post Lists
==========

The `post_list.html` include renders lists of blog posts, with
support for filtering by category or tag.

## Listing all published posts

To render a list of all the site's posts:

```liquid
{% raw %}{% include post_list.html %}{% endraw %}
```

## Listing draft posts

To render a list of draft posts only, pass `drafts=true`:

```liquid
{% raw %}{% include post_list.html drafts=true %}{% endraw %}
```

## Listing posts in a category

You can assign a category to a Jekyll post by putting the post's file in a `_posts/` dir within a subdir.
For example if a post is in `bar/_posts/` rather than in the top-level `_posts/` dir,
then the post will be in the `bar` category.
Alternatively you can set a post's category by putting `category: bar` in the post's YAML frontmatter.

To render only posts from a given category pass `category="some-category"` to `post_list.html`:

```liquid
{% raw %}{% include post_list.html category="some-category" %}{% endraw %}
```

You can use this to create a page for a category.
One of this site's categories is `"example-category"`.
To create a category page for `"example-category"` you can either
create an `example-category.md` file or an `example-category/index.md` file
and it will be rendered at `/example-category/`.

The `/example-category/` URL is nice:
if your [`permalink` setting](https://jekyllrb.com/docs/permalinks/) starts with `/:categories/`
(all of Jekyll's [built-in permalink formats](https://jekyllrb.com/docs/permalinks/#built-in-formats) do)
then the permalinks of posts in `example-category` will start with `/example-category/`,
so they'll be sub-URLs of the category's page.

For an example category page see this site's
[`example-category/index.md`]({{ site.github.repository_url }}/blob/master/example-category/index.md) file,
with renders this [page for the example category](../index.md).

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

## Listing posts with a tag

You can tag a post in Jekyll by adding a `tags` variable to its YAML front matter,
for example: `tags: [hot, summer]`.

To render the list of posts with a given tag pass `tag="some-tag"`  to `post_list.html`:

```liquid
{% raw %}{% include post_list.html tag="some-tag" %}{% endraw %}
```

You can use this to create a page for a tag.
One of this site's categories is `"example-tag"`.
To create a tag page for `"example-tag"` you can either
create an `example-tag.md` file or an `example-tag/index.md` file
and it will be rendered at `/example-tag/`.

For an example category page see this site's
[`example-tag.md`]({{ site.github.repository_url }}/blob/master/example-tag.md) file,
with renders this [page for the example tag](../../example-tag.md).

Unlike categories, [tags in Jekyll can't appear in URLs](https://jekyllrb.com/docs/posts/#categories-and-tags).
