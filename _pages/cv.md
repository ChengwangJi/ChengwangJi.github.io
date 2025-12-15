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
* Spring 2024: Academic Pages Collaborator
  * Github University
  * Duties includes: Updates and improvements to template
  * Supervisor: The Users

* Fall 2015: Research Assistant
  * Github University
  * Duties included: Merging pull requests
  * Supervisor: Professor Hub

* Summer 2015: Research Assistant
  * Github University
  * Duties included: Tagging issues
  * Supervisor: Professor Git
  
Skills
======
* Skill 1
* Skill 2
  * Sub-skill 2.1
  * Sub-skill 2.2
  * Sub-skill 2.3
* Skill 3

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
