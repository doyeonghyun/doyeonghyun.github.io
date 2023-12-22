---
layout: page
title: 포트폴리오
permalink: /portfolio/
jekyll-theme-WuK:
  default:
    sidebar:
      open: true
  tags:
    vega_lite:
      enable: true
---

모든 게시글의 카탈로그는 태그로 분류됩니다.

{% if page.jekyll-theme-WuK.tags.vega_lite.enable %}

```vega-lite
{% capture json_data %}[
{% assign target_tag = "포트폴리오" %}
{% for tag in site.tags reversed %}
  {% if tag[0] contains target_tag %}
 , {"tags": "{{ tag[0] }}", "count": {{ tag[1].size }} }
  {% endif %}
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

{% assign target_tags = ["포트폴리오", "테스"] %}

{% for tag in site.tags reversed %} 
  {% if tag[0] contains target_tag %}
## {{ tag[0] }}

{% for post in tag[1] %}
- *{{ post.date | date_to_string }}* [{{ post.title }}]({{ post.url | relative_url }}){% endfor %}
  {% endif %}
{% endfor %}
