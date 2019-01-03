# In-depth Guides

In-depth guides for common modding tasks.

---

`See the Document Hierarchy below to explore.`

<ul>
  {% for post in site.pages %}
    {% if post.path contains 'wiki/black_ops_3/guides' %}
    <li>
      <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
    </li>
    {% endif %}
  {% endfor %}
</ul>