---
layout: archive
title: "CV"
permalink: /cv/
author_profile: true
redirect_from:
  - /resume
---

{% include base_path %}

<style>
  .cv-downloads {
    margin-bottom: 30px;
    display: grid;
    gap: 12px;
  }

  .cv-download-row {
    display: flex;
    align-items: center;
    flex-wrap: wrap;
    gap: 12px;
  }

  .cv-download-link {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    padding: 10px 20px;
    text-decoration: none;
    border-radius: 5px;
    font-weight: 700;
    border: 1px solid #24292e;
    line-height: 1.2;
  }

  .cv-download-link--dark {
    background-color: #24292e;
    color: #ffffff;
  }

  .cv-download-link--light {
    background-color: #ffffff;
    color: #24292e;
  }

  .cv-download-count {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    color: #6b7280;
    font-size: 0.92rem;
    white-space: nowrap;
    min-width: 110px;
  }

  .cv-download-count i {
    font-size: 0.85rem;
  }
</style>

<div class="cv-downloads">
  <div class="cv-download-row">
    <a
      id="cv-en-link"
      class="cv-download-link cv-download-link--dark"
      href="{{ base_path }}/files/CV_Chengwangji.pdf"
      target="_blank"
      rel="noopener noreferrer"
      aria-label="Download English CV as PDF"
    >
      <i class="fa-solid fa-file-pdf" aria-hidden="true"></i>
      <span>English CV (PDF)</span>
    </a>
    <span class="cv-download-count" aria-live="polite">
      <i class="fa-solid fa-download" aria-hidden="true"></i>
      <span id="cv-en-count">--</span>
      <span>downloads</span>
    </span>
  </div>

  <div class="cv-download-row">
    <a
      id="cv-cn-link"
      class="cv-download-link cv-download-link--light"
      href="{{ base_path }}/files/简历_季成旺.pdf"
      target="_blank"
      rel="noopener noreferrer"
      aria-label="Download Chinese CV as PDF"
    >
      <i class="fa-solid fa-file-pdf" aria-hidden="true"></i>
      <span>Chinese CV (PDF)</span>
    </a>
    <span class="cv-download-count" aria-live="polite">
      <i class="fa-solid fa-download" aria-hidden="true"></i>
      <span id="cv-cn-count">--</span>
      <span>downloads</span>
    </span>
  </div>
</div>

<script>
  (function () {
    var apiBase = "https://countapi.mileshilliard.com/api/v1";
    var items = [
      {
        linkId: "cv-en-link",
        countId: "cv-en-count",
        key: "chengwangji-cv-en-downloads",
        format: function (value) {
          return value + " " + (value === 1 ? "download" : "downloads");
        }
      },
      {
        linkId: "cv-cn-link",
        countId: "cv-cn-count",
        key: "chengwangji-cv-cn-downloads",
        format: function (value) {
          return value + " 次下载";
        }
      }
    ];

    function setCount(countId, value) {
      var el = document.getElementById(countId);
      if (el) {
        el.textContent = value;
      }
    }

    function loadCount(item) {
      return fetch(apiBase + "/get/" + item.key, { cache: "no-store" })
        .then(function (response) {
          if (response.status === 404) {
            return fetch(apiBase + "/set/" + item.key + "?value=0", {
              cache: "no-store"
            }).then(function () {
              return { value: 0 };
            });
          }

          if (!response.ok) {
            throw new Error("Failed to load count");
          }

          return response.json();
        })
        .then(function (data) {
          setCount(item.countId, item.format(data.value));
        })
        .catch(function () {
          setCount(item.countId, "--");
        });
    }

    function trackClick(item) {
      var link = document.getElementById(item.linkId);
      if (!link) {
        return;
      }

      link.addEventListener("click", function () {
        fetch(apiBase + "/hit/" + item.key, {
          cache: "no-store",
          keepalive: true
        })
          .then(function (response) {
            return response.ok ? response.json() : null;
          })
          .then(function (data) {
            if (data && typeof data.value !== "undefined") {
              setCount(item.countId, item.format(data.value));
            }
          })
          .catch(function () {});
      });
    }

    items.forEach(function (item) {
      loadCount(item);
      trackClick(item);
    });
  })();
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
