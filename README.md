
# Identifying Cell Type-Defining Genes for Translation to Flow Cytometry

## Project Overview

This project aims to identify key genes that define immune cell types in a single-cell RNA-sequencing dataset. The ultimate goal is to translate these gene markers into flow cytometry applications, making the analysis more accessible and cost-effective. The study utilizes various bioinformatics methods, including dimensional reduction, clustering, and random forest classifiers, to analyze immune cells derived from experimental autoimmune encephalomyelitis (EAE) and PBS-injected controls.

## Prerequisites

To run the analysis, you will need the following software and R packages installed:

- **R (version >= 4.0.0)**
- **RStudio (recommended)**

### Required R Packages:

```R

install.packages(c(
  "Seurat", "ggplot2", "GoodmanKruskal", "caret", 
  "ltm", "arm", "randomForest", "dplyr", 
  "scales", "ROCR", "tidyverse", "caTools", 
  "ROSE", "devtools", "grid", "gridBase", 
  "gridExtra", "ggpubr", "vip", "tidymodels", 
  "kableExtra", "flextable"
))

remotes::install_github("jspaezp/sctree")
devtools::install_github("crazyhottommy/scclusteval")

```

## Project Structure

The project directory should be structured as follows:

```plaintext
project_root/
│
├── data/                    # Directory containing the dataset
│   └── data.RData           # Sample of single-cell RNA-seq dataset file
│
├── README.md                # This README file
└── analysis.Rmd             # The main R Markdown file containing the code and analysis
```

### Data

The dataset used in this project is a single-cell RNA-sequencing dataset downloaded from the Gene Expression Omnibus (GEO) under accession number **GSE146113**. It has been pre-processed into a Seurat object and underwent pre-processing, normalisation, and clustering to isolate the cell types of interest (microglia and monocytes) for this analysis. This data was exported as a seurat object. For reproducibility, a sample is provided in the `data/` directory as `data.RData`. 

If you require access to the full dataset or have any questions, please email claire.wishart@sydney.edu.au. 

## Running the Analysis

To run the analysis:

1. **Clone the repository or download the project files.**

   ```bash
   git clone [project URL]
   ```

2. **Open the project in RStudio.**

3. **Install the required R packages** (if not already installed) by running the R command above.

4. **Load the dataset** into your R environment by running:

   ```R
   load("data/data.RData")
   ```

5. **Run the analysis** by knitting the `analysis.Rmd` file to generate the report:

   - Open `analysis.Rmd` in RStudio.
   - Click the "Knit" button to generate the output (e.g., HTML report).

The output report will include all steps of the analysis, from data preprocessing to the identification of cell type-defining genes using random forest classifiers.

## Output

The output of the analysis will include:

- **Preprocessing of the dataset**: Filtering low-quality cells, normalizing gene expression, and identifying variable genes.
- **Dimensional reduction**: Using PCA to reduce the complexity of the dataset.
- **Clustering**: Grouping cells into distinct cell types.
- **Random Forest Classifier**: Training a model to identify key genes for each cell type and evaluating its performance.
- **Visualizations**: PCA plots, clustering plots, and confusion matrices.

## References

- Gene Expression Omnibus (GEO), GSE146113: [Link to dataset](https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE146113)

## Contact

For any questions or issues, please contact claire.wishart@sydney.edu.au.
