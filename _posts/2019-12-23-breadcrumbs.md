---
categories: [Example Category, Another Category]
---

Page and post headings have a line of navigation breadcrumbs beneath the title.
For example, here are this page's breadcrumbs:

<p>
{% include breadcrumbs.html omit_date=false %}
</p>

Breadcrumbs help users locate themselves within the hierarchy of your site.
While [header links](./2019-11-25-header-and-footer-links.md)
act as the site's primary navigation,
breadcrumbs show the user exactly where they currently are. They show the
path from the home page down to the current page and provide links for moving back
up the site hierarchy.

The breadcrumbs are made up of:

* A breadcrumb for the site's front page: **Home** in this post's breadcrumbs
* A breadcrumb for the page or post's collection, if it has one: **> Posts** in this post's breadcrumbs
  (posts belong to the collection "posts" by default)
* One breadcrumb for each of the page or post's categories, if it has any:
  **> Example Category** and **> Another Category** in this post's breadcrumbs
* For posts: breadcrumbs for the post's year, month and day: **> 2019 > Dec > 23** in this post's breadcrumbs
* Finally, a breadcrumb for the page or post's title: **> Breadcrumbs** for this post

Creating pages for breadcrumbs to link to
-----------------------------------------

Breadcrumbs will automatically find and link to their corresponding pages if they exist:

* If the site has a front page then the **Home** breadcrumb will be a link to the front page

* If there's a page whose URL matches the page or post's collection, the collection breadcrumb will be a link to that page.

  For example to create a page for the default "posts" collection create a `posts.md` or `posts/index.md` file.
  You might use this page to [render a list of all your posts](../example-category/_posts/2019-12-22-post-lists.md#listing-all-published-posts).

  The collection page's URL must be equal to the name of the collection with spaces replaced by `-`'s and uppercase letters downcased.
  For example a `Foo Bar` collection would match a page with a `/foo-bar/` URL.

* For each category, if there's a page whose URL matches the category's name then the category's breadcrumb will be a link to that page.

  For example to create a page for "Example Category" create a `example-category.md` or `example-category/index.md` file
  (as with collection pages: replacing spaces with `-`'s and downcasing uppercase letters).

  You might use this page to [list all posts in the category](../example-category/_posts/2019-12-22-post-lists.md#listing-posts-in-a-category).

* For a post's year, month and day, if there's a page whose URL matches that
  year, month, or day, then the year, month or day breadcrumb will link to it.

  For example the breadcrumb for the year 2019 will match a `2019.md` or `2019/index.md` file.
  You could use this page to list all posts from 2019.

  December 2019 matches a `2019/12.md` or `2019/12/index.md` file,
  and 23rd December 2019 matches a `2019/12/23.md` or `2019/12/23/index.md` file.

Controlling breadcrumb text
---------------------------

Whenever a breadcrumb finds a corresponding page to link to, it also takes on that page's title as the breadcrumb text.

For example if the `example-category.md` page has the title "All Posts in
Example Category" then "All Posts in Example Category" will appear as the
breadcrumb text for the category, in the breadcrumbs of posts that belong to
the category.

Or if `posts.md` has the title "Archive" then the post's collection will appear
as "Archive" in the breadcrumbs of posts belonging to that collection.

The title of the front page of the site (the top-level `index.md` file)
controls the text of the Home breadcrumb.

You can override this for any page by adding a `breadcrumb_text` variable to the page's frontmatter:

```yaml
---
breadcrumb_text: Example Category
---

All Posts in Example Category
=============================

...
```

Hiding breadcrumbs
------------------

You can turn off any of the breadcrumb components using these `_config.yml` settings:

`breadcrumbs_omit_home: true`
: Hide the home breadcrumb

`breadcrumbs_omit_collection: true`
: Hide the collection breadcrumb

`breadcrumbs_omit_categories: true`
: Hide the category breadcrumbs

`breadcrumbs_omit_date: true`
: Hide the year, month and day breadcrumbs for posts

`breadcrumbs_omit_year: true`
: Hide just the year breadcrumb for posts

`breadcrumbs_omit_month: true`
: Hide just the month breadcrumb for posts

`breadcrumbs_omit_day: true`
: Hide just the day breadcrumb for posts

For example, here are this page's breadcrumbs with `omit_collection: true` and `omit_date: true`:

<p>
{% include breadcrumbs.html omit_collection=true omit_date=true %}
</p>

Making breadcrumbs match URLs
-----------------------------

You might want your pages' and posts' breadcrumbs to match the `/`-separated parts of their permalink URLs.
You can achieve this either by changing your [`permalink` setting](https://jekyllrb.com/docs/permalinks/)
in `_config.yml` to match the default breadcrumbs or by configuring the
breadcrumbs to match your `permalink` setting.

For example this permalink setting:

```yaml
permalink: /:collection/:categories/:year/:month/:day/:title/
```

will make your permalink URLs match the default breadcrumbs.

Another example: if you use the built-in `permalink: pretty` format then adding
this breadcrumbs setting to `_config.yml` will change your breadcrumbs to match
your pretty permalinks:

```yaml
breadcrumbs_omit_collection: true
```
