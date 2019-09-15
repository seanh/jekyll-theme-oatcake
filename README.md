jekyll-theme-seanh
==================

My Jekyll theme, as used on [seanh.cc](https://seanh.cc/).
A very plain and simple [Jekyll](https://jekyllrb.com/) / [GitHub Pages](https://pages.github.com/)
theme with a system font stack and hopefully decent typography. Has a lot of
typographical details like `<kbd>` and `<samp>` support, figures with captions,
and emojis.

Demo site: <https://seanh.github.io/jekyll-theme-seanh/>

Using with GitHub Pages
-----------------------

1. Add the theme to your `_config.yml` file with the `remote_theme` setting, and
   also add the non-default plugins that the theme needs:

   ```yaml
   remote_theme: seanh/jekyll-theme-seanh
   plugins:
     - jekyll-mentions
     - jemoji
     - jekyll-avatar
     - jekyll-feed
     - jekyll-seo-tag
     - jekyll-sitemap
   ```

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

License
-------

The theme is available as open source under the terms of the [MIT License](https://opensource.org/licenses/MIT).
