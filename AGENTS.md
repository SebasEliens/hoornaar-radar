# Agent instructions

## Pre-commit requirement — always re-run the notebook

**Before every commit**, execute the full notebook so that `docs/hornet_timelapse.html`
stays in sync with the current code and parameters:

```
uv run jupyter nbconvert --to notebook --execute --inplace notebooks/hornet_nest_simulation_study.ipynb
```

Then stage both files:

```
git add notebooks/hornet_nest_simulation_study.ipynb docs/hornet_timelapse.html
```

`docs/hornet_timelapse.html` is the live GitHub Pages artifact at
https://sebaseliens.github.io/hoornaar-radar/hornet_timelapse.html — it must
always reflect the current parameters and simulation output.
