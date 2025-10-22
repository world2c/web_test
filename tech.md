---
layout: page
title: 科技文章
permalink: /tech/
---

# 📱 科技文章

这里记录我的技术学习笔记、编程经验和科技思考。

---

{% for post in site.posts %}
  {% if post.categories contains 'tech' %}
<article style="margin-bottom: 40px; padding-bottom: 20px; border-bottom: 1px solid #eee;">
  <h2 style="margin-bottom: 10px;">
    <a href="{{ post.url }}" style="color: #0366d6; text-decoration: none;">
      {{ post.title }}
    </a>
  </h2>
  <p style="color: #666; font-size: 14px; margin-bottom: 10px;">
    📅 {{ post.date | date: "%Y年%m月%d日" }}
    {% if post.tags %}
      | 🏷️ 
      {% for tag in post.tags %}
        <span style="background: #f1f1f1; padding: 2px 8px; border-radius: 3px; margin-right: 5px;">{{ tag }}</span>
      {% endfor %}
    {% endif %}
  </p>
  <p style="color: #333; line-height: 1.6;">
    {{ post.excerpt | strip_html | truncate: 200 }}
  </p>
  <a href="{{ post.url }}" style="color: #0366d6;">阅读全文 →</a>
</article>
  {% endif %}
{% endfor %}

{% assign tech_posts = site.posts | where_exp: "post", "post.categories contains 'tech'" %}
{% if tech_posts.size == 0 %}
<p style="color: #666; text-align: center; padding: 40px;">
  暂无科技文章，敬请期待...
</p>
{% endif %}
