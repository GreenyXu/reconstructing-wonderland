# Data-Driven Surface Generation

## Overview

This project explores how visual data can be translated into spatial and architectural surface forms.

By combining computer vision and clustering techniques, image datasets are analysed and transformed into height maps, which can be used as displacement surfaces in Blender.

The workflow connects:

- image data
- feature extraction
- clustering logic
- procedural surface generation

---

## Pipeline

The project is structured into four stages:

### 1. Data Collection
Scraping and organising architectural images.

`01_data_collection.ipynb`

---

### 2. Feature Extraction
Two feature systems are used:

- **HOG (Histogram of Oriented Gradients)**  
  → captures low-level geometry (edges, directions, repetition)

- **CLIP embeddings**  
  → captures high-level semantic similarity

`02_feature_extraction.ipynb`

---

### 3. Clustering Analysis
- PCA for dimensionality reduction
- KMeans clustering
- Comparison between HOG and CLIP feature spaces

Outputs:
- cluster labels
- visual grouping of images

`03_clustering_analysis.ipynb`

---

### 4. Surface Generation
Cluster results are translated into height maps:

- CLIP → defines macro surface type  
- HOG → defines micro geometric behaviour  

Outputs:
- grayscale height maps
- displacement-ready textures for Blender

`04_surface_generation.ipynb`

---

## Outputs

- `/outputs/clustering/` → clustering results  
- `/outputs/heightmaps/` → generated height maps  

---

## Blender Workflow

To use the generated height maps:

1. Create a dense grid mesh
2. Add:
   - Subdivision Surface
   - Displace Modifier
3. Load heightmap image
4. Adjust:
   - Strength (0.2 – 0.6)
   - Midlevel (0.5)

---

## Key Idea

This project treats data as a design driver:

- images → features → clusters → rules → surfaces  

It demonstrates how computational processes can generate spatial form from visual datasets.

---

## Future Work

- Integrating text-based datasets (literature / social media)
- Multi-modal clustering (image + text)
- More complex 3D surface transformations
