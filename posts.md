<ul style="list-style-type: none;">
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
      <span class="muted">{{ post.date | date: "%b %Y" }}</span>
    </li>
  {% endfor %}
</ul>
