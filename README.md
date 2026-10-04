# Hoornaar Radar

A simulation study for locating Asian hornet (*Vespa velutina*) nests from detections at beehives.

## What it does

The notebook simulates a network of beehives fitted with hornet detectors that record each hornet's departure **heading** and **ground speed**. It then:

1. Infers probable nest locations using a Poisson detection-rate model, von Mises bearing likelihood, and a homing/foraging speed classifier
2. Sends virtual search teams to the most probable locations and removes found nests
3. Feeds each removal back into the model (iterative refinement)
4. Compares detector coverage scenarios
5. Produces an **interactive timelapse map** where you can toggle detectors on hives and mark destroyed nests

The live map is published at **[sebaseliens.github.io/hoornaar-radar/hornet_timelapse.html](https://sebaseliens.github.io/hoornaar-radar/hornet_timelapse.html)**.

## Real vs. simulated data

| Component | Source |
|---|---|
| Study area and basemap | Real: OpenStreetMap tiles |
| Public hornet records | Real (when online): GBIF / Observation.org API |
| Beehive locations | `data/hives.csv` if present, otherwise simulated |
| Historic removed nests | `data/removed_nests.csv` if present, otherwise none |
| Nests, hornet flights, detections, searches | Simulated from literature parameters |

## Setup

```bash
uv sync
uv run jupyter nbconvert --to notebook --execute --inplace notebooks/hornet_nest_simulation_study.ipynb
```

The executed notebook writes the timelapse map to `docs/hornet_timelapse.html`.

## Optional real inputs

Place these CSV files in `data/` to replace simulated values:

- `hives.csv` — columns: `lat`, `lon`, optionally `name`, `has_detector`
- `removed_nests.csv` — columns: `lat`, `lon`, optionally `date`, `label`

## References

- Lioy et al. 2021 (*Sci. Rep.*) — nest distances and hornet flight speeds
- Kennedy et al. 2018 (*Commun. Biol.*) — nest search radii
- Rojas-Nossa et al. 2022 (*Front. Insect Sci.*) — bearing tolerance and nest buffer zones
- Franklin et al. 2017 (*Appl. Entomol. Zool.*) — nest habitat preferences
- Rome et al. 2015 (*J. Appl. Entomol.*) — nest relocation
