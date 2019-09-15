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

Running Locally
---------------

<div class="seealso" markdown="1">
**See also:**
GitHub's instructions for [running a GitHub Pages site locally](https://help.github.com/en/articles/setting-up-your-github-pages-site-locally-with-jekyll)
using the GitHub Pages gem.
</div>

To install and run this theme and demo site locally:

1. Install Ruby (2.1 or newer), Bundler and git:

   ```
   sudo apt install ruby bundler git
   ```
2. Clone this repo and cd into it:

   ```
   git clone https://github.com/seanh/jekyll-theme-seanh.git
   cd jekyll-theme-seanh
   ```

3. Install Jekyll and other dependencies:

   ```
   bundle install --path vendor/bundle
   ```

4. Finally, serve the site at <http://localhost:4000/jekyll-theme-seanh/>:

   ```
    bundle exec jekyll serve
    ```

You should run `bundle-update` now and then to keep up to date with the GitHub
Pages gem.

### Publishing a Release

To release a new version of the theme to [RubyGems](https://rubygems.org/gems/jekyll-theme-seanh):

1. Update the version number in
   [jekyll-theme-seanh.gemspec]({{ site.github.repository_url }}/blob/master/jekyll-theme-seanh.gemspec)
   and commit the change to git.

2. Package the new version of the theme:

   ```
   gem build jekyll-theme-seanh.gemspec
   ```

3. Upload the packaged theme to RubyGems:

   ```
   gem push jekyll-theme-seanh-X.Y.Z.gem
   ```

Contributing
------------

Bug reports and pull requests are welcome on GitHub at <https://github.com/seanh/jekyll-theme-seanh/>.

License
-------

The theme is available as open source under the terms of the [MIT License](https://opensource.org/licenses/MIT).
