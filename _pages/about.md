---
layout: single
title: "Open-Vocabulary Video Visual Relationship Detection"
permalink: /
author_profile: false # 彻底移除左侧边栏
---

## 🎥 Demo
<div style="width: 100%; text-align: center; margin-bottom: 50px;">
  <video width="100%" style="max-width: 900px; border-radius: 12px; border: 1px solid #ddd; box-shadow: 0 4px 20px rgba(0,0,0,0.1);" controls muted autoplay loop>
    <source src="/images/demo.mp4" type="video/mp4">
    Your browser does not support the video tag.
  </video>
  <p style="color: #666; margin-top: 10px; font-style: italic;">
    This demo showcases our unified framework across various open-vocabulary scenarios.
  </p>
</div>

---

## 📢 News
<div style="margin-top: 1rem;">
  <div style="display: flex; margin-bottom: 8px;">
    <span style="min-width: 85px; color: #666; font-size: 0.9rem; font-weight: 500;">Apr. 2025</span>
    <span style="flex: 1; font-size: 0.95rem;">Our paper <b>"METOR: A Unified Framework for Mutual Enhancement of Objects and
Relationships in Open-vocabulary Video Visual Relationship Detection"</b> was accepted by <b>IJCAI 2025</b>.</span>
  </div>
  <div style="display: flex; margin-bottom: 8px;">
    <span style="min-width: 85px; color: #666; font-size: 0.9rem; font-weight: 500;">Apr. 2025</span>
    <span style="flex: 1; font-size: 0.95rem;">Our paper <b>"End-to-end Open-vocabulary Video Visual
Relationship Detection using Multi-modal
Prompting"</b> was accepted by <b>IEEE TPAMI</b>.</span>
  </div>
  <div style="display: flex; margin-bottom: 8px;">
    <span style="min-width: 85px; color: #666; font-size: 0.9rem; font-weight: 500;">Dec. 2023</span>
    <span style="flex: 1; font-size: 0.95rem;">Our paper <b>"Multi-Modal Prompting for Open-Vocabulary Video Visual Relationship Detection"</b> was accepted by <b>AAAI 2024</b>.</span>
  </div>
</div>

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
