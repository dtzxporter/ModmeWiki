# Game Modding | Black Ops 3

## After months of agony, Black Ops 3 finally has public development tools!

At first they can be a little intimidating for new modders, but fear not - Modme will be creating a comprehensive wiki full of tutorials and guides for your viewing pleasure, to assist all of you with your projects. Fresh blood will get all the starting information they need, while experienced and advanced modders will be contributing their own knowledge and methods too.

Here are some quick links to get you started if you're new to the scene:

**Zombies Fundamentals: _essential for zombiemode maps_**
- [[black_ops_3/basics/setup_perks]]
- [[black_ops_3/basics/setup_mystery_box]]
- [[black_ops_3/basics/setup_zones]]
- [[black_ops_3/basics/setup_power_switch]]
- [[black_ops_3/basics/setup_traps]]

**Beginner Guides:**
- [[black_ops_3/guides/scripting_guide]]
- [[black_ops_3/guides/weapon_porting]]

---

`See the Document Hierarchy below to explore.`

<ul>
  {% for post in site.pages %}
    {% if post.path contains 'wiki/black_ops_3' %}
    <li>
      <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
    </li>
    {% endif %}
  {% endfor %}
</ul>