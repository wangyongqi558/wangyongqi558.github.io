---
layout: single
title: "Open-Vocabulary Video Visual Relationship Detection"
permalink: /
author_profile: false
---

## 🎥 Project Demo (Unified)
<div style="width: 100%; padding: 60px; background: #f4f4f4; border: 1px solid #ddd; border-radius: 12px; text-align: center; margin-bottom: 40px;">
  <h3 style="color: #888;">[ Full-length Video Demo Placeholder ]</h3>
  <p>Our unified framework for identifying complex interactions (subject-predicate-object) in dynamic videos.</p>
</div>

---

## 📚 Research Works

{% for post in site.portfolio reversed %}
  <div style="margin-bottom: 60px; display: flex; gap: 30px; align-items: start; border-bottom: 1px solid #eee; padding-bottom: 30px;">
    <div style="flex: 1;">
      <img src="{{ post.teaser }}" alt="Methodology" style="width: 100%; border: 1px solid #eee; border-radius: 8px;">
    </div>
    <div style="flex: 2;">
      <h3 style="margin-top: 0;"><a href="{{ post.url }}">{{ post.title }}</a></h3>
      <p><strong>Abstract:</strong> {{ post.abstract_short }}</p>
      <p><strong>Method:</strong> {{ post.method_short }}</p>
      <p><strong>Results:</strong> {{ post.result_short }}</p>
    </div>
  </div>
{% endfor %}
