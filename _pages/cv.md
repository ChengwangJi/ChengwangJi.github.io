---
layout: archive
title: "CV"
permalink: /cv/
author_profile: true
redirect_from:
  - /resume
---

{% include base_path %}

<div style="margin-bottom: 30px; display: flex; flex-wrap: wrap; gap: 15px;">
  
  <a href="/files/cv_en.pdf" target="_blank" style="
      display: inline-block;
      padding: 10px 20px;
      background-color: #24292e; /* GitHub Black */
      color: #ffffff;
      text-decoration: none;
      border-radius: 5px;
      font-weight: bold;
      border: 1px solid #24292e;">
    📄 English CV (PDF)
  </a>

  <a href="/files/cv_cn.pdf" target="_blank" style="
      display: inline-block;
      padding: 10px 20px;
      background-color: #ffffff; 
      color: #24292e;
      text-decoration: none;
      border-radius: 5px;
      font-weight: bold;
      border: 1px solid #24292e;">
    📄 中文简历 (PDF)
  </a>

</div>

Education
======
* Ph.D in University of Macau, 2022-2026 (expected)
* B.E. in Jilin University, 2018-2022

Work experience
======
* None

  
Skills
======
* Convex optimization
* Model-driven deep learning
* Wireless platform prototype

Publications
======
  <ul>{% for post in site.publications reversed %}
    {% include archive-single-cv.html %}
  {% endfor %}</ul>
  
Talks
======
  <ul>{% for post in site.talks reversed %}
    {% include archive-single-talk-cv.html  %}
  {% endfor %}</ul>
  
Teaching
======
  <ul>{% for post in site.teaching reversed %}
    {% include archive-single-cv.html %}
  {% endfor %}</ul>
  
Service and leadership
======
* Currently signed in to 43 different slack teams
