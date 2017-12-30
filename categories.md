---
layout: default
title: "Categories"
---

<div class="post">
  <h2 class="pageTitle">Categories</h2>

  {% for category in site.categories %}
    <div class="category-space">
      {% capture category_name %}{{ category | first }}{% endcapture %}
      <div id="#{{ category_name | slugify }}"></div>
      <p></p>

      <a name="{{ category_name | slugify }}"></a>
      <h4 class="category-head">
        {{ category_name }}
        ({{ site.categories[category_name].size }} notes)
      </h4>

      <ul>
        {% for post in site.categories[category_name] %}
            <li>
              <a href="{{ site.baseurl }}{{ post.url }}">{{post.title}}</a>
            </li>
        {% endfor %}
      </ul>
    </div>
  {% endfor %}
</div>
