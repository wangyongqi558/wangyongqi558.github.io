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
    This demo showcases our end to end model across various open-vocabulary scenarios.
  </p>
</div>


<div style="text-align: center; margin-top: 20px; margin-bottom: 30px;">
    <button id="geminiBtn" style="padding: 12px 25px; background-color: #007bff; color: white; border: none; border-radius: 6px; font-size: 16px; cursor: pointer; transition: 0.3s; box-shadow: 0 4px 6px rgba(0,0,0,0.1);">
        🚀 Compare to Gemini's Detection Results
    </button>
</div>

<div id="geminiContainer" style="display: none; width: 100%; text-align: center; margin-bottom: 50px; padding: 20px; background-color: #fcfcfc; border: 1px dashed #007bff; border-radius: 12px;">
    <h3 style="color: #007bff; margin-bottom: 15px;">Gemini Detection Results</h3>
    <video id="geminiVideo" width="100%" style="max-width: 800px; border-radius: 8px;" controls>
        <source src="/images/gemini_comparison.mp4" type="video/mp4">
        Your browser does not support the video tag.
    </video>
</div>

<script>
document.addEventListener('DOMContentLoaded', function() {
    const btn = document.getElementById('geminiBtn');
    const container = document.getElementById('geminiContainer');
    const video = document.getElementById('geminiVideo');

    if (btn) {
        btn.addEventListener('click', function() {
            if (container.style.display === "none") {
                container.style.display = "block";
                this.innerHTML = "收起对比结果 (Close Comparison)";
                this.style.backgroundColor = "#6c757d";
                video.play();
            } else {
                container.style.display = "none";
                this.innerHTML = "🚀 Compare to Gemini's Detection Results";
                this.style.backgroundColor = "#007bff";
                video.pause();
            }
        });
    }
});
</script>
---

## 📢 News
<div style="margin-bottom: 2rem;">
  <div style="display: flex; justify-content: space-between; margin-bottom: 10px; font-size: 0.95rem;">
    <span style="font-weight: 600; color: #666; min-width: 90px;">Nov 2025</span>
    <span style="flex: 1; text-align: justify; border-bottom: 1px dashed #eee; padding-bottom: 8px;">
       We introduced <b>VaM-VidVRD</b>, the first multi-modal benchmark for <b>Open-vocabulary Video Visual Relationship Detection</b> featuring synchronized audio, text, and 3D data, in our paper <b>"Multi-modal Open-vocabulary Video Visual Relationship Detection"</b>.
    </span>
  </div>
  <div style="display: flex; justify-content: space-between; margin-bottom: 10px; font-size: 0.95rem;">
    <span style="font-weight: 600; color: #666; min-width: 90px;">Apr 2025</span>
    <span style="flex: 1; text-align: justify; border-bottom: 1px dashed #eee; padding-bottom: 8px;">
      Our paper <b>"METOR: A Unified Framework for Mutual Enhancement of Objects and Relationships in Open-vocabulary Video Visual Relationship Detection"</b> was accepted by <b>IJCAI 2025</b>.
    </span>
  </div>
  <div style="display: flex; justify-content: space-between; margin-bottom: 10px; font-size: 0.95rem;">
    <span style="font-weight: 600; color: #666; min-width: 90px;">Apr 2025</span>
    <span style="flex: 1; text-align: justify; border-bottom: 1px dashed #eee; padding-bottom: 8px;">
      Our paper <b>"End-to-end Open-vocabulary Video Visual Relationship Detection using Multi-modal Prompting"</b> was accepted by <b>IEEE TPAMI</b>.
    </span>
  </div>
  <div style="display: flex; justify-content: space-between; margin-bottom: 10px; font-size: 0.95rem;">
    <span style="font-weight: 600; color: #666; min-width: 90px;">Dec 2023</span>
    <span style="flex: 1; text-align: justify;">
      Our paper <b>"Multi-Modal Prompting for Open-Vocabulary Video Visual Relationship Detection"</b> was accepted by <b>AAAI 2024</b>.
    </span>
  </div>
</div>

---

## 📚 Publications

{% for post in site.portfolio reversed %}
<div style="margin-bottom: 15px; width: 100%; text-align: left;">
  <h3 style="margin-bottom: 3px; font-size: 1.1em; color: #222;">
    <a href="{{ post.url }}" style="text-decoration: none; color: inherit;">{{ post.title }}</a>
  </h3>

  <div style="margin-bottom: 10px;">
    {% if post.paper_url %}
      <a href="{{ post.paper_url }}" style="margin-right: 15px; padding: 5px 12px; background: #007bff; color: white; border-radius: 4px; text-decoration: none; font-size: 0.8em;">[Paper / PDF]</a>
    {% endif %}
    {% if post.code_url %}
      <a href="{{ post.code_url }}" style="padding: 5px 12px; background: #333; color: white; border-radius: 4px; text-decoration: none; font-size: 0.8em;">[Code / GitHub]</a>
    {% endif %}
  </div>
</div>
{% endfor %}
