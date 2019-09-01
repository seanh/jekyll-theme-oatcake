Abbreviations and Acronyms
==========================

You can mark up an abbreviation using the `<abbr>` tag. For example this:

```html
<abbr title="World Wide Web">WWW</abbr>
```

renders like this: <abbr title="World Wide Web">WWW</abbr>.

There's also `<acronym>`, which works the same:
<acronym title="National Aeronautics and Space Administration">NASA</acronym>.

Kramdown also provides a way to [define abbreviations and have them be marked up in the text automatically](https://kramdown.gettalong.org/syntax.html#abbreviations).
For example this:

    This is some text not written in HTML but in another language!

    *[another language]: It's called Markdown

    *[HTML]: HyperTextMarkupLanguage

renders like this:

This is some text not written in HTML but in another language!

*[another language]: It's called Markdown

*[HTML]: HyperTextMarkupLanguage


