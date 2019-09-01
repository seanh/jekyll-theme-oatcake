Insertions, Deletions and Highlights
====================================

You can represent text that has been deleted from a document by wrapping it in
[`<del>` tags](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/del)
or in `~~`'s (like this: `~~deleted text~~`):

Sean Hammond is a software developer working for Hypothesis and living in
<del>Berlin</del> Edinburgh.

You can also represent text that has been _inserted_ into a document with
[`<ins>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ins):

Sean Hammond is a software developer working for Hypothesis and living in
<del>Berlin</del> <ins>Edinburgh</ins>.

Finally, you can represent text that has been marked or highlighted for
relevance or importance by using [`<mark>` tags](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/mark):

<mark>Sean Hammond</mark> is a software developer working for Hypothesis and living in
<del>Berlin</del> <ins>Edinburgh</ins>.
