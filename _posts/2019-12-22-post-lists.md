Post Lists
==========

The [`post_list.html`]({{ site.github.repository_url }}/blob/master/_includes/post_list.html)
include renders lists of blog posts, with support for filtering by category or
tag.

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

To render only posts from a given category pass `category="some-category"` to `post_list.html`:

```liquid
{% raw %}{% include post_list.html category="some-category" %}{% endraw %}
```

## Listing posts with a tag

To render the list of posts with a given tag pass `tag="some-tag"`  to `post_list.html`:

```liquid
{% raw %}{% include post_list.html tag="some-tag" %}{% endraw %}
```
