---
layout: default
---

<div class="home">
  
    <ul>
    {% for post in site.posts %}
        <li>
        <a href="{{ post.url }}">{{ post.title }}</a>
        </li>
        <script src="https://utteranc.es/client.js"
        repo="[ENTER REPO HERE]"
        issue-term="title"
        theme="github-dark"
        crossorigin="anonymous"
        async>
</script>
    {% endfor %}
    </ul>

</div>