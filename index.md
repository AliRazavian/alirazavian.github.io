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
            repo="AliRazavian/alirazavian.github.io"
            issue-term="url"
            theme="preferred-color-scheme"
            crossorigin="anonymous"
            async>
    </script>
</script>
    {% endfor %}
    </ul>

</div>