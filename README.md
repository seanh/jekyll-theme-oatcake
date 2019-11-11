jekyll-theme-seanh
==================

This is the [GitHub Pages](https://pages.github.com/) theme that I use on
[seanh.cc](https://seanh.cc/). Theme demo site: <https://seanh.github.io/jekyll-theme-seanh/>

Running Locally
---------------

**See also:**
GitHub's instructions for [running a GitHub Pages site locally](https://help.github.com/en/articles/setting-up-your-github-pages-site-locally-with-jekyll)
using the GitHub Pages gem.

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

Publishing a Release
--------------------

Just create a new tag and [GitHub release](https://github.com/seanh/jekyll-theme-seanh/releases).

GitHub Pages sites can then upgrade to the new version by bumping the version number in their
`_config.yml` files: `remote_theme: seanh/jekyll-theme-seanh@X.Y.Z`

See the [jekyll-remote-theme](https://github.com/benbalter/jekyll-remote-theme) plugin that
GitHub Pages uses for building sites with GitHub-hosted themes.
