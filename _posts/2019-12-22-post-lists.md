Post Lists
==========

The `post_list.html` include renders lists of blog posts, with
support for filtering by category or tag.

To render a list of all the site's posts:

```liquid
{% raw %}{% include post_list.html %}{% endraw %}
```

To render a list of draft posts only, pass `drafts=true`:

```liquid
{% raw %}{% include post_list.html drafts=true %}{% endraw %}
```

To render only posts from a given category pass `category="some-category"`:

```liquid
{% raw %}{% include post_list.html category="some-category" %}{% endraw %}
```

To render only posts with a given tag pass `tag="some-tag"`:

```liquid
{% raw %}{% include post_list.html tag="some-tag" %}{% endraw %}
```

You can use all of the arguments at once. For example to render only drafts in
category some-category with tag some-tag:

```liquid
{% raw %}{% include post_list.html drafts=true category="some-category "tag="some-tag" %}{% endraw %}
```
