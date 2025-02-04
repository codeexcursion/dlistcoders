---
layout: default
---
<div id="indexPageContent">
  <div id="articles">
    <h2>Mojo Language</h2>

      {% for post in site.categories['Tech Article'] %}
    <ul>
        <li>
          {{ post.date | date: "%-d %B %Y" }}<br/>
          <a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a><br/>
          tags: {{ post.tags | join: " - " }}
        </li>
    </ul>
    <br/>
      {% endfor %}
  </div>

</div>
