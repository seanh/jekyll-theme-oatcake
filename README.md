# jekyll-theme-seanh

Welcome to your new Jekyll theme! In this directory, you'll find the files you need to be able to package up your theme into a gem. Put your layouts in `_layouts`, your includes in `_includes`, your sass files in `_sass` and any other assets in `assets`.

To experiment with this code, add some sample content and run `bundle exec jekyll serve` – this directory is setup just like a Jekyll site!

TODO: Delete this and the text above, and describe your gem


## Installation

Add this line to your Jekyll site's `Gemfile`:

```ruby
gem "jekyll-theme-seanh"
```

And add this line to your Jekyll site's `_config.yml`:

```yaml
theme: jekyll-theme-seanh
```

And then execute:

    $ bundle

Or install it yourself as:

    $ gem install jekyll-theme-seanh

## Usage

TODO: Write usage instructions here. Describe your available layouts, includes, sass and/or assets.

## Contributing

Bug reports and pull requests are welcome on GitHub at https://github.com/[USERNAME]/hello. This project is intended to be a safe, welcoming space for collaboration, and contributors are expected to adhere to the [Contributor Covenant](http://contributor-covenant.org) code of conduct.

## Development

To set up your environment to develop this theme, run `bundle install`.

Your theme is setup just like a normal Jekyll site! To test your theme, run `bundle exec jekyll serve` and open your browser at `http://localhost:4000`. This starts a Jekyll server using your theme. Add pages, documents, data, etc. like normal to test your theme's contents. As you make modifications to your theme and to your content, your site will regenerate and you should see the changes in the browser after a refresh, just like normal.

When your theme is released, only the files in `_layouts`, `_includes`, `_sass` and `assets` tracked with Git will be bundled.
To add a custom directory to your theme-gem, please edit the regexp in `jekyll-theme-seanh.gemspec` accordingly.

### CSS

The CSS uses the [BEM (Block Element Modifier) method](http://getbem.com/) for modularity:

* All CSS selectors match using CSS class names only, no tag names or IDs.

* Blocks (standalone entities) have simple ASCII names like `"site-search"`.

  You know something is a block if it's a standalone entity that is meaningful
  on its own. Blocks can still interact with each other and can be nested
  inside of each other, but are semantically equal with no precedence or
  hierarchy.

* Elements (sub-parts of blocks) are named like `"block__element"`, for example `"site-search__field"`.

  You know something is an element, rather than a block, if it's semantically
  tied to its block and has no semantic meaning of its own.

  Instead of a traditional CSS selector like `.block element { ... }` you'd use `.block__element { ... }`.

* Modifiers are flags on block or elements, `"<BLOCK>--<MODIFIER>"` or `"<BLOCK>__<ELEMENT>--<MODIFIER>"`,
  for example `"site-search--full"` or `"person__hand--left"`.

  You only use these on HTML tags that also have the corresponding block or element.
  For example `<div class="site-search site-search--full">` or
  `<div class="person__hand person__hand--left">`.

  1. Block modifier: `.block--modifier { ... }`
  2. Block's elements modifier - in the HTML the modifier class is added to the
     block tag but modifies its elements: `.block--modifier block__element { ... }`
  3. Element modifier - in the HTML the modifier is added to the element's tag
     directly: `.block__element--modifier { ... }`

* Single dashes are allowed within the name of a block, element or modifier.

Complete example:

```html
<style>
    .form { }
    .form--theme-xmas { }
    .form--simple { }
    .form__input { }
    .form__submit { }
    .form__submit--disabled { }
</style>

<form class="form form--theme-xmas form--simple">
  <input class="form__input" type="text" />
  <input
    class="form__submit form__submit--disabled"
    type="submit" />
</form>
```

## License

The theme is available as open source under the terms of the [MIT License](https://opensource.org/licenses/MIT).

