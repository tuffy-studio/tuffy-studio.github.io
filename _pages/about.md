---
permalink: /
title: "Jielun Peng"
excerpt: "About me"
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---

{% if site.google_scholar_stats_use_cdn %}
{% assign gsDataBaseUrl = "https://cdn.jsdelivr.net/gh/" | append: site.repository | append: "@" %}
{% else %}
{% assign gsDataBaseUrl = "https://raw.githubusercontent.com/" | append: site.repository | append: "/" %}
{% endif %}
{% assign url = gsDataBaseUrl | append: "google-scholar-stats/gs_data_shieldsio.json" %}

<span class='anchor' id='about-me'></span>
# 👋 **Jielun Peng** **彭杰伦**[^1]

I received my B.S. degree in 2025 from School of Future Technology at Harbin Institute of Technology (HIT), China.
I am currently a first year master’s student at HIT, advised by Prof. [Xiaopeng Hong](https://homepage.hit.edu.cn/hongxiaopeng). My research primarily focuses on the development and implementation of AI safety, with particular attention to its applications in:

- Audio-Visual Deepfake Detection
- Explainable AIGC/Deepfake Detection with MLLMs
- Temporal/Spatial Forgery Localization


# 📖 Educations
- *2025.09 - 2028.01 (expected)*, A master’s student in Faculty of computing, Harbin Institute of Technology. Advisor: Prof. [Xiaopeng Hong](https://homepage.hit.edu.cn/hongxiaopeng)
- *2021.09 - 2025.06*, B.Sc. in School of Future Technology, [Harbin Institute of Technology]((https://www.hit.edu.cn/)).

# 📢 News & Achievements

<div class="news-buttons" style="margin-bottom: 25px; display: flex; flex-wrap: wrap; gap: 10px; align-items: center;">
  <span style="font-weight: bold;">Filter:</span>
  <button onclick="filterNews('all', event)" style="background: #333; color: white; border: none; padding: 4px 16px; border-radius: 20px; cursor: pointer; font-size: 0.9em;">Show All</button>
  <!-- <button onclick="filterNews('award', event)" style="background: #f1f1f1; border: 1px solid #ddd; padding: 4px 16px; border-radius: 20px; cursor: pointer; font-size: 0.9em; color: #333;">🏆 Awards</button> -->
  <button onclick="filterNews('paper', event)" style="background: #f1f1f1; border: 1px solid #ddd; padding: 4px 16px; border-radius: 20px; cursor: pointer; font-size: 0.9em; color: #333;">📝 Publications</button>
  <button onclick="filterNews('challenge', event)" style="background: #f1f1f1; border: 1px solid #ddd; padding: 4px 16px; border-radius: 20px; cursor: pointer; font-size: 0.9em; color: #333;">🚀 Challenges</button>
</div>

<div id="news-timeline" style="padding: 10px 5px; border-left: 2px solid #eee; margin-left: 10px;">

  <div class="news-item challenge" style="margin-bottom: 15px; display: flex; align-items: flex-start;">
    <span style="flex: 0 0 100px; color: #666; font-size: 0.95em; font-family: monospace;">2026.06</span>
    <span style="margin-left: 15px;"><b style="color: #0B3C8A;">[Top 3]</b> Top 3 performance in ACM MM 2026, Explainable Deepfake Detection Challenge.</span>
  </div>

  <div class="news-item challenge" style="margin-bottom: 15px; display: flex; align-items: flex-start;">
    <span style="flex: 0 0 100px; color: #666; font-size: 0.95em; font-family: monospace;">2026.06</span>
    <span style="margin-left: 15px;"><b style="color: #0B3C8A;">[Winner]</b> Winner (1/101) in IJCAI 2026, DDL 2.0 General AIGC Audio-Video Detection Challenge.</span>
  </div>

  <div class="news-item challenge" style="margin-bottom: 15px; display: flex; align-items: flex-start;">
    <span style="flex: 0 0 100px; color: #666; font-size: 0.95em; font-family: monospace;">2026.06</span>
    <span style="margin-left: 15px;"><b style="color: #0B3C8A;">[Winner]</b> Winner (1/113) in IJCAI 2026, DDL 2.0 Deepfake Detection, Localization, and Explainability Challenge.</span>
  </div>

  <div class="news-item challenge" style="margin-bottom: 15px; display: flex; align-items: flex-start;">
    <span style="flex: 0 0 100px; color: #666; font-size: 0.95em; font-family: monospace;">2026.03</span>
    <span style="margin-left: 15px;"><b style="color: #0B3C8A;">[Top 2%]</b> Top 2% (7/337) performance in CVPR 2026, NTIRE Robust Deepfake Detection Challenge.</span>
  </div>

  <div class="news-item paper" style="margin-bottom: 15px; display: flex; align-items: flex-start;">
    <span style="flex: 0 0 100px; color: #666; font-size: 0.95em; font-family: monospace;">2026.02</span>
    <span style="margin-left: 15px;"><b style="color: #27ae60;">[CVPR]</b> One paper is accepted by CVPR 2026 Findings. <a href="#" target="_blank">[Paper]</a></span>
  </div>

</div>

<script>
(function() {
  const LIMIT = 10;
  let expanded = false;

  function getBtn() { return document.getElementById('news-toggle-btn'); }

  function applyFilter(activeCategory) {
    const timeline = document.getElementById('news-timeline');
    const btn = getBtn();
    if (!timeline || !btn) return;
    const items = Array.from(timeline.querySelectorAll('.news-item'));
    let visible = 0;
    items.forEach(item => {
      const matchesCategory = (activeCategory === 'all' || item.classList.contains(activeCategory));
      if (matchesCategory) {
        item.style.display = (!expanded && visible >= LIMIT) ? 'none' : 'flex';
        visible++;
      } else {
        item.style.display = 'none';
      }
    });
    btn.style.display = visible > LIMIT ? 'inline-block' : 'none';
  }

  window.toggleNews = function() {
    expanded = !expanded;
    const btn = getBtn();
    if (btn) btn.textContent = expanded ? 'Show Less' : 'Show More';
    applyFilter(window._newsCategory || 'all');
  };

  window._newsCategory = 'all';
  window.filterNews = function(cat, e) {
    window._newsCategory = cat;
    const newsBtns = document.querySelectorAll('.news-buttons button');
    newsBtns.forEach(b => { b.style.background = '#f1f1f1'; b.style.color = '#333'; });
    if (e && e.currentTarget) {
      e.currentTarget.style.background = '#333';
      e.currentTarget.style.color = 'white';
    }
    expanded = false;
    const btn = getBtn();
    if (btn) btn.textContent = 'Show More';
    applyFilter(cat);
  };

  document.addEventListener('DOMContentLoaded', function() {
    applyFilter('all');
  });
})();
</script>

<div id="back-to-top" onclick="window.scrollTo({top:0,behavior:'smooth'})"
  style="display:none; position:fixed; bottom:30px; right:30px; z-index:999;
         background:#333; color:white; border:none; border-radius:50%;
         width:44px; height:44px; font-size:20px; line-height:44px;
         text-align:center; cursor:pointer; box-shadow:0 2px 8px rgba(0,0,0,0.3);">↑</div>
<script>
window.addEventListener('scroll', function() {
  const btn = document.getElementById('back-to-top');
  if (btn) btn.style.display = window.scrollY > 400 ? 'block' : 'none';
});
</script>

<div style="text-align: center; margin: 16px 0 32px 0;">
  <button id="news-toggle-btn" onclick="toggleNews()" style="background: #f1f1f1; border: 1px solid #ddd; padding: 5px 20px; border-radius: 20px; cursor: pointer; font-size: 0.9em; color: #333;">Show More</button>
</div>

# 📝 Publications 

[**CVPR 2026 (Findings)**] <u>Jielun Peng</u>, Yabin Wang, Yaqi Li, Long Kong, Xiaopeng Hong. *Leave No Stone Unturned: Uncovering Holistic Audio-Visual Intrinsic Coherence for Deepfake Detection.* [[paper]](https://openaccess.thecvf.com/content/CVPR2026F/html/Peng_Leave_No_Stone_Unturned_Uncovering_Holistic_Audio-Visual_Intrinsic_Coherence_for_CVPRF_2026_paper.html)

[**IEEE TMC (CCF-A)**]  Dongbo Li, Yuchen Sun, <u>Jielun Peng</u>, Siyao Cheng, Zhisheng Yin, Nan Cheng, Jie Liu, Zhijun Li, Chenren Xu. *Dual network computation offloading based on DRL for satellite-terrestrial integrated networks.* [[paper]](https://ieeexplore.ieee.org/abstract/document/10746595/)

# 🚀 Challenges

- Top 3 performance in ACM MM 2026, Explainable Deepfake Detection Challenge. (Team Leader)

- Winner (1/101) in IJCAI 2026, DDL 2.0 General AIGC Audio-Video Detection Challenge. (Team Leader)

- Winner (1/113) in IJCAI 2026, DDL 2.0 Deepfake Detection, Localization, and Explainability Challenge. (co-first author)

- Top 2% (7/337) performance in CVPR 2026, NTIRE Robust Deepfake Detection Challenge. (Team Leader)

# 🎖 Honors and Awards
- *2025.11* Outstanding Master Student Scholarship of Harbin Institute of Technology.
- *2025.05* Excellent Graduate of Harbin Institute of Technology.
- *2024.12* National Schloarship of P.R. China.
- *2023.11* Ministry of Education of P.R. China - Huawei Scholarship.


[^1]: My parents are big fans of Jay Chou (周杰伦), hence the name.