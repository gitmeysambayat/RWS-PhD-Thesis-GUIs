# RWS research tools

Browser tools for exploring how circular web openings affect the response of steel beam-to-column connections under cyclic loading. Developed by **Meysam Bayat** for the PhD thesis *Predicting Reduced Web Section (RWS) Connection Performance with Circular Web Opening in Steel Moment Frames*.

The tools connect a finite element (FE) database to visual comparison, response screening and machine-learning (ML) backbone prediction. They make individual cases, comparison criteria and model outputs inspectable without running an FE solver.

**[Open the demonstrations](https://gitmeysambayat.github.io/RWS-PhD-Thesis-GUIs/)** · **[Methods and use](https://gitmeysambayat.github.io/RWS-PhD-Thesis-GUIs/methods.html)**

## Explore the work

| Tool | What you can do | Implementation and instructions |
| --- | --- | --- |
| [Reduced Web Section Explorer](https://gitmeysambayat.github.io/RWS-PhD-Thesis-GUIs/database-guis/rws-explorer/) | Select FE cases, overlay moment–rotation backbones, inspect response measures and contour images, and export plots. | [Embedded FE data and JavaScript/SVG interface](database-guis/rws-explorer/) |
| [Dynamic radar comparison](https://gitmeysambayat.github.io/RWS-PhD-Thesis-GUIs/database-guis/dynamic-radar-plot/) | Filter cases and compare six response indicators on fixed scales. | [Embedded FE summaries, Plotly and noUiSlider](database-guis/dynamic-radar-plot/) |
| [Cumulative energy comparison](https://gitmeysambayat.github.io/RWS-PhD-Thesis-GUIs/database-guis/energy-dissipation/) | Compare saved cumulative energy curves across cases and batches, in kJ or relative to a solid-beam baseline. | [Embedded response data and Plotly](database-guis/energy-dissipation/) |
| [FE and ML backbone comparison](https://gitmeysambayat.github.io/RWS-PhD-Thesis-GUIs/chapter-6-ml-backbone-gui/) | Run browser-side predictions, overlay exact FE cases where available, and inspect prediction differences. | [JavaScript inference and exported XGBoost tree model](chapter-6-ml-backbone-gui/) |

For a first comparison, open the Explorer, select a profile, grade and span-to-depth setting, and choose **C00**. Press **Add curve** to retain it, then select **C100**, the full-section reference. The first curve follows the controls while the added curve stays on the plot. Use the same case identifiers in the other tools to examine energy or ML agreement.

## Data and scope

The Explorer and ML interface share an embedded **7,575-case FE dataset**: five IPE profiles, three steel grades, five span-to-depth settings and 101 cases per combination. Its export metadata is dated 17 February 2026. Moments are reported in kN·m and rotations in rad. One case has incomplete backbone and energy records; its available response must not be treated as a complete loading sequence.

The three database tools display saved analysis results. The ML tool additionally evaluates the bundled tree ensemble in the browser for inputs within its controls. Exact FE comparisons are available only at database design points. A dataset-wide comparison is not an independent test-set validation.

These are research tools for examining this circular-RWS study. Radar area is a comparison score, and displayed strength thresholds are individual checks; neither establishes an optimum or connection qualification. See [methods and limitations](methods.html) for input conventions, exported-field provenance and interpretation boundaries.

## Run locally

With Python 3 installed, run this command **from the repository root**:

```sh
python3 -m http.server 8000 --bind 127.0.0.1
```

Open [http://127.0.0.1:8000/](http://127.0.0.1:8000/). No build step or Python package installation is required. Keep the folders together: the ML page loads its neighbouring `xgb_model.json`, and the Explorer and ML page load local contour images. The radar and energy pages need internet access to load their plotting libraries from public CDNs.

## Repository and research sources

`index.html` is the landing page; `methods.html` documents use and interpretation. Each tool directory contains its HTML/JavaScript application, embedded data, instructions and an interface screenshot. The Explorer and ML directories also contain `contours/`. This repository distributes the browser demonstrations and exported data/model assets; it does not contain the FE-generation or ML-training pipeline.

Related research:

- [A case study for optimising the geometry and moment capacity of code compliant welded RWS connections](https://doi.org/10.3389/fbuil.2025.1592665), *Frontiers in Built Environment*.
- [Evaluation of Reduced Web Section (RWS) Connections Subjected to Cyclic Loading](https://doi.org/10.1002/cepa.70170), *ce/papers*.
- [A Comparative Study of Data-Driven Analysis of Reduced Web Section (RWS) Connections](https://doi.org/10.21203/rs.3.rs-8506924/v1), Research Square **preprint**.

When using the research, cite the relevant publication and identify the tool and repository revision used. The publications provide research context; the repository contents define this software release.

## Credits and reuse

Research software: Meysam Bayat. See the linked publications for research co-authorship. The radar and energy interfaces use [Plotly.js](https://plotly.com/javascript/); the radar controls also use [noUiSlider](https://refreshless.com/nouislider/). Institutional and research-group logos retain their respective ownership.

No repository-wide licence is currently provided. Public availability does not grant a general reuse licence; clarify permission with the author before redistributing code, data or images. Third-party components retain their own licences.
