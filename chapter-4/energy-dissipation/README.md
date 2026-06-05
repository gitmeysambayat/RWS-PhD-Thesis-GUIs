# Cumulative Energy Dissipation for RWS Connections

![Cumulative energy dissipation screenshot](screenshots/20260605_v1_EnergyDissipation.png)

## Live GUI

[Open the cumulative energy dissipation GUI](https://gitmeysambayat.github.io/EnergyDissipation-RWS_Connections/)

## Purpose

This Chapter 4 companion GUI compares cumulative energy dissipation across selected RWS connection batches and cases. It supports selection by span-to-depth ratio, IPE profile, steel grade, and case ID, with normalised and actual cumulative energy plot tabs.

The selected-case matrix uses the same opening-geometry notation as the thesis workflow, including <i>d</i><sub>o</sub>/<i>h</i> and <i>S</i>/<i>h</i>.

## Engineering Context

Energy dissipation is one of the response measures used to compare cyclic RWS connection performance in the thesis workflow and related RWS studies [1,2]. This GUI is intended to reveal comparative trends between behaviourally similar cases, not to replace detailed cyclic qualification or project-specific seismic design checks.

## Repository Contents

- `index.html`: redirect entry point for GitHub Pages.
- `batches_with_plots.html`: standalone Plotly-based cumulative energy GUI with embedded data.
- `3DMBC_logo.png`, `city-st-georges-responsive-logo.svg`, `favicon_3dmbc.png`: branding and icon assets.
- `screenshots/20260605_v1_EnergyDissipation.png`: README screenshot.

## Local Use

Open `index.html` or `batches_with_plots.html` directly in a browser, or serve the repository root with any static HTTP server. The page uses Plotly from a public CDN.

## References

[1] M. Bayat, K. D. Tsavdaridis, and A. Alonso-Rodriguez, "A case study for optimising the geometry and moment capacity of code compliant welded RWS connections," *Frontiers in Built Environment*, 2025. DOI: [10.3389/fbuil.2025.1592665](https://doi.org/10.3389/fbuil.2025.1592665).

[2] M. Bayat, K. D. Tsavdaridis, and A. Alonso-Rodriguez, "Evaluation of Reduced Web Section (RWS) Connections Subjected to Cyclic Loading," *ce/papers*, 2025. DOI: [10.1002/cepa.70170](https://doi.org/10.1002/cepa.70170).
