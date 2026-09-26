# TGTA-Flood — Reviewer Reproducibility Package

## Manuscript
**A Terrain-Aware Spatiotemporal AI Framework for Dynamic Flash-Flood Propagation and Location-Aware Early Warning in Mountainous River Networks**

Manuscript reference: ENVSOFT-D-26-03232

## Purpose
This repository is prepared in response to the editor's request for an accessible, interrogable data/model package.

## Data sources

### 1. GeoMorphAI Wayanad Flood ML Dataset
Primary externally sourced Wayanad machine-learning dataset supplied for this repository:
`krupadevaraj/geomorphai-wayanad-flood-ml-dataset`

The original CSV supplied to this repository is retained unchanged at:
`data/source/GeoMorphAI_Wayanad_ML_Dataset_Final.csv`

Verified file-level properties:
- 10,000 records
- 19 columns
- 5,000 Flood_Label=0
- 5,000 Flood_Label=1
- no missing values in the supplied CSV

### 2. Paper reference/prototype dataset
The earlier prototype dataset used during manuscript development is retained separately at:
`data/reference_paper_dataset/`

It is explicitly labelled synthetic/prototype. It must not be represented as observed Wayanad measurements.

## Critical reproducibility statement
The GeoMorphAI dataset contains terrain, coordinates, remote-sensing indices, soil/raster features and a binary flood label. It does **not** contain the complete temporal hydrological and river-network variables required to reproduce every component of TGTA-Flood.

In particular, the supplied GeoMorphAI file does not contain:
- rainfall time series
- water-level time series
- discharge/flow time series
- flow velocity
- timestamps
- directed river-network edges
- flood-arrival-time observations
- mobile-location exposure grids
- vulnerability observations

Therefore this package does **not** fabricate these variables or claim that the GeoMorphAI file alone reproduces the paper's water-level, propagation, arrival-time, DFPRI and location-aware warning experiments.

## Why the two datasets are retained
The editor requested the data and models used in the paper. Retaining the original prototype/reference dataset preserves the provenance of the manuscript-development experiments, while retaining GeoMorphAI provides the externally sourced Wayanad ML dataset used for the spatial/terrain flood-classification component.

## Repository structure

```text
data/
  source/                       # GeoMorphAI source dataset
  processed/                    # non-destructive derived/cleaned datasets
  reference_paper_dataset/      # manuscript prototype/reference data

data_dictionary/
  geomorphai_data_dictionary.csv
  geomorphai_to_tgta_mapping.csv

experiments/
  validate_dataset.py

docs/
  DATA_PROVENANCE.md
  MANUSCRIPT_DATA_ALIGNMENT.md
  REPRODUCIBILITY.md
  EDITOR_RESPONSE_DRAFT.txt
  RELEASE_CHECKLIST.md

src/
baselines/
graph/
models/
configs/
results/
```

## Reproduction principle
No values have been added to the GeoMorphAI source file to make it conform to manuscript tables. Derived files are clearly identified as derived. Any temporal/graph/propagation variables needed for the complete TGTA-Flood pipeline must come from the actual experimental data/model release used to generate the corresponding manuscript results.

## Citation
See `CITATION.cff`.

## License
Code and documentation licensing should be applied only to material owned or distributable by the authors. Dataset redistribution is governed by the source dataset's licence/terms; see `docs/DATA_PROVENANCE.md`.
