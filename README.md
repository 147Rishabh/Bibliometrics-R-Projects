# Bibliometrics-R-Projects
R scripts for bibliometric analysis and visualization using Web of Science data


Due to confidentiality, actual data files are not included, but the script demonstrates the methodology and structure of the analysis. This is intended to help researchers perform similar analyses with their own datasets.

## Tools & Packages Used
- **R**
- **bibliometrix** – for bibliographic data conversion, analysis, and network extraction
- **dplyr** – for data wrangling
- **knitr** – for summary formatting (optional)
- **ggplot2** – for visualizations (optional)

## Key Workflow Steps

1. **Import and Merge Multiple BibTeX Files**
   The first step is to import multiple `.bib` files into R, which are merged into a single dataset:
   ```r
   D <- c("savedrecs.bib", "savedrecs (1).bib", "savedrecs (2).bib", "savedrecs (3).bib", "savedrecs (4).bib", "savedrecs (5).bib", "savedrecs (6).bib", "savedrecs (7).bib", "savedrecs (8).bib", "savedrecs (9).bib", "savedrecs (10).bib", "savedrecs (11).bib", "savedrecs (12).bib", "savedrecs (13).bib", "savedrecs (14).bib", "savedrecs (15).bib", "savedrecs (16).bib", "savedrecs (17).bib", "savedrecs (18).bib", "savedrecs (19).bib", "savedrecs (20).bib", "savedrecs (21).bib", "savedrecs (22).bib")
   M <- convert2df(D, dbsource = "isi", format = "bibtex")
   
# Filter Data for a Specific Time Period

pubs_old <- data.frame(M) %>% dplyr::filter(PY > 2015 & PY < 2019)

#Run Bibliometric Analysis A basic bibliometric analysis is run to generate an overview

#Build and Analyze Collaboration Network
