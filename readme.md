# UM Spring Semester Research Project
## _Automated Annotation of Tabular Data for Clinical Applications_

Students: Anton Changalidi, Aurora Pia Ghiardelli, Ashkan Karimi Saber, Ivan Poliakov

Supervisors: Shervin Mehryar, Dr. Remzi Celebi

# Project

This project focuses on the automated annotation of the MIMIC III Demo dataset, particularly on column type, column property, and cell entity annotations. By developing a robust framework for annotation, the study aims to enhance the interpretability and utility of medical records within electronic health systems. Annotations were initially performed on a subset of records from a single patient, demonstrating the feasibility of both manual and semi-automated processes to achieve high-quality mappings to standard medical ontologies. 

# Github Directory Structure

- `basic_tasks` - all basic manipulations with MIMIC dataset
    - `00_download_MIMIC_tables.ipynb` -- how to download MIMIC tables
    - `01_generate_patient_tables.ipynb` -- how to generate data for one specific patient
    - `02_annotate_patient_tables.ipynb` -- how to manually annotate data for one patient through code
    - `data` - directory in which all manipulations were performed
- `full_anno` - full annotation steps for one patient: data selection, CTA, CPA, CEA.
    - `select_specific_patient_merge_tables.ipynb` - select all tables for specific patient (randomly selected).
    - `add_cea_for_chartevents.ipynb` - adding CEA using manually created CEA dictionary (`cea_dict.py`)
    - `CTA_finished/CTA_merged.csv` -- finished, cross-validated CTA for all tables
    - Directories:
        - `data` - initial MIMIC III demo data
        - `merged_tables` - merged tables for one patient (after `select_specific_patient_merge_tables.ipynb`)
        - `all_anno` semi-manually performed CTA, CPA, CEA (with usage of `add_cea_for_chartevents.ipynb`)
- `tools_usage` - samples configurations for tools, that can be needed for future:
    - `initial.cfg` - example usage of SDM-RDFizer
    - `run.sh` - example running configuration of morph-kgc
- `16-PresentationPhase3.pdf` - final presentation;
- `16-ReportPhase3.pdf` - final report.

# Annotation Structure

## CTA (Column Type Annotation)
The CTA process involved the annotation of column types within the MIMIC dataset to enhance data interpretability and automation compatibility. This was conducted with cross-validation to ensure accuracy.

Result:
- `CTA_finished/CTA_merged.csv` -- for all tables
- `all_anno/*_anno.xlsx` -- for each patient (`CTA_CEA` sheet)

## CPA (Column Property Annotation)
CPA annotations were structured in two formats to facilitate different analytical needs, detailing the relationships between column properties.

Result:
- `all_anno/*_anno.xlsx`, `CEA_short` sheet: shortened format
- `all_anno/*_anno.xlsx`, `CEA_long` sheet: detailed format for comprehensive analysis (indirect properties are shown fully)

## CEA (Cell Entity Annotation)
CEA involved annotating specific data elements within cells to link them accurately to standardized medical terminologies, greatly enhancing the dataset's utility for clinical and research applications.

Result:
- `all_anno/*_anno.xlsx` -- for each patient (`CTA_CEA` sheet)


# References


[1] Bader Aldughayfiq et al. “Capturing Semantic Relationships in Electronic Health Records
Using Knowledge Graphs: An Implementation Using MIMIC III Dataset and GraphDB”.
In: Healthcare 11.1762 (2023), pp. 1–25. doi: 10.3390/healthcare11121762. url: https:
//doi.org/10.3390/healthcare11121762.

[2] Shervin Mehryar and Remzi Celebi. “Semantic Annotation of Tabular Data for Machine-toMachine Interoperability via Neuro-Symbolic Anchoring”. In: SemTab’23: Semantic Web
Challenge on Tabular Data to Knowledge Graph Matching 2023, co-located with the 22nd
International Semantic Web Conference (ISWC). Corresponding author: Shervin Mehryar
(shervin.mehryar@maastrichtuniversity.nl). CEUR Workshop Proceedings. Athens, Greece,
Nov. 2023. url: http://ceur-ws.org/Vol-3557/paper5.pdf.

[3] Johnson, A. E. W., Pollard, T. J., Shen, L., Lehman, L. H., Feng, M., Ghassemi, M., Moody, B., Szolovits, P., Celi, L. A., & Mark, R. G. (2016). MIMIC-III, a freely accessible critical care database. Scientific Data, 3, 160035.

[4] Johnson, A., Pollard, T., & Mark, R. (2016). MIMIC-III Clinical Database (version 1.4). PhysioNet. https://doi.org/10.13026/C2XW26.

