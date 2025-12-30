---
layout: default
---

<div class="home">

  <p>Blog bem despretensioso, com posts ocasionais sobre qualquer assunto, mas principalmente jogos.</p>

  {% assign latest = site.posts.first %}
  {% if latest %}
    <hr />

    <h2>Último post</h2>

    <h1><a href="{{ latest.url | relative_url }}">{{ latest.title }}</a></h1>
    <p><small>{{ latest.date | date: "%d/%m/%Y" }}</small></p>

    <div class="post-content">
      {{ latest.content }}
    </div>

    <hr />

    <h2>Posts anteriores</h2>
    <ul>
      {% for post in site.posts offset:1 limit:10 %}
        <li>
          <small>{{ post.date | date: "%d/%m/%Y" }}</small>
          — <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
        </li>
      {% endfor %}
    </ul>
  {% else %}
    <p>Ainda não há posts.</p>
  {% endif %}

</div>
