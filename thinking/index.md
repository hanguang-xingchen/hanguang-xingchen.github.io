---
title: Thinking
layout: thinking
---

<div class="thinking-index">
{% assign articles = site.pages | where_exp: "item", "item.path contains 'thinking/20'" | where_exp: "item", "item.name != 'index.md'" | sort: 'date' | reverse %}
{% for article in articles %}
<div class="thinking-entry">
    <div class="thinking-date">{{ article.date | date: '%Y-%m-%d' }}</div>
    <div class="thinking-title"><a href="{{ article.url | relative_url }}">{{ article.title }}</a></div>
    <div class="thinking-preview">{{ article.content | strip_html | truncate: 150 }}</div>
</div>
{% endfor %}
</div>
