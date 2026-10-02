# Agent instructions

## Before committing

Always re-run the full notebook before committing so the generated HTML stays in sync with the code:

```
uv run jupyter nbconvert --to notebook --execute --inplace notebooks/hornet_nest_simulation_study.ipynb
```

Then stage both the notebook and the output:

```
git add notebooks/hornet_nest_simulation_study.ipynb docs/hornet_timelapse.html
```

The file `docs/hornet_timelapse.html` is the live GitHub Pages artefact at
https://sebaseliens.github.io/hoornaar-radar/hornet_timelapse.html — it must
always reflect the current parameters and simulation output.
