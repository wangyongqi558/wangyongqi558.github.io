---
layout: archive
title: "Open-Vocabulary Video Visual Relationship Detection"
permalink: /
author_profile: false
---

{% include base_path %}

# 🎥 Project Video Demo (Unified)
<div style="width: 100%; padding: 50px; background: #f8f9fa; border: 1px solid #ddd; border-radius: 8px; text-align: center; margin-bottom: 40px;">
  <h2 style="color: #666;">[ Video Demo Placeholder ]</h2>
  <p>Our comprehensive framework for detecting subject-predicate-object triplets in dynamic video scenes.</p>
</div>

---

# 📚 Research Works
{% for post in site.portfolio reversed %}
  <div style="margin-bottom: 50px; border-bottom: 1px solid #eee; padding-bottom: 20px;">
    <h2><a href="{{ post.url }}">{{ post.title }}</a></h2>
    
    <div style="display: flex; gap: 20px; align-items: flex-start;">
      <div style="flex: 1;">
        <img src="{{ post.teaser_image }}" style="width: 100%; border-radius: 5px; border: 1px solid #eee;">
      </div>
      <div style="flex: 2;">
        <strong>Abstract:</strong> {{ post.abstract_short }} <br><br>
        <strong>Method:</strong> {{ post.method_short }} <br><br>
        <strong>Results:</strong> {{ post.result_short }}
      </div>
    </div>
  </div>
{% endfor %}
