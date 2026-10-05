# Cumulative energy comparison for RWS connections

Compare saved cumulative hysteretic energy curves for circular Reduced Web Section (RWS) connections. The tool supports comparisons within a batch and across different profiles, steel grades and span-to-depth settings.

**[Open the energy comparison](https://gitmeysambayat.github.io/RWS-PhD-Thesis-GUIs/database-guis/energy-dissipation/)** · [Methods and limitations](../../methods.html) · [All tools](../../README.md)

![Energy comparison showing case selection and cumulative energy curves](../../screenshots/20261005_EnergyDissipation.png)

## Use

1. Choose a batch using the span-to-depth, profile and grade selectors.
2. Select cases from the opening-geometry matrix or case selector. The page starts with C01 and C21 selected; press **Clear all** before setting up a single-case comparison. Selections are retained across batches; use the selected-case list to remove individual curves.
3. Choose **Plot selected**, then switch between **Normalised** and **Actual**.

The normalised view plots stored energy ratios relative to the batch's full-section reference, **C100**, with a reference line at 1. The actual view plots energy in **kJ** against cycle number; its checkbox adds a C100 curve for each selected batch.

The browser plots precomputed arrays. It does not integrate new hysteresis data or run FE analyses. Case `6.500.S235.C00` contains 26 cycle points rather than the 34 available for the other cases. Normalised and actual energy answer different comparison questions: inspect both and preserve batch identifiers when interpreting a result. An energy comparison alone does not establish seismic qualification.

## Files and local use

- `index.html`: entry point redirecting to the application.
- `batches_with_plots.html`: interface, embedded energy data and Plotly animation.
- `screenshots/`: interface screenshot; the remaining image assets are logos and icons.

From the **repository root**, run `python3 -m http.server 8000 --bind 127.0.0.1`, then open [the local energy comparison](http://127.0.0.1:8000/database-guis/energy-dissipation/). Internet access is needed for Plotly.js, loaded from a public CDN.

Developed by Meysam Bayat as a companion to the RWS thesis. See the [repository research sources, credits and reuse terms](../../README.md#repository-and-research-sources).
