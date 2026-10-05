# RWS research tools

Four browser tools by **Meysam Bayat** for comparing finite element (FE) results and machine-learning (ML) backbone predictions for steel connections with circular web openings. Companion to the PhD thesis *Predicting Reduced Web Section (RWS) Connection Performance with Circular Web Opening in Steel Moment Frames*.

**[Open the demonstrations](https://gitmeysambayat.github.io/RWS-PhD-Thesis-GUIs/)** · **[Methods and use](https://gitmeysambayat.github.io/RWS-PhD-Thesis-GUIs/methods.html)**

## Tools

| Tool | What you can do | Implementation and instructions |
| --- | --- | --- |
| [Reduced Web Section Beams Explorer](https://gitmeysambayat.github.io/RWS-PhD-Thesis-GUIs/database-guis/rws-explorer/) | Overlay FE backbones, inspect contours and export plots. | [FE data and JavaScript/SVG](database-guis/rws-explorer/) |
| [Dynamic radar comparison](https://gitmeysambayat.github.io/RWS-PhD-Thesis-GUIs/database-guis/dynamic-radar-plot/) | Filter and rank cases by six indicators for optimisation studies. | [FE summaries, Plotly and noUiSlider](database-guis/dynamic-radar-plot/) |
| [Cumulative energy comparison](https://gitmeysambayat.github.io/RWS-PhD-Thesis-GUIs/database-guis/energy-dissipation/) | Compare cumulative energy in kJ or relative to a solid-beam reference. | [Energy data and Plotly](database-guis/energy-dissipation/) |
| [FE and ML backbone comparison](https://gitmeysambayat.github.io/RWS-PhD-Thesis-GUIs/chapter-6-ml-backbone-gui/) | Run predictions and compare them with matching FE cases. | [JavaScript inference and XGBoost export](chapter-6-ml-backbone-gui/) |

To compare an opening with the full section, select **C00** in the Explorer, press **Add curve**, then select **C100**. The first curve follows the controls; added curves stay on the plot. Use matching case IDs across tools.

## Data and scope

The Explorer and ML interface share **7,575 stored FE cases**: five IPE profiles × three grades × five span-to-depth settings × 101 cases. Export date: 17 February 2026. Moments: kN·m; rotations: rad. Case `6.500.S235.C00` has incomplete backbone and energy records and is excluded from radar ranking and export.

The database tools display saved results. The ML tool computes predictions within its input bounds; exact FE comparisons require a matching database point. Its dataset-wide benchmark is not an independent test-set validation.

Radar area and displayed thresholds are screening measures, not proof of an optimum or connection qualification. See [methods and limitations](methods.html) for input conventions and field scaling.

## Repository and research sources

Each tool directory contains its application and data; Explorer and ML also include contour images. The repository includes the deployed model, but not the FE-generation or ML-training pipeline.

Published papers:

- [FE parametric study of circular Reduced Web Section (RWS) connections subjected to cyclic loading](https://doi.org/10.1002/cepa.70779), *ce/papers* 9(2–3), 1835–1840 (2026).
- [Reducing column-face demands in circular Reduced Web Section (RWS) connections](https://doi.org/10.1002/cepa.70780), *ce/papers* 9(2–3), 1885–1890 (2026).
- [A case study for optimising the geometry and moment capacity of code compliant welded RWS connections](https://doi.org/10.3389/fbuil.2025.1592665), *Frontiers in Built Environment*.
- [Evaluation of Reduced Web Section (RWS) Connections Subjected to Cyclic Loading](https://doi.org/10.1002/cepa.70170), *ce/papers*.
- [Cyclic performance of reduced web section (RWS) beam connections](https://openaccess.city.ac.uk/id/eprint/35039/), conference paper, *The 2nd International Symposium on Advanced Materials and Design for Structural Safety and Sustainability*, Lyon, 6–7 February 2025.

Preprint:

- [A Comparative Study of Data-Driven Analysis of Reduced Web Section (RWS) Connections](https://doi.org/10.21203/rs.3.rs-8506924/v1), Research Square **preprint**.

Cite the relevant publication, tool and repository revision used.

## Credits and reuse

See the publications for research co-authorship. Radar and energy use [Plotly.js](https://plotly.com/javascript/); radar also uses [noUiSlider](https://refreshless.com/nouislider/).

No repository-wide licence is provided. Obtain the author's permission before redistributing code, data or images. Third-party components and logos retain their respective licences or ownership.
