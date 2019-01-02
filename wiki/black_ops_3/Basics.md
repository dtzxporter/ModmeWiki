# Basics

If it's your first time modding, the tools can be a little intimidating at first, so here are some tutorials to get you started.

**Zombies Fundamentals: _essential for ZM maps_**

- [Setup Perks]({{ '/wiki/black_ops_3/basics/Setting-up-perk-machines.html' | relative_url }})
- [Setup Mysterybox]({{ '/wiki/black_ops_3/basics/Setting-up-mystery-box.html' | relative_url }})
- [Setup Zones]({{ '/wiki/black_ops_3/basics/Setting-up-zones.html' | relative_url }})
- [Setup Powerswitch]({{ '/wiki/black_ops_3/basics/Setting-up-a-proper-power-switch.html' | relative_url }})
- [Setup Traps]({{ '/wiki/black_ops_3/basics/Setting-up-traps.html' | relative_url }})

---

`See the Document Hierarchy below to explore.`

<ul>
  {% for post in site.pages %}
    {% if post.path contains 'wiki/black_ops_3/basics' %}
    <li>
      <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
    </li>
    {% endif %}
  {% endfor %}
</ul>