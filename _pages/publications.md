---
layout: page
permalink: /publications/
title: 论文
description: 已接收论文、发表论文、预印本与技术报告；内容由 BibTeX 统一维护。
nav: true
nav_order: 5
en_url: /en/publications/
---

<!-- _pages/publications.md -->

{% assign visible_publications = site.bibliography | where: "website", "true" %}
{% if visible_publications.size == 0 %}
目前还没有公开的论文条目。后续成果会按时间倒序展示，并提供论文、代码、数据和项目页面链接。
{% endif %}

<!-- Bibsearch Feature -->

{% include bib_search.liquid %}

<div class="publications">

{% bibliography %}

</div>
