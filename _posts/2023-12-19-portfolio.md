---
layout: page
title: 포트폴리오
permalink: /portfolio/
jekyll-theme-WuK:
  default:
    sidebar:
      open: true
  tags:
    vega_lite: # 显示一个统计图，需要引入 vega-lite
      enable: true
---

모든 게시글의 카탈로그는 태그로 분류됩니다.

{% if page.jekyll-theme-WuK.tags.vega_lite.enable %}

```vega-lite
{% capture json_data %}[
{% for tag in site.tags.포트폴리오 reversed %}
 , {"tags": "{{ tag[0] }}", "count": {{ tag[1].size }} }
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

{% for tag in site.tags.포트폴리오 reversed %}
## {{ tag[0] }}

{% for post in tag[1] %}
- *{{ post.date | date_to_string }}* [{{ post.title }}]({{ post.url | relative_url }}){% endfor %}
{% endfor %}
