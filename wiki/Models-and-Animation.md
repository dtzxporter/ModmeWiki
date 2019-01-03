# Models And Animation

A set of tutorials regarding animating and models for games, not specifically for Call of duty. Posts will be listed as "Title [game] (software)".

---

`See the Document Hierarchy below to explore.`

<ul>
  {% for post in site.pages %}
    {% if post.path contains 'wiki/models_and_animation' %}
    <li>
      <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
    </li>
    {% endif %}
  {% endfor %}
</ul>