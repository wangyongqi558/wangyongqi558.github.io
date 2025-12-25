---
layout: single
title: "Open-Vocabulary Video Visual Relationship Detection"
permalink: /
author_profile: false # 彻底移除左侧边栏
---

## 🎥 Unified Project Demo
<div style="width: 100%; margin-bottom: 50px;">
  <div style="background: #f8f9fa; border: 1px solid #ddd; border-radius: 8px; padding: 60px; text-align: center;">
    <p style="color: #888; font-style: italic;">[ Overall Project Video Demo Placeholder ]</p>
  </div>
</div>

---

## 📚 Publications

{% for post in site.portfolio reversed %}
<div style="margin-bottom: 60px; width: 100%; text-align: left;">
  <h3 style="margin-bottom: 10px; font-size: 1.4em; color: #222;">
    <a href="{{ post.url }}" style="text-decoration: none; color: inherit;">{{ post.title }}</a>
  </h3>

  <div style="margin-bottom: 20px;">
    {% if post.paper_url %}
      <a href="{{ post.paper_url }}" style="margin-right: 15px; padding: 5px 12px; background: #007bff; color: white; border-radius: 4px; text-decoration: none; font-size: 0.9em;">[Paper / PDF]</a>
    {% endif %}
    {% if post.code_url %}
      <a href="{{ post.code_url }}" style="padding: 5px 12px; background: #333; color: white; border-radius: 4px; text-decoration: none; font-size: 0.9em;">[Code / GitHub]</a>
    {% endif %}
  </div>

  <div style="width: 100%; margin-bottom: 25px;">
    <img src="{{ post.teaser }}" style="width: 100%; max-width: 900px; display: block; margin: 0 auto; border: 1px solid #eee; border-radius: 4px;">
  </div>

  <div style="width: 100%; text-align: justify; line-height: 1.6; color: #444;">
    <p>{{ post.abstract_short }}</p>
  </div>
</div>
{% endfor %}
