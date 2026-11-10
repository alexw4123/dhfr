# DHFR research handoff

Start with [README.md](README.md) for the study, attribution, and evidence boundaries. The live page is [DHFR](https://alexw4123.github.io/dhfr/).

## Where to work

- `index.html` holds the visible study title and page sections. `research-v6.css` owns the current layout. Keep the **Compare 3D models** action accessible near the title, including at phone widths.
- `app.js` owns the overview, guided explanation, and model comparison interactions. One NGL stage moves between these views. `molecule-engine.js` owns model rendering and source verification.
- `content.js`, `application-data.js`, and `research-sections.js` own the research text and evidence views. Use the current scripts in `index.html` and [.github/workflows/pages.yml](.github/workflows/pages.yml) to distinguish the release from older viewer iterations.

## Preview and validate

- Reproduce the workflow's static staging step in a scratch directory and serve it with `python -m http.server 8000`. The workflow extracts `assets.zip` to supply the PDBs and viewer dependencies. There is no package install step.
- Verify both model choices against [ASSET-MANIFEST.json](ASSET-MANIFEST.json). Each complex has 3,153 atoms and 3,195 explicit bonds. Preserve the coordinate files, order, connectivity, and selection mappings. If a release changes listed presentation files, refresh their manifest hashes and byte counts.
- When editing navigation, check the opening at phone widths and use **Compare 3D models** to verify the active viewer reaches `#models`. Preserve section links and the ability to switch model representations.
- Label the structures as models and retain the evidence limits. The displayed records contain no measured inhibition or cell-response results. Keep private notebooks out of the public site.
- A push to `main` runs the Pages deployment. Use a separate branch for review when the task does not authorize a site release.
