# Reduced Web Section Explorer

Inspect saved finite element (FE) results for circular Reduced Web Section (RWS) connections. The interface links a case's geometry to its moment–rotation backbone, characteristic response measures and available contour images.

**[Open the Explorer](https://gitmeysambayat.github.io/RWS-PhD-Thesis-GUIs/database-guis/rws-explorer/)** · [Methods and limitations](../../methods.html) · [All tools](../../README.md)

![Explorer showing case controls, backbone response and contour images](../../screenshots/20261005_RWSExplorer.png)

## Use

1. Choose an IPE profile, steel grade and span-to-depth setting.
2. Select an opening case from the matrix or geometry controls. **C100** selects the full-section reference.
3. Press **Add curve** before selecting another case to retain the current one. The first curve follows the controls; added curves remain available for comparison. Use **Key points** to show characteristic moments, or export the plot as SVG or PNG.
4. Inspect the selected case's available von Mises and PEEQ contour images; PEEQ denotes equivalent plastic strain.

The embedded database contains 7,575 cases. Selection retrieves stored results; the page does not run FE analyses or predict an unanalysed geometry. Moment is shown in kN·m, with rotation in rad. Case `6.500.S235.C00` has missing backbone ordinates from ±0.03 to ±0.06 rad. Column-face response indicators include normalised quantities; the original raw-field scaling needs the provenance qualifications in the methods page.

The displayed strength-retention check is one response criterion. It does not establish connection prequalification or project-specific design compliance.

## Files and local use

- `index.html`: interface, embedded FE dataset and JavaScript/SVG plotting.
- `contours/`: case-labelled von Mises and PEEQ images, organised by grade and profile.
- `screenshots/`: interface screenshot; the remaining image assets are logos and icons.

From the **repository root**, run `python3 -m http.server 8000 --bind 127.0.0.1`, then open [the local Explorer](http://127.0.0.1:8000/database-guis/rws-explorer/). No build step is required.

Developed by Meysam Bayat as a companion to the RWS thesis. See the [repository research sources, credits and reuse terms](../../README.md#repository-and-research-sources).
