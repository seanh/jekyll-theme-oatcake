New Post Form
=============

As well as the [Edit and View Source links](./2019-11-11-edit-page-and-view-source-buttons.md)
the `☰` menu in the bottom-right of every page also includes a
<kbd>New</kbd> button that opens a modal dialog with a form
for quickly creating a new post on GitHub.

When submitted the new post form opens GitHub's <samp>New File</samp> page with
the path, filename and commit message pre-filled based on the title you enter.
You can type the body of your post and just click GitHub's <kbd>Create new
file</kbd> button. A new post created in this way is a
[draft](./2019-12-22-drafts.md) by default so you can save the file to GitHub
without it appearing on your site yet.  To publish the post just delete the
pre-filled YAML front matter from the file.

To remove the New Post link `new_post_link: false` in your `_config.yml`:

```yaml
new_post_link: false
```
