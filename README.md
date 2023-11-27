# Project Contributors

Group 3:

Anne Skov-Johannessen s184330, github: AnneSkov-J

Dea F. Skipper s184324, github: deax0203

Helene B. L. Petersen s194699, github: HelenePetersen

Johanne B. Overgaard s194691, github: jobaov

Rebecca C. Grenov s184344, github: RebeGr

However, the statistics showed in Github insights are not reflected by the true contributions in this project. Several commits was done without being aware these was not tracked on our accounts. This results in more than 5 authors are reflected, because the rest are tracked as anonymous. This project has been done with everyone contributing equally.

# File organisation

This repository is organized with a data, doc, R and results folder. In data is a raw folder created with the data downloaded, which is obtained from Gene Expression Omnibus (GEO) under the accession number GSE50834. The rest of the data folder is filled with intermediary output files when running the scripts. The final data folder will contain two output files from 01_load.qmd, one file from 02_clean.qmd and one file from 04_augment.qmd. All output tsv files are named corresponding to the script number it is produced from.

The doc folder contain the presentation and an image folder with files used in the presentation.qmd, not generated from our own analysis.

The R folder contain the scripts to perform the analysis.

The results folder contain outputs generated from scripts in the R folder to be included in the presentation. All scripts rendered to html files are also placed here.

## 01_load.qmd

This script load gene expression and meta data and extract relevant variables.

Output: Data is saved as 01_dat_load_count.tsv and 01_dat_load_meta.tsv

## 02_clean.qmd

This script perform data wrangling on gene expression data and meta data respectively to turn it into a tidy format, where each variable have its own column, each observation have its own row and each value have its own cell. When the desired format are obtained is gene expression and meta data joined. A patient replicate are handled by taking the average of the multiple samples and adding a variable "modified", explaining if the original data have been modified.

Output: Data is saved as 02_dat_clean.tsv

## 03_describe.qmd

This script load in the cleaned data and create a bar plot and table showing the distribution of males and females for each patient group; HIV and HIV/TB.

Output: Bar plot is saved in the results folder as barplot_patient_group.png.

## 04_augment.qmd

This script load in the cleaned data and normalized it by quantile normalization and log2 transformed. This data is saved as 04_dat_aug.tsv. A visualization of the normalization effect is shows in two box plots.

Output: Box plots saved in the result folder as non_normalized_expr.png and normalized_expr.png.

## 05_analysis_1.qmd

The augment data are loaded and used for a principal component analysis, where the first principal component is plotted against the second principal component in a scatter plot. A bar plot is created to show how much variance each principal component explains.

Output: Plots saved in the results folder as scatter_pc1_pc2.png and var_explained.png.

## 06_analysis_2.qmd

The augment data are loaded and used to perform a linear regression model to find significantly enriched gene expression in HIV/TB. The results are showed in a forest and volcano plot. Finally are the significant genes compared with the gene list from the original paper, to explore if an intersection could be found.

Output: Plots saved in the result folder as forest_plot.png and volcano_plot.png.

## 00_all.qmd

When this script is rendered it run each of the scripts above and create a rendered html file for each. It also connects all the scripts and create one html file with the complete analysis.

Output: html files saved in the results folder.
