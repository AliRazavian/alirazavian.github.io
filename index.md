---
layout: default
---

<div class="home">
  
    <ul>
    {% for post in site.posts %}
        <li>
        <a href="{{ post.url }}">{{ post.title }}</a>
        </li>
    {% endfor %}
    </ul>

</div>