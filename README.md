---
output:
  pdf_document: default
  html_document: default
---
# Project Documentation

## Overview

This project calculates a path for renovating German residential buildings that conforms to current climate goals. Moreover, it analyzes the costs and economic as well as distributional effects of a green transformation of the (German) residential sector.

This readme introduces the main components of the underlying project, which is implemented in \textit{R}. 

## Folder Structure

The project directory is organized as follows:

```
- Code
  - 1_Climate_goals.Rmd
  - 2_Data_Cleaning.Rmd
  - 3_Analysis.Rmd
  - 4_Cost_and_distribution.Rmd
  - 5_Input-Output_Analysis.Rmd
  - 6_Results_and_Graphs.Rmd
- Data
  - Data on residential buildings [not enclosed]
  - Data on private wealth [not enclosed]
  - IO-Table for Germany for 2019 (`IO_data_EN2019.csv`)
  - Preliminary information on assigning costs to sectors (`cost_factors_renovation_IO.csv`)
- Graphs
  - [generated plots]
- Intermediate_Results
  - [calculated intermediate results]
  - [not enclosed: representative dataset on buildings as created in section 2]
- Results
  - [calculated final results]
  - [not enclosed: final, adapted dataset on buildings as created in section 3]
  - [not enclosed: representative dataset on buildings as created in section 2]
- Supplemental_Material
  - Working_Paper.pdf
- Gebaude_Git.Rproj
```

### 1. Code

This folder contains the scripts required to perform the analysis. The R scripts are named and ordered sequentially to guide the user through the workflow. For every script a knitted PDF output is supplied to ensure tractability

1. **1_Climate_goals.Rmd**: Calculates a climate path for renovating German residential buildings in accordance with legal requirements and goals.
2. **2_Data_Cleaning.Rmd**: Cleans the data necessary for analysis and creates a (more) representative dataset.
3. **3_Analysis.Rmd**: Contains a toolbox to calculate emission savings from improving insulation and replacing heating facilities, which can be adapted for other countries.
4. **4_Cost_and_distribution.Rmd**: Calculates the costs and distributional effects of a green transformation in the German residential sector.
5. **5_Input-Output_Analysis.Rmd**: Takes the additional costs to calculate economic impacts (e.g. on GDP, employment or imports).
7. **6_Results_and_Graphs.Rmd**: Compiles results and generates concluding graphs.

In section 2-4 the code requires the user to specify a desired renovation rate. In sections 2 and 3 this renovation rate is a design parameter representing the choice set of a imaginary social planner and, hence, should be made consistent. In section 4 the renovation rate is just a parameter for picking the correct intermediate output to calculate economic impacts for the desired scenario in sections 4 and 5.

To compare the carbon impact for several renovation rates the code in sections 2-3 has to be executed consecutively for different renovation rates, which can be compared by employing section 6. Due to this modular structure different parts of the analysis can be performed in isolation.

Package dependencies are typically visible at the start of each section. In general we assume the user has a current version of the `here`-package installed.

### 2. Data 

This folder contains the the relevant data for the IO model (code sections 5 and 6). Other data used in the project cannot be shared directly but can be obtained from:
- RWI: [Link to RWI data](https://www.rwi-essen.de/en/research-advice/further/research-data-center-ruhr-fdz/data-sets)
- HFCS: [Link to HFCS data](https://www.ecb.europa.eu/stats/ecb_surveys/hfcs/html/index.en.html)

### 3. Graphs

This folder will store all plots generated from the code. 

### 4. Intermediate_Results and Results

The first of these folders stores all calculated intermediate results, the latter collects final results. In these folders, we show all files as produced by our code except those files, that reproduce confidential information.

A second version of this folders with the suffix `-orig` exists to ensure that original outputs always remain available and are never overwritten. Consequentially, these folders are not referenced in the code.

### 5. Supplemental Material

Contains the current version of our working paper.

### 6. Gebaude_Git.Rproj

This is the R Project file. Opening this file in RStudio sets up the working directory and environment for the project.

