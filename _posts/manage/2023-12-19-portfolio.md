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

{% if page.jekyll-theme-WuK.tags.vega_lite.enable %}


```vega-lite
{% capture json_data %}[
{% for tag in site.tags.['포트폴리오'] reversed %}
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

{% for post in site.tags.['포트폴리오'] reversed %}
## {{ post[0] }}

{% for post_item in post[1] %}
- *{{ post_item.date | date_to_string }}* [{{ post_item.title }}]({{ post_item.url | relative_url }})
{% endfor %}
{% endfor %}


***
{% assign i = 0 %}
{% for post in site.posts %}{% assign year = post.date | date: page.jekyll-theme-WuK.archive.group_by %}{% assign nyear = post.next.date | date: page.jekyll-theme-WuK.archive.group_by %}{% if year != nyear > '2023-12-18'  %}

## {{ year }}{% assign i = i | plus: 1 %}

{% endif %}
- _{{ post.date | date_to_string }}_ [{{ post.title }}]({{ post.url | relative_url }}){% endfor %}
