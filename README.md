# PDN Project — Drosophila Neurotransmitter Mapping

Analysis code for mapping GABA neurotransmitter expression onto the reconstructed L1 *Drosophila melanogaster* larval CNS connectome, as part of the PDN project (AY2025-2026).

## Project Overview

A connectome describes all neurons and their synaptic connections, but a wiring diagram alone is insufficient for functional interpretation. This project maps neurotransmitter identity (specifically GABA) onto individually identified neurons in the larval *Drosophila* brain by overlaying fluorescence light-sheet microscopy data onto electron microscopy (eFIB-SEM) reconstructions. Neurons were traced and identified in CATMAID, and the DAMd1 and CP1 lineages were used as case studies to assess the consistency of neurotransmitter expression within and across hemilineages.

## Notebooks

| Notebook | Description |
|---|---|
| `Cable_Length_Comparison.ipynb` | Compares cable lengths of neurons traced in the GABA volume against equivalent neurons in the reference Seymour volume (Winding et al. 2023), as a measure of reconstruction completeness |
| `DAMd1 Comparison.ipynb` | Assesses consistency of GABA fluorescence intensity across left-right homologous pairs in the DAMd1 lineage; includes paired t-test and Wilcoxon signed-rank test |
| `Cell_Body_Cluster.ipynb` | Evaluates spatial clustering of neurons with similar fluorescence intensities within the CP1 lineage (CP1d and CP1v hemilineages); includes Mann-Whitney U test and KDE plots |
| `Ishan_nblast.ipynb` | Runs NBLAST morphological similarity scoring to identify traced GABA-volume neurons against the reference L1 CNS connectome |
| `Fluorescence.ipynb` | Processes raw fluorescence data and generates the soma locations CSV used by other notebooks |

## Dependencies

```
pip install pymaid navis scipy matplotlib seaborn plotly
```

- [`pymaid`](https://pymaid.readthedocs.io/) — interface with CATMAID for fetching neuron skeletons and annotations
- [`navis`](https://navis.readthedocs.io/) — neuron analysis and NBLAST implementation
- `scipy` — statistical tests (Shapiro-Wilk, paired t-test, Wilcoxon, Mann-Whitney U)
- `matplotlib` / `seaborn` / `plotly` — visualisation

## Requirements

Access to a running CATMAID instance is required to fetch neuron data. Credentials not included. 

## Reference

Winding et al. (2023). *The connectome of an insect brain.* Science, 379(6636). https://doi.org/10.1126/science.add9330
