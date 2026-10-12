## Dataset Preparation and Annotation

### 1. Dataset Overview

The Yuecheng UAV dataset was constructed from RGB UAV orthophotography acquired over Yuecheng, Jincheng, Shanxi Province, China. The original orthomosaic has a spatial resolution of 0.05 m and a size of 57,890 × 35,228 pixels.

The dataset contains six land-cover classes: agricultural land, building, bare land, road, water, and vegetation.

### 2. Dataset Partitioning

To reduce spatial overlap between training and evaluation samples, the original orthomosaic was divided into non-overlapping 4,608 × 4,608 blocks. These blocks were assigned to the training, validation, and test sets at a ratio of 6:2:2 using class-stratified sampling. Each block was subsequently cropped into 512 × 512 image patches.

Patches originating from the same block were kept within the same subset. This partitioning strategy avoids overlap between training and evaluation patches caused by the cropping procedure, although spatial correlation may remain between different blocks.

### 3. Annotation Procedure and Quality Control

The dataset was annotated by one annotator using a combination of object-based image analysis and manual visual interpretation.

An initial land-cover classification was generated using eCognition software. The classification results were subsequently inspected and manually corrected with reference to the original high-resolution UAV imagery.

Annotation quality control was performed through visual inspection and correction of the initial classification results. Particular attention was given to areas with similar visual characteristics, ambiguous class boundaries, and potential confusion between agricultural land and vegetation.

The final pixel-level labels were obtained after manual correction. The annotation process did not include an independent multi-annotator agreement assessment.

### 4. Land-Cover Class Definitions

| Class | Description |
|---|---|
| Agricultural land | Cultivated or identifiable agricultural fields, including terraced fields and areas with recognizable cultivation patterns or field boundaries. |
| Building | Identifiable buildings and roofed structures. |
| Bare land | Exposed soil and other unvegetated ground not identified as agricultural land. |
| Road | Identifiable roads and transportation surfaces. |
| Water | Rivers, ponds, and other visible surface water bodies. |
| Vegetation | Trees, shrubs, grassland, and other non-agricultural vegetated areas. |

#### Distinction Between Agricultural Land and Vegetation

Agricultural land was identified primarily based on recognizable cultivation patterns, such as terraced fields and field boundaries, together with surrounding land-use context. Vegetation includes trees, shrubs, grassland, and other non-agricultural vegetated areas.

During manual interpretation, color, texture, spatial patterns, and surrounding context were jointly considered to distinguish these two classes, particularly in areas with similar spectral appearances.

The distinction was therefore based on a combination of visual and contextual characteristics rather than vegetation color alone.

### 5. Spatial Characteristics and Limitations

The Yuecheng UAV dataset was constructed from a single orthomosaic covering one geographic area and one acquisition. The original imagery was divided into non-overlapping spatial blocks before dataset partitioning to reduce overlap between training and evaluation samples. However, spatial autocorrelation may remain between different blocks.

The dataset is limited to the available imagery and does not represent variations across geographic regions or acquisition conditions. Therefore, repeated training runs on the fixed dataset split reflect model training variability rather than uncertainty across independent geographic regions. These limitations should be considered when interpreting the experimental results.
