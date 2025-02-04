---
layout: default
---
<div id="indexPageContent">
  <div id="articles">
    <h2>Mojo Language</h2>

      {% for post in site.categories['Tech Article'] %}
    <ul>
        <li>
          <a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a><br/>
          Created: {{ post.date | date: "%-d %B %Y" }} Modified: {{ post.modifiedDate | date: "%-d %B %Y" }}<br/>
          tags: {{ post.tags | join: " - " }}
        </li>
    </ul>
    <br/>
      {% endfor %}
  </div>

</div>
