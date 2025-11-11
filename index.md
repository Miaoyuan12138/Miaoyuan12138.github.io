---
layout: default
title: HW5 — Altair to Vega-Lite (Bigfoot)
---

# HW5: Two Visualizations of BFRO Reports

<div id="c1"></div>

**Plot 1 – Multiline over time (interactive).**  
This chart shows yearly Bigfoot report counts for the top eight U.S. states. 

**Encodings:** x=Year (temporal), y=reports (quantitative, symlog), color=state (nominal). I use a dropdown selection to condition 

**size** (5 vs 1) and opacity to highlight one state at a time. 

**Transformations:** parsed dates, created `Year`, grouped by `Year,state`, chose top states by total counts. 

**Colormap:** `sinebow` gives distinct hues without implying order. 

**Interactivity:** I use a `selection_point` bound to a dropdown named “State:”. The selected state gets a thicker line (size=5, opacity=1) and others are thinner (size=1, opacity=0.35). The default selection is “California”, and this makes comparisons clear when many lines overlap.

---

<div id="c2"></div>

**Plot 2 – Top-15 states (static bar chart).**  
This ranks total reports by state. 

**Encodings:** x=reports, y=state (sorted -x), fixed color. 

**Transformations:** aggregated counts by state, took top 15. The static ranking complements the trend view by making magnitudes comparable at a glance.

---

<div id="c1"></div>
<div id="c2"></div>

### Links
<p>
  <a href="https://raw.githubusercontent.com/UIUC-iSchool-DataViz/is445_data/main/bfro_reports_fall2022.csv"
     target="_blank" rel="noopener noreferrer"
     style="display:inline-block;padding:8px 14px;border-radius:8px;border:1px solid #888;text-decoration:none;">
    The Data
  </a>
  &nbsp;
  <a href="https://github.com/Miaoyuan12138/Miaoyuan12138.github.io/blob/main/Workbook.ipynb"
     target="_blank" rel="noopener noreferrer"
     style="display:inline-block;padding:8px 14px;border-radius:8px;border:1px solid #888;text-decoration:none;">
    The Analysis
  </a>
</p>

<script src="https://cdn.jsdelivr.net/npm/vega@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-lite@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-embed@6"></script>
<script>
  vegaEmbed('#c1', '{{ "/assets/vegaplots/bigfoot_lines.json" | relative_url }}', {actions:false});
  vegaEmbed('#c2', '{{ "/assets/vegaplots/bigfoot_bars.json" | relative_url }}', {actions:false});
</script>