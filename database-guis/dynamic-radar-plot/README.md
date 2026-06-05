# RWS Connections Dynamic Radar Plot

![RWS dynamic radar plot screenshot](screenshots/20260605_v1_RadarPlot.png)

## Live GUI

[Open the RWS dynamic radar plot](https://gitmeysambayat.github.io/RWS-PhD-Thesis-GUIs/database-guis/dynamic-radar-plot/)

## Purpose

This complementary thesis GUI compares RWS connection cases using a radar plot with fixed global metric ranges. It supports design-oriented interrogation of the FE database and database-driven synthesis workflow. The embedded app data defines the plotted spokes as PEEQ at the column face, von Mises stress at the column face, cumulative energy, degradation, <i>&theta;</i>(0.6), and <i>M</i><sub>c</sub>.

The filter panel supports profile, steel grade, top-N selection, primary normalised filters, and secondary filters. The CSV export button downloads the currently filtered dataset.

## Engineering Context

RWS connections are used to move inelastic demand away from the beam-column interface by weakening the beam web rather than the flanges [1]. The radar plot is intended for comparative screening only. It should be read together with the underlying backbone response, energy dissipation, and column-face demand evidence.

## Repository Contents

- `index.html`: redirect entry point for GitHub Pages.
- `RWS_radar_dynamic.html`: standalone Plotly-based radar GUI with embedded data.
- `3DMBC_logo.png`, `city-st-georges-responsive-logo.svg`, `favicon_3dmbc.png`: branding and icon assets.
- `screenshots/20260605_v1_RadarPlot.png`: README screenshot.

## Local Use

Open `index.html` or `RWS_radar_dynamic.html` directly in a browser, or serve the repository root with any static HTTP server. The page uses Plotly and noUiSlider from public CDNs.

## References

[1] M. Bayat, K. D. Tsavdaridis, and A. Alonso-Rodriguez, "A case study for optimising the geometry and moment capacity of code compliant welded RWS connections," *Frontiers in Built Environment*, 2025. DOI: [10.3389/fbuil.2025.1592665](https://doi.org/10.3389/fbuil.2025.1592665).

[2] M. Bayat, K. D. Tsavdaridis, and A. Alonso-Rodriguez, "Evaluation of Reduced Web Section (RWS) Connections Subjected to Cyclic Loading," *ce/papers*, 2025. DOI: [10.1002/cepa.70170](https://doi.org/10.1002/cepa.70170).
