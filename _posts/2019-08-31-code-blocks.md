Code Blocks
===========

Code blocks use the [gruvbox colour scheme](https://github.com/morhetz/gruvbox).
Here's what a basic code block looks like:

    def test_validate_url_returns_an_http_url_unmodified():
        url = 'http://github.com/jimsmith'

        validated_url = validate_url(url)

        assert validated_url == 'http://github.com/jimsmith'

If a code block is too long it'll get a horizontal scrollbar, rather than
stretching the entire page:

    def test_validate_url_returns_an_http_url_unmodified():
        assert validate_url('http://github.com/jimsmith') == 'http://github.com/jimsmith'

You can use bold text in code blocks:

<pre><code>def test_validate_url_returns_an_http_url_unmodified():
    url = 'http://github.com/jimsmith'

    validated_url = <strong>validate_url(url)</strong>

    assert validated_url == 'http://github.com/jimsmith'</code></pre>

To use Python syntax highlighting begin the code block with
<code>```python</code>.  For example this:

    ```python
    def test_validate_url_returns_an_http_url_unmodified():
        url = 'http://github.com/jimsmith'
        validated_url = validate_url(url)
        assert validated_url == 'http://github.com/jimsmith'
    ```

will render like this:

```python
def test_validate_url_returns_an_http_url_unmodified():
    url = 'http://github.com/jimsmith'
    validated_url = validate_url(url)
    assert validated_url == 'http://github.com/jimsmith'
```

You can also use [Jekyll's {% raw %}`{% highlight %}`{% endraw %} tag](https://jekyllrb.com/docs/liquid/tags/#code-snippet-highlighting)
for code highlighting, and this allows you to turn on line numbers with the
`linenos` option. For example: `{% raw %}{% highlight ruby linenos %}{% endraw %} ... {% raw %}{% endhighlight %}{% endraw %}`:

{% highlight ruby linenos %}
def foo
  puts 'foo'
end
{% endhighlight %}

<code>```shell</code> (or <code>```sh</code> <code>```bash</code>
<code>```ksh</code> or <code>```zsh</code>) is for highlighting shell scripts,
_not_ interactive shell sessions:

```sh
# Loop over every $python_version in the .python-version file.
while IFS= read -r python_version
do
    pyenv install --skip-existing "$python_version"
    if ! "$(pyenv root)/versions/$python_version/bin/tox" --version > /dev/null 2>&1
    then
        "$(pyenv root)/versions/$python_version/bin/pip" install --quiet --disable-pip-version-check tox > /dev/null
    fi
done < .python-version
```

For an _interactive_ shell session use <code>```console</code>,
<code>```terminal</code>, <code>```shell_session</code> or
<code>```shell-session</code>:

```terminal
$ git clone https://github.com/hypothesis/bouncer.git
Cloning into 'bouncer'...
warning: templates not found in /home/seanh/.config/git/template
remote: Enumerating objects: 1766, done.
remote: Total 1766 (delta 0), reused 0 (delta 0), pack-reused 1766
Receiving objects: 100% (1766/1766), 954.14 KiB | 2.16 MiB/s, done.
Resolving deltas: 100% (1044/1044), done.
$ cd bouncer
$ export DEBUG=yes                               # Turn on debug mode.
$ export HYPOTHESIS_URL="http://localhost:5000"  # The URL of the Hypothesis instance to use.
$ make dev
[2019-08-31 19:32:13 +0100] [17902] [INFO] Starting gunicorn 19.9.0
[2019-08-31 19:32:13 +0100] [17902] [INFO] Listening at: http://127.0.0.1:8000 (17902)
[2019-08-31 19:32:13 +0100] [17902] [INFO] Using worker: sync
[2019-08-31 19:32:13 +0100] [17905] [INFO] Booting worker with pid: 17905
```

Here's the [full list of languages supported](https://github.com/rouge-ruby/rouge/wiki/List-of-supported-languages-and-lexers)
for syntax highlighting.

Representing Variables with `<var>`
-----------------------------------

You can also represent the name of a variable by using [the `<var>` tag](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/var):

The variables <var>minSpeed</var> and <var>maxSpeed</var> control the minimum
and maximum speed of the apparatus in revolutions per minute (RPM).
