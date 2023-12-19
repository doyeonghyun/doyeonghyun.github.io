---
layout: page
title: 포트폴리오
permalink: /portfolio/
jekyll-theme-WuK:
  default:
    sidebar:
      open: true
  tags:
    vega_lite: # 통계 그래프 표시, vega-lite를 가져와야 함
      enable: true
---

모든 게시글의 카탈로그는 태그로 분류됩니다.

{% if page.jekyll-theme-WuK.tags.vega_lite.enable %}
  {% assign portfolio_posts = site.posts | where_exp: "post", "post.path contains '/portfolio/'" %}
  {% capture json_data %}
  [
    {% for tag in portfolio_posts | group_by: 'tags' %}
      {"tags": "{{ tag.name }}", "count": {{ tag.size }} },
    {% endfor %}
  ]
  {% endcapture %}
  {% assign json_data = json_data | remove_first: "," %}
  {
    "data": { "values": {{ json_data }} },
    "encoding": {
      "y": {"field": "tags", "type": "nominal"},
      "x": {"field": "count", "type": "quantitative" }
    },
    "mark": "bar"
  }
{% endif %}

{% for tag in portfolio_posts | group_by: 'tags' %}
  ## {{ tag.name }}
  {% for post in tag.items %}
    - *{{ post.date | date_to_string }}* [{{ post.title }}]({{ post.url | relative_url }})
  {% endfor %}
{% endfor %}
