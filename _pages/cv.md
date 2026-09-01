---
layout: archive
title: "CV"
permalink: /cv/
author_profile: true
redirect_from:
  - /resume
---

{% include base_path %}

<div style="
    margin-bottom: 30px;
    display: flex;
    flex-wrap: wrap;
    gap: 25px;
    align-items: center;
">

  <!-- English CV -->
  <div style="display: flex; align-items: center; gap: 8px;">

    <a id="cv-en-btn"
       href="/files/cv_en.pdf"
       target="_blank"
       rel="noopener noreferrer"
       style="
          display: inline-block;
          padding: 10px 20px;
          background-color: #24292e;
          color: #ffffff;
          text-decoration: none;
          border-radius: 5px;
          font-weight: bold;
          border: 1px solid #24292e;">
      📄 English CV (PDF)
    </a>

    <span id="cv-en-count"
          style="
            font-size: 0.85em;
            color: #777;
            white-space: nowrap;">
      0 downloads
    </span>

  </div>


  <!-- Chinese CV -->
  <div style="display: flex; align-items: center; gap: 8px;">

    <a id="cv-cn-btn"
       href="/files/cv_cn.pdf"
       target="_blank"
       rel="noopener noreferrer"
       style="
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

    <span id="cv-cn-count"
          style="
            font-size: 0.85em;
            color: #777;
            white-space: nowrap;">
      0 次下载
    </span>

  </div>

</div>


<script>
document.addEventListener("DOMContentLoaded", function () {

    const API_BASE = "https://countapi.mileshilliard.com/api/v1";

    // 根据你的域名自动生成独立的计数器名称
    const siteKey = window.location.hostname
        .replace(/[^a-zA-Z0-9_-]/g, "-");

    const counters = {
        en: siteKey + "-cv-en-downloads",
        cn: siteKey + "-cv-cn-downloads"
    };


    // 读取当前下载次数
    async function loadCount(key, elementId, language) {
        const element = document.getElementById(elementId);

        try {
            const response = await fetch(
                `${API_BASE}/get/${key}`,
                { cache: "no-store" }
            );

            if (!response.ok) {
                throw new Error("Counter does not exist yet.");
            }

            const data = await response.json();

            if (language === "en") {
                element.textContent =
                    `${data.value} ${data.value === 1 ? "download" : "downloads"}`;
            } else {
                element.textContent =
                    `${data.value} 次下载`;
            }

        } catch (error) {
            if (language === "en") {
                element.textContent = "0 downloads";
            } else {
                element.textContent = "0 次下载";
            }
        }
    }


    // 点击按钮后次数 +1
    async function increaseCount(key, elementId, language) {
        const element = document.getElementById(elementId);

        try {
            const response = await fetch(
                `${API_BASE}/hit/${key}`,
                {
                    cache: "no-store",
                    keepalive: true
                }
            );

            if (!response.ok) return;

            const data = await response.json();

            if (language === "en") {
                element.textContent =
                    `${data.value} ${data.value === 1 ? "download" : "downloads"}`;
            } else {
                element.textContent =
                    `${data.value} 次下载`;
            }

        } catch (error) {
            console.log("Download counter error:", error);
        }
    }


    // 页面加载时显示当前次数
    loadCount(counters.en, "cv-en-count", "en");
    loadCount(counters.cn, "cv-cn-count", "cn");


    // 英文简历
    document
        .getElementById("cv-en-btn")
        .addEventListener("click", function () {
            increaseCount(
                counters.en,
                "cv-en-count",
                "en"
            );
        });


    // 中文简历
    document
        .getElementById("cv-cn-btn")
        .addEventListener("click", function () {
            increaseCount(
                counters.cn,
                "cv-cn-count",
                "cn"
            );
        });

});
</script>


Education
======
* Ph.D. in Electrical and Computer Engineering, University of Macau, 2022-2026
* B.E. in Jilin University, 2018-2022

Work experience
======
* Research Assistant, University of Macau, 2026-2027


Skills
======
* Convex optimization
* Model-driven deep learning
* Wireless platform prototype


Publications
======
<ul>
{% for post in site.publications reversed %}
  {% include archive-single-cv.html %}
{% endfor %}
</ul>


Talks
======
<ul>
{% for post in site.talks reversed %}
  {% include archive-single-talk-cv.html %}
{% endfor %}
</ul>
