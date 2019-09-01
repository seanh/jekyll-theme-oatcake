<ul style="list-style-type: none;">
  {% for post in site.posts %}
    {% if post.draft %}{% continue %}{% endif %}
    {% include post_link.html post=post %}
  {% endfor %}
</ul>
