# Game Modding | Black Ops 3

### After months of agony, Black Ops 3 finally has public development tools!

At first they can be a little intimidating for new modders, but fear not - Modme will be creating a comprehensive wiki full of tutorials and guides for your viewing pleasure, to assist all of you with your projects. Fresh blood will get all the starting information they need, while experienced and advanced modders will be contributing their own knowledge and methods too.

Here are some quick links to get you started if you're new to the scene:

**Zombies Fundamentals: _essential for zombiemode maps_**
- [Setup Perks]({{ '/wiki/black_ops_3/basics/Setting-up-perk-machines.html' | relative_url }})
- [Setup Mysterybox]({{ '/wiki/black_ops_3/basics/Setting-up-mystery-box.html' | relative_url }})
- [Setup Zones]({{ '/wiki/black_ops_3/basics/Setting-up-zones.html' | relative_url }})
- [Setup Powerswitch]({{ '/wiki/black_ops_3/basics/Setting-up-a-proper-power-switch.html' | relative_url }})
- [Setup Traps]({{ '/wiki/black_ops_3/basics/Setting-up-traps.html' | relative_url }})

**Beginner Guides:**
- [Scripting Guide]({{ '/wiki/black_ops_3/guides/Scripting-guide.html' | relative_url }})
- [Weapon Porting]({{ '/wiki/black_ops_3/guides/Weapon-Porting.html' | relative_url }})

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