---
layout: default
---
<div id="indexPageContent">
  <div id="articles">
    <h2>Mojo Language</h2>

    <ul>
      {% for post in site.categories['Mojo Article'] %}
        <li>
          <a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a><br/>
          Created: {{ post.date | date: "%-d %B %Y" }}<br/>
          Modified: {{ post.modifiedDate | date: "%-d %B %Y" }}<br/>
          tags: {{ post.tags | join: " - " }}<br/>
          {{ post.excerpt }}
        </li>
      {% endfor %}
    </ul>
  </div>

</div>
