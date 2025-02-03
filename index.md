---
layout: default
---
<div id="indexPageContent">
  <div id="articles" style="width: 40%; float: left; padding-right: 5%; padding-left: 5%;">
    <h3>Articles</h3>

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
