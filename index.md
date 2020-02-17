---
layout: page
---

Oatcake
=======

This is **Oatcake**, the [GitHub Pages](https://pages.github.com/) theme that I use on
[seanh.cc](https://seanh.cc/). It's meant to be a plain theme, fast and mobile
friendly, that doesn't get in the way of reading or writing. It has a simple
layout, uninteresting colours, and a system font stack that matches with the
user's OS.

The theme has
[nice basic typography](_posts/2019-08-01-basics.md)
and lots of typographical extras like
[figures](_posts/2019-08-02-figures.md),
[code highlighting](_posts/2019-08-03-code-blocks.md),
[`<kbd>` and `<samp>` styling](_posts/2019-08-05-kbd-and-samp.md),
[footnotes](_posts/2019-08-06-footnotes.md),
[emoji](_posts/2019-08-11-emoji.md),
[alerts](_posts/2019-09-09-alert-boxes.md),
[lead paragraphs](_posts/2019-09-09-lead-paragraphs.md),
[badges](_posts/2019-09-13-badges-and-pills.md)
and more.

It also has convenient links for [creating](_posts/2019-11-11-new-post-form.md)
and [editing](_posts/2019-11-11-edit-page-and-view-source-buttons.md) pages
and supports [drafts](_posts/2019-12-22-drafts.md) even on GitHub Pages.

See the posts for the [full list of features](#posts).

Using with GitHub Pages
-----------------------

1. Add the theme to your `_config.yml` file with the `remote_theme` setting, and
   also add the [jekyll-feed plugin](https://github.com/jekyll/jekyll-feed)
   that the theme needs:

   ```yaml
   remote_theme: seanh/jekyll-theme-oatcake@0.1.3
   plugins:
   - jekyll-feed
   ```
   
   <div class="tip" markdown="1">
   You'll want to change the `@0.1.3` part at the end of the theme name to
   the [the latest version of the theme]({{ site.github.repository_url }}/releases).

   When new versions of the theme are released you update this theme version number in your
   `_config.yml` file, commit it, and push it to GitHub, and GitHub pages will rebuild your
   site with the new version of the theme.

   See [jekyll-remote-theme](https://github.com/benbalter/jekyll-remote-theme) for more about
   how GitHub Pages handles GitHub-hosted Jekyll themes.
   </div>

2. Include the list of blog posts in a page somewhere, by using this include:

   ```liquid
   {% raw %}{% include post_list.html %}{% endraw %}
   ```

   For example you might want to include it on your front page, or on a `/posts` page.

Posts
-----

{% include post_list.html %}

Contributing
------------

Bug reports and pull requests are welcome on GitHub at <https://github.com/seanh/jekyll-theme-oatcake/>.
