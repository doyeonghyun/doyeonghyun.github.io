---
layout: page
title: 포트폴리오
permalink: /portfolio/
jekyll-theme-WuK:
  default:
    sidebar:
      open: true
  portfolio:
    vega_lite:
      enable: true
---

모든 게시글의 카탈로그는 태그로 분류됩니다.

{% if page.jekyll-theme-WuK.portfolio.vega_lite.enable %}

```vega-lite
{% capture json_data %}[
{% for tag in site.portfolio reversed %}
 , {"tags": "{{ portfolio[0] }}", "count": {{ portfolio[1].size }} }
{% endfor %}
]{% endcapture %}
{% assign json_data = json_data | remove_first: "," %}
{
  "data": { "values": {{ json_data }} },
  "encoding": {
    "y": {"field": "tags", "type": "nominal"},
    "x": {"field": "count", "type": "quantitative" }
  },
  "mark": "bar"
}
```

{% endif %}

{% for tag in site.tags reversed %}
## {{ tag[0] }}

{% for post in tag[1] %}
- *{{ post.date | date_to_string }}* [{{ post.title }}]({{ post.url | relative_url }}){% endfor %}
{% endfor %}
