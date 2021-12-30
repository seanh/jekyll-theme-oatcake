User Input: `<kbd>` and `<samp>`
================================

The theme supports user input with [the `<kbd>` element](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/kbd)
and sample output with [the `<samp>` element](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/samp).

Sample Output with `<samp>`
---------------------------

To represent sample or quoted output from a computer program, wrap it in
`<samp>` tags: <samp>Keyboard not found. Press F1 to continue</samp>

User Input with `<kbd>`
-----------------------

To represent user input from a keyboard or any other text entry device wrap it
in `<kbd>` tags: <kbd>help mycommand</kbd>

You can use nested `<kbd>`'s to represent multiple keystrokes that form a
single input: <kbd><kbd>Ctrl</kbd> + <kbd>c</kbd></kbd>.

Up to two levels of nesting are supported by the CSS:
<kbd><kbd><kbd>Ctrl</kbd> + <kbd>b</kbd></kbd> <kbd><kbd>Shift</kbd> + <kbd>t</kbd></kbd></kbd>.

Representing Onscreen Input Options by Nesting `<samp>` within `<kbd>`
----------------------------------------------------------------------

A `<samp>` inside a `<kbd>` represents input **that is based on text presented
by the system**, such as selecting menu items or clicking on buttons:

> To create a new file, choose the menu option
> <kbd><kbd><samp>File</samp></kbd> &rarr; <kbd><samp>New Document</samp></kbd></kbd>.
>
> Don't forget to click the <kbd><samp>OK</samp></kbd> button
> to confirm once you've entered the name of the new file.

Representing Echoed Input by Nesting `<kbd>` within `<samp>`
------------------------------------------------------------

A `<kbd>` inside a `<samp>` represents input that has been echoed back to the
user by the system:

> If a syntax error occurs, the tool will output the initial
> command you typed for your review:
> > <samp><kbd>custom-git add my-new-file.cpp</kbd></samp>

Another usage for this is showing the output of a terminal session as a
`<samp>` inside a `<pre>`, and with the user-entered parts as `<kbd>`'s inside
the `<samp>`:

<pre><samp>mike@interwebz:~$ <kbd>md5 -s "Hello world"</kbd>
MD5 ("Hello world") = 3e25960a79dbc69b674cd4ec67a72c62

mike@interwebz:~$ █</samp></pre>
