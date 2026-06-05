# Machine-Learning-Based Backbone Curve Prediction for RWS Connections

![FE and ML backbone prediction screenshot](screenshots/20260605_v1_FEMLBackbone.png)

## Live GUI

[Open the FE and ML backbone prediction GUI](https://gitmeysambayat.github.io/RWS-PhD-Thesis-GUIs/chapter-6-ml-backbone-gui/)

## Purpose

This GUI supports FE benchmark review and ML-based backbone curve prediction for circular RWS connections. The app combines the embedded FE-derived database, a local `xgb_model.json` model file, and contour image assets for selected FE cases.

In the submitted thesis, this GUI belongs to Chapter 6, "Explainable Machine-Learning-Based Prediction of Backbone Curves and GUI", where the model benchmarking, explainability, and browser-based deployment are developed.

## Main Features

- FE benchmark mode for exact database cases.
- ML prediction mode for backbone curve prediction within the model development domain.
- FE and ML curve overlays for selected cases.
- Benchmark summary table with <i>M</i><sub>0.04</sub>, <i>M</i><sub>0.06</sub>, <i>&theta;</i><sub>u</sub>, and error metrics.
- von Mises and PEEQ contour display where the selected FE case has matching image assets.

## Engineering Context

Machine-learning surrogate models can support rapid parametric exploration when the training domain, validation error, and applicability limits are clearly stated. This GUI is a research deployment and screening tool. It is not a substitute for validated FE analysis, experimental evidence, or project-specific seismic qualification.

## Repository Contents

- `index.html`: standalone FE and ML GUI.
- `xgb_model.json`: local model file used by the browser app.
- `contours/`: von Mises and PEEQ contour image assets.
- `3DMBC_logo.png`, `city-st-georges-responsive-logo.svg`, `favicon_3dmbc.png`: branding and icon assets.
- `screenshots/20260605_v1_FEMLBackbone.png`: README screenshot.

## Local Use

Serve the repository root with a static HTTP server and open `index.html`. A static server is recommended because the GUI loads `xgb_model.json` as a local browser asset.

## References

[1] M. Bayat, K. D. Tsavdaridis, and A. Alonso-Rodriguez, "A case study for optimising the geometry and moment capacity of code compliant welded RWS connections," *Frontiers in Built Environment*, 2025. DOI: [10.3389/fbuil.2025.1592665](https://doi.org/10.3389/fbuil.2025.1592665).

[2] M. Bayat, K. D. Tsavdaridis, and A. Alonso-Rodriguez, "Evaluation of Reduced Web Section (RWS) Connections Subjected to Cyclic Loading," *ce/papers*, 2025. DOI: [10.1002/cepa.70170](https://doi.org/10.1002/cepa.70170).

[3] M. Bayat and K. D. Tsavdaridis, "A Comparative Study of Data-Driven Analysis of Reduced Web Section (RWS) Connections," Research Square preprint, 2026. DOI: [10.21203/rs.3.rs-8506924/v1](https://doi.org/10.21203/rs.3.rs-8506924/v1).
