# FE and ML backbone comparison for RWS connections

Compare saved finite element (FE) backbones with browser-computed machine-learning (ML) predictions for circular Reduced Web Section (RWS) connections. Chapter 6 thesis companion using an exported XGBoost model.

**[Open the FE and ML tool](https://gitmeysambayat.github.io/RWS-PhD-Thesis-GUIs/chapter-6-ml-backbone-gui/)** · [Methods and limitations](../methods.html) · [All tools](../README.md)

![FE and ML interface showing geometry controls, curve overlays and comparison metrics](../screenshots/20261005_FEMLBackbone.png)

## Use

1. In **FE benchmark mode**, choose a case to overlay FE and ML curves. Press **Add curve** before changing cases to retain an FE curve; the first curve follows the controls. Export as SVG or PNG.
2. In **ML prediction mode**, vary the geometry. Exact FE comparisons and contours appear only at matching database points.
3. Inspect case-level errors or **Run full FE benchmark** to compare all 7,575 records. Each metric reports its available comparisons; missing FE responses are excluded.

Inputs cover five IPE profiles and three grades: span-to-depth control 6–14, opening diameter/depth 30–75%, and opening distance from column face/depth 60–240%. A zero opening selects the full section. These bounds do not guarantee prediction accuracy.

## Implementation and evidence

`index.html` evaluates the 400 trees in `xgb_model.json`. It scales 21 predicted moment ratios by section plastic moment to produce a backbone in kN·m over −0.06 to +0.06 rad. Predictions update with the inputs.

The benchmark uses the Explorer's FE dataset. Training code and train/test assignments are absent, so it does not establish independent predictive validation. Displayed strength or rotation thresholds do not establish connection qualification.

## Files and local use

- `index.html`: interface, FE dataset, model loading, inference, comparisons and SVG plotting.
- `xgb_model.json`: exported tree ensemble and feature names.
- `contours/`: case-labelled FE contour images, organised by grade and profile.

From the **repository root**, run `python3 -m http.server 8000 --bind 127.0.0.1`, then open [the local FE and ML tool](http://127.0.0.1:8000/chapter-6-ml-backbone-gui/). Keep `xgb_model.json` beside `index.html`; direct HTML-file access can block model loading.

By Meysam Bayat. [Research sources and reuse terms](../README.md#repository-and-research-sources).
