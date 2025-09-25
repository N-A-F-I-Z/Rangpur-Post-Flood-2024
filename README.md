# Land Use Land Cover (LULC) and Waterbody Extraction – Rangpur, Bangladesh #

## This project applies Google Earth Engine (GEE) to generate a Land Use Land Cover (LULC) map and extract water bodies for Rangpur District, Bangladesh. The workflow uses Sentinel-2 MSI Level-2A imagery and a Decision Tree (CART) classifier to classify LULC, and applies NDWI/MNDWI indices to extract surface water features. ##

![Rangpur District LULC, NDWI and Extracted Waterbodies Post Flood 2024](Combined%20Map.jpg)

## 🔹 Data Sources ##

- Sentinel-2 L2A MSI (10–30 m resolution, BOA reflectance)

- FAO GAUL 2015 – Level 2 boundaries (for administrative district mask)

## 🔹 Workflow ##

- Study Area Selection

- Rangpur District is extracted from GAUL (ADM2 level) boundaries.

### Image Preprocessing ###

- Sentinel-2 imagery filtered for Oct–Nov 2024 with <10% cloud cover.

- Median composite created and clipped to Rangpur boundary.

- True Color (TC) and False Color (FC) composites prepared for visualization.

### Land Use Land Cover (LULC) Classification ###

- Training samples: waterbody, built-up, agriculture, vegetation, and furrow.

- Features used: Sentinel-2 bands (B2, B3, B4, B8).

- Classifier: CART (smileCart).

- Training (80%) and validation (20%) split applied.

- LULC map generated at 10 m resolution.

- Accuracy assessed using a confusion matrix and an overall accuracy score.

### Waterbody Extraction ###

- NDWI = (Green − NIR) / (Green + NIR)

- MNDWI = (Green − SWIR1) / (Green + SWIR1)

- Threshold-based extraction (NDWI > 0.03) applied to generate a water mask.

## 🔹 Outputs ##

- LULC Map of Rangpur (10 m)

- NDWI Raster

- Extracted Waterbody Layer

## 🔹 Key Applications ###

- Monitoring land cover changes

- Agricultural land management

- Surface water resource assessment

- Supporting local planning and environmental studies

## 🔹 Tools & Libraries ##

- Google Earth Engine (GEE)

- Sentinel-2 MSI dataset

- FAO GAUL boundaries

📌 This repository contains the Earth Engine script and export workflow for reproducibility. Users can modify the region of interest (ROI), time range, and classification scheme to adapt the workflow for other areas of interest.
