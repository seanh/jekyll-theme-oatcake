jekyll-theme-seanh
==================

This is the [GitHub Pages](https://pages.github.com/) theme that I use on
[seanh.cc](https://seanh.cc/). It's meant to be a plain theme, fast and mobile
friendly, that doesn't get in the way of reading or writing. It has a simple
layout, uninteresting colours, and a system font stack that matches with the
user's OS.

The theme also aims to delight with
[nice typography](_posts/2019-08-01-basics.md)
and features like
[figures](_posts/2019-08-02-figures.md),
[code highlighting](_posts/2019-08-03-code-blocks.md),
[`<kbd>` and `<samp>` styling](_posts/2019-08-05-kbd-and-samp.md),
[footnotes](_posts/2019-08-06-footnotes.md),
[emoji](_posts/2019-08-11-emoji.md),
[alerts](_posts/2019-09-09-alert-boxes.md),
[lead paragraphs](_posts/2019-09-09-lead-paragraphs.md),
[badges](_posts/2019-09-13-badges-and-pills.md)
and more.

See the posts for the [full list of features](posts.md).

Using with GitHub Pages
-----------------------

1. Add the theme to your `_config.yml` file with the `remote_theme` setting, and
   also add the non-default plugins that the theme needs:

   ```yaml
   remote_theme: seanh/jekyll-theme-seanh@0.1.3
   plugins:
     - jekyll-mentions
     - jemoji
     - jekyll-avatar
     - jekyll-feed
     - jekyll-seo-tag
     - jekyll-sitemap
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

   <div class="tip" markdown="1">
   You also have a bunch more plugins available to you by default on GitHub
   Pages, in addition to those listed above. See the [list of plugins installed
   by default on GitHub
   Pages](https://help.github.com/en/articles/configuring-jekyll-plugins#default-plugins).
   </div>

   <div class="tip" markdown="1">
   For a full example configuration with Jekyll settings and settings for a few
   of the plugins, see
   [this demo site's `_config.yml`]({{ site.github.repository_url }}/blob/master/_config.yml).
   </div>

2. Include the list of blog posts in a page somewhere, by using this include:

       {% raw %}{% include post_list.html %}{% endraw %}

   For example you might want to include it on your front page, or on a `/posts` page.
   See [posts.md]({{ site.github.repository_url }}/blob/master/posts.md)
   for an example.

3. If you plan on using tags then copy [tags.md]({{ site.github.repository_url }}/blob/master/tags.md),
   the tags page, to your site.

4. If you want to have a page listing all your draft posts then copy
   [drafts.md]({{ site.github.repository_url }}/blob/master/drafts.md) to your site.

Contributing
------------

Bug reports and pull requests are welcome on GitHub at <https://github.com/seanh/jekyll-theme-seanh/>.