# RWS dynamic radar comparison

Support optimisation studies by filtering saved finite element (FE) results, comparing six response indicators and shortlisting existing circular Reduced Web Section (RWS) configurations. Fixed global ranges keep the radar scales consistent when the selection changes.

**[Open the radar comparison](https://gitmeysambayat.github.io/RWS-PhD-Thesis-GUIs/database-guis/dynamic-radar-plot/)** · [Methods and limitations](../../methods.html) · [All tools](../../README.md)

![Radar comparison with response filters and selected case outlines](../../screenshots/20261005_RadarPlot.png)

## Use and interpretation

Choose profile, grade and span-to-depth filters, then adjust the numerical ranges. **Top N** limits the number of displayed cases; the counter also reports all cases that pass the filters.

The six spokes represent the stored column-face PEEQ indicator, normalised column-face von Mises response, normalised dissipated energy, strength degradation, moment at 0.06 rad relative to the full-section reference, and peak moment relative to that reference. PEEQ denotes equivalent plastic strain; interpret the exported indicator using the provenance note in the methods page.

The display reverses the lower-is-preferred metrics so that the chosen favourable direction is outward. It ranks filtered cases by polygon area. This ranking depends on the metric definitions, ranges and spoke order; it is a comparison aid, not a structural optimisation or qualification procedure.

**Download Filtered CSV** exports all cases passing the filters, including cases beyond the displayed Top N. The current interface requests a download password. No FE analyses or ML predictions run in this tool.

## Files and local use

- `index.html`: entry point redirecting to the application.
- `RWS_radar_dynamic.html`: embedded dataset, filtering, radar scoring and CSV export.
- `screenshots/`: interface screenshot; the remaining image assets are logos and icons.

From the **repository root**, run `python3 -m http.server 8000 --bind 127.0.0.1`, then open [the local radar comparison](http://127.0.0.1:8000/database-guis/dynamic-radar-plot/). Internet access is needed for Plotly.js and noUiSlider, loaded from public CDNs.

Developed by Meysam Bayat as a companion to the RWS thesis. See the [repository research sources, credits and reuse terms](../../README.md#repository-and-research-sources).
