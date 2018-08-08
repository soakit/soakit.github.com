---
layout: default
title: "分类：Categories"
---

<ul class="list-unstyled">
{% for cat in site.categories %}
    <li class="{{cat[0]}}">
      <h2>{{ cat[0] }}({{ cat[1].size }})</h2>
      <ul class="list-unstyled">
        {% for post in cat[1] %}
          <li>
            <h4>
              <span class="btn-group" style="min-width: 108px;">{{ post.date | date_to_string }}</span> &raquo;&nbsp;&nbsp;
              <a href="{{ post.url }}">{{ post.title }}</a>
            </h4>
          </li>
	      {% endfor %}
      </ul>
    </li>
{% endfor %}
</ul>
