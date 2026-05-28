---
layout: default
title: Dashboard
---

<div class="dashboard-header">
  <h1>Sectors — ranked by conviction</h1>
  <span class="as-of">Updated May 2026</span>
</div>

<div class="legend">
  <span><span class="legend-dot" style="background:#22c55e"></span> High Conviction — strong thesis, favorable entry</span>
  <span><span class="legend-dot" style="background:#eab308"></span> Monitor — interesting but wait for clarity</span>
  <span><span class="legend-dot" style="background:#ef4444"></span> Avoid — headwinds outweigh opportunity</span>
</div>

<div class="sector-cards">
{% assign sorted_sectors = site.sectors | sort: "priority" %}
{% for sector in sorted_sectors %}
  {% include sector-card.html sector=sector %}
{% endfor %}
</div>
