---
sitemap: false
robots: noindex, nofollow
---
<ul class="posts-list">
  {% for post in site.posts %}
    {% unless post.draft %}{% continue %}{% endunless %}
    {% include post_link.html post=post %}
  {% endfor %}
</ul>
