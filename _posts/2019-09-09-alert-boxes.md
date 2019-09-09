Alert Boxes
===========

You can create alert boxes of various kinds using the CSS classes
`admonition`, `warning`, `tip`, `note`, `seealso` and `todo`.
These are meant to be similar to
[Bootstrap's alerts](https://getbootstrap.com/docs/4.1/components/alerts/),
[Semantic UI's messages](https://semantic-ui.com/collections/message.html),
or the various [admonitions](http://docutils.sourceforge.net/docs/ref/rst/directives.html#attention)
and [see also's](https://www.sphinx-doc.org/en/master/extdev/nodes.html?highlight=admonition#sphinx.addnodes.seealso)
etc provided by reStructuredText and Sphinx.

To use an alert write a `<div>` with a CSS class on it, like this:

```html
<div class="note">
This is a note.
</div>
```

If you want to use Markdown rather than raw HTML inside the `<div>` then add a
`markdown="1"` attribute to it:

```html
<div class="note" markdown="1">
Now I can use things like Markdown `code` and [links](example.com).
</div>
```

Here are all the available styles:

<div class="admonition">
This is a generic admonition.
</div>

<div class="warning" markdown="1">
This is a warning box.
Also known as an `attention`, `caution`, `danger`, `error`, or `important` box.
</div>

<div class="tip" markdown="1">
This is a `tip` or `hint` box.
</div>

<div class="note">
This is a note.
</div>

<div class="seealso">
This is a seealso.
</div>

<div class="todo">
This is a todo.
</div>

All of the alert box styles have special colors for links:

<div class="admonition" markdown="1">
This is a generic admonition [with a link](example.com) in it.
</div>

<div class="warning" markdown="1">
This is a warning [with a link](example.com) in it.
</div>

<div class="tip" markdown="1">
This is a tip or hint [with a link](example.com) in it.
</div>

<div class="note" markdown="1">
This is a note [with a link](example.com) in it.
</div>

<div class="seealso" markdown="1">
This is a seealso [with a link](example.com) in it.
</div>

<div class="todo" markdown="1">
This is a todo [with a link](example.com) in it.
</div>

You can put arbitrary HTML inside alert boxes (remember your `markdown="1"` if
using Markdown):

<div class="todo" markdown="1">
### Todo

> * List item one
> * List item two
> * List item three

* * *

Aliquam eu quam blandit, condimentum velit nec, hendrerit urna.
</div>
