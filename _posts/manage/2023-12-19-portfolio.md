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

해당 페이지는 포트폴리오만 확인할 수 있습니다. 모든 게시글의 카탈로그는 '포트폴리오'라는 단어가 들어간 태그로 분류됩니다.


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

## **아쉽게도 아직 작성한 포트폴리오가 없습니다!** 

빨리 만들어서 올릴게요!

{% endif %}

{% assign target_tag = "포트폴리오" %}

{% for tag in site.tags reversed %} 
  {% if tag[0] contains target_tag %}
## {{ tag[0] }}

{% for post in tag[1] %}
- *{{ post.date | date_to_string }}* [{{ post.title }}]({{ post.url | relative_url }}){% endfor %}
  {% endif %}
{% endfor %}

