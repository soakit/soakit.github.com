---
layout: default
title: Tags
---
<ul class="list-unstyled">
{% for tag in site.tags %}
    <li class="{{tag[0]}}">
      <h2>{{ tag[0] }}({{ tag[1].size }})</h2>
      <ul class="list-unstyled">
        {% for post in tag[1] %}
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