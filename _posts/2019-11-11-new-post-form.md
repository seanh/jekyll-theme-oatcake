New Post Form
=============

The [`new_post_form.html`]({{ site.github.repository_url }}/blob/master/_includes/new_post_form.html) include renders a form
for quickly creating a new post on GitHub:

{% include new_post_form.html %}

The form opens GitHub's <samp>New File</samp> page with the path, filename and commit message pre-filled based on the title you enter.
You can type the body of your post and just click GitHub's <kbd>Create new file</kbd> button. A new post created in this way
is a draft by default so you can save the file to GitHub without it appearing on your site yet.
To publish the post just delete the pre-filled YAML front matter from the file.

To add a new post form like the one above to your site just call the `new_post_form.html` include like this:
`{% raw %}{% include new_post_form.html %}{% endraw %}`. You could put this in a `new.md` file and then just visit
`YOUR_SITE.com/new` whenever you want to create a new post. See
[`{{ site.github.hostname }}/{{ site.github.repository_nwo }}/new.md`](https://raw.githubusercontent.com/{{ site.github.repository_nwo }}/master/new.md)
for an example.
