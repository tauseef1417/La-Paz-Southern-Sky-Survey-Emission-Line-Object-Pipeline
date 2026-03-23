# La Paz Southern Sky Survey — Emission-Line Object Pipeline

Code and analysis for:

> **Feasibility study for novel application of Southern Sky La Paz survey 
> low dispersive spectral plates in recent astrophysics**  
> T. A. Zafar, R. Hudec — 2026

## Overview
A two-stage deep learning pipeline for extracting emission-line object 
candidates from digitized archival low-dispersion spectroscopy (LDS) 
photographic plates of the La Paz Southern Sky Survey (Bolivia, 1926–1929).

**Pipeline stages:**
1. Multi-scale background subtraction + connected component detection
2. Unsupervised anomaly scoring via 1D Convolutional Autoencoder + Isolation Forest
3. Human review & binary mask generation
4. Supervised classification via fine-tuned ResNet18

**Results on 168 plates:**
- 186,965 spectral candidates detected
- 49,775 emission-object candidates confirmed (P ≥ 0.5)
- 92.4% internal validation accuracy
- Full 168-plate processing: < 2 hours on single Tesla T4 GPU

## Repository Structure
```
lapaz-survey-pipeline/
├── Lapaz_Paper.ipynb       # Main pipeline notebook (Google Colab)
├── README.md
├── requirements.txt
└── sample_outputs/         # Example figures from the paper
```

## Requirements
See `requirements.txt`. Run on Google Colab (T4 GPU recommended).

## Usage
Open `Lapaz_Paper.ipynb` in Google Colab:

[![Open In Colab](https://colab.research.google.com/github/tauseef1417/La-Paz-Southern-Sky-Survey-Emission-Line-Object-Pipeline/blob/main/Lapaz_Paper_clean.ipynb)

Mount your Google Drive and point the plate directory variable to your 
digitized plate collection.

## Citation
If you use this code, please cite:
```
@article{hudec2026lapaz,
  title={Feasibility study for novel application of Southern Sky La Paz 
         survey low dispersive spectral plates in recent astrophysics},
  author={Zafar, Tauseef Ahmad and Hudec, René},
  year={2026}
}
```

## Data Availability
The La Paz plates are held at Sonneberg Observatory, Germany, 
and are available upon request from the observatory.

## License
MIT License
