All Posts by Tag
================

<ul>
  {% for tag in site.tags %}
  <li>
    <h3 id="{{ tag[0] }}">{{ tag[0] }}</h3>
    <ul style="list-style-type: none;">
    {% for post in tag[1] %}
      {% if post.draft %}{% continue %}{% endif %}
      {% include post_link.html post=post %}
    {% endfor %}
    </ul>
  </li>
{% endfor %}
  <li>
    <h3 id="Untagged">Untagged</h3>
    <ul style="list-style-type: none;">
    {% for post in site.posts %}
        {% if post.draft %}{% continue %}{% endif %}
        {% if post.tags.size > 0 %}{% continue %}{% endif %}
        {% include post_link.html post=post %}
    {% endfor %}
    </ul>
  </li>
</ul>
