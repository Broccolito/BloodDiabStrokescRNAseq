# Data Repository for scRNA-seq and Cell Communication Analysis in T2DM Stroke Model

This repository contains the data and Seurat/CellChat objects generated for analyzing the transcriptomic response of peripheral monocytes to Type 2 Diabetes Mellitus (T2DM) and ischemic stroke in a mouse model. Data were generated using single-cell RNA sequencing (scRNA-seq), bulk RNA-seq, and analysis with NicheNet and CellChat. This study aims to reveal molecular and cellular changes in diabetic and ischemic conditions, particularly focusing on interferon signaling and inflammation.

## Repository Structure

### Root Files

- `README.md`: This file, describing the repository and data files.
- `cellchat_object/`: Contains RDA files for CellChat analysis.
- `scrna_sequencing_raw/`: Raw scRNA-seq data files.
- `seurat_object/`: Contains Seurat objects for clustering and visualization.
- `trajectory_object/`: Contains Cell Data Set (CDS) objects for trajectory and pseudotime analysis.

### File Descriptions

#### `cellchat_object/`

- **dbdb_case_cellchat.rda**: CellChat object for the db/db mice with ischemic stroke. Analysis was conducted to identify cell-cell communication patterns altered due to stroke in diabetic conditions.
- **dbdb_control_cellchat.rda**: CellChat object for db/db control (no stroke) mice. Provides baseline data for diabetic conditions.
- **dbp_case_cellchat.rda**: CellChat object for the db/+ (normoglycemic) mice with ischemic stroke, representing the stroke model in non-diabetic conditions.
- **dbp_control_cellchat.rda**: CellChat object for db/+ control (no stroke) mice. Baseline for non-diabetic, non-stroke conditions.

**Methods**: CellChat analysis identifies ligand-receptor interactions to reveal cross-talk between monocyte subtypes, focusing on pathways affected by T2DM and stroke. These data provide insights into thromboinflammatory responses, interferon signaling, and immune suppression in diabetic mice.

#### `scrna_sequencing_raw/`

- **db_db-DMCAO.zip**: Raw scRNA-seq data for db/db mice post-distal middle cerebral artery occlusion (DMCAO).
- **db_db-Sham.zip**: Raw scRNA-seq data for db/db mice with sham surgery (control).
- **db_pos-Sham.zip**: Raw scRNA-seq data for db/+ mice with sham surgery.
- **db_pos-dMCAO.zip**: Raw scRNA-seq data for db/+ mice post-DMCAO.

**Methods**: scRNA-seq was performed using 10X Genomics GemCode Technology. Data were processed with Cell Ranger (v1.3), and differential gene expression analysis was conducted in Seurat with normalization based on UMI counts.

#### `seurat_object/`

- **bloodstroke.rda**: Seurat object containing processed scRNA-seq data of peripheral blood mononuclear cells (PBMCs) from both diabetic and normoglycemic mice under stroke and sham conditions. Contains cell clusters annotated using SingleR and the ImmGen database.
- **monocytes.rda**: Seurat object specifically for monocytes, enriched through re-clustering in Seurat. Enables focused analysis of monocyte subsets and their responses to diabetic and ischemic conditions.

**Methods**: Filtering was performed for cells with fewer than 500 detected genes, and data were normalized using log-normalization. Clustering was carried out with PCA and visualized with UMAP.

#### `trajectory_object/`

- **dbdb_control_cds.rda**: Cell Data Set (CDS) object for db/db control monocytes, representing baseline differentiation trajectory under diabetic conditions.
- **dbdb_stroke_cds.rda**: CDS for db/db stroke monocytes, used to observe pseudotime trajectories and differentiation in diabetic and ischemic states.
- **dbp_control_cds.rda**: CDS for db/+ control monocytes, baseline data for normoglycemic mice.
- **dbp_stroke_cds.rda**: CDS for db/+ stroke monocytes, tracking pseudotime trajectory in response to ischemic stroke.
- **monocytes_cds.rda**: CDS focusing on monocyte trajectory across all experimental conditions, facilitating the comparison of diabetic and normoglycemic trajectories.

**Methods**: Trajectory analysis was conducted in Monocle 3 to explore cellular differentiation paths. Trajectories reveal potential maturation stages and highlight changes due to T2DM and ischemic conditions.

## Methodology Overview

1. **scRNA-seq and Bulk RNA-seq**: Mononuclear cells were isolated and sequenced using 10X Genomics protocols, with analysis in Seurat to determine cell clusters, particularly monocytes. Bulk RNA-seq was used for pathway validation in broader cell populations.
2. **CellChat Analysis**: Ligand-receptor interactions were identified in CellChat, analyzing how cell communication changes with T2DM and stroke. Pathways of interest include the Anxa1-Fpr2 axis for thromboinflammation and MHCII-CD4 for immune activation.
3. **Trajectory Analysis**: Using Monocle 3, we investigated monocyte differentiation paths to uncover the effects of T2DM and stroke on cellular progression. Results demonstrate disrupted monocyte differentiation and increased proinflammatory markers in diabetic stroke conditions.
4. **NicheNet Analysis**: Identified key ligands affecting monocyte gene expression in diabetic versus non-diabetic conditions, highlighting interferon signaling and inflammatory markers such as Ccl6, Ccl9, and Ifng.

## Notes

- Ensure all analyses respect data filtering thresholds as set in Seurat and Monocle.
- Refer to the manuscript for further details on experimental setup, animal models, and additional context.

## License

Data and scripts are available for non-commercial use under a Creative Commons License.