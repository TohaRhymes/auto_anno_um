# UM Spring Semester Research Project
## _Automated Annotation of Tabular Data for Clinical Applications_

Students: Anton Changalidi, Aurora Pia Ghiardelli, Ashkan Karimi Saber, Ivan Poliakov

Supervisors: Shervin Mehryar, Dr. Remzi Celebi

# Project

!!!!!!!!TODO<Project description>!!!!!!!!!!!

# Github Directory structure

- `basic_tasks` - all basic manipulations with MIMIC dataset
    -  `00_download_MIMIC_tables.ipynb` -- how to download mimic tables
    -  `01_generate_patient_tables.ipynb` -- how to generate data for one specific patient
    -  `02_annotate_patient_tables.ipynb` -- how to manually annotate data for one patient through code
    -  `data` - directory in which all manipulations were performed
-  `full_anno` - full annotation steps for one patient: data selection, CTA, CPA, CEA.
    - `select_specific_patient_merge_tables.ipynb` - select all tables for specific patient (randomly selected).
    - `add_cea_for_chartevents.ipynb` - adding CEA using manually created CEA dictionary (`cea_dict.py`)
    - `CTA_finished/CTA_merged.csv` -- finished, cross-validated CTA for all tables
    -  Directories:
        - `data` - initial MIMIC III demo data
        - `merged_tables` - merged tables for one patient (after `select_specific_patient_merge_tables.ipynb`)
        - `all_anno` semi-manually performed CTA, CPA, CEA (with usage of `add_cea_for_chartevents.ipynb`)
- `tools_usage` - samples configurations for tools, that can be needed for future:
    - `initial.cfg` - example usage of SDM-RDFizer
    - `run.sh` - example runnig configuration of morph-kgc

# Annotation structure

## CTA

!!!!!!!!TODO<about cross validation>!!!!!!!!!!!

Result:
    - `CTA_finished/CTA_merged.csv` -- for all tables
    - `all_anno/*_anno.xlsx` -- for each patient (`CTA_CEA` sheet)
## CPA

!!!!!!!!TODO<about 2 formats>!!!!!!!!!!!

Result:
    - `all_anno/*_anno.xlsx`, `CEA_short` sheet: ...
    - `all_anno/*_anno.xlsx`, `CEA_long` sheet: ...

## CEA
!!!!!!!!TODO<description needed>!!!!!!!!!!!
Result:
    - `all_anno/*_anno.xlsx` -- for each patient (`CTA_CEA` sheet)


# References

[] Shervin Mehryar and Remzi Celebi. “Semantic Annotation of Tabular Data for Machine-to-Machine Interoperability via Neuro-Symbolic Anchoring”. In: SemTab’23: Semantic Web Challenge on Tabular Data to Knowledge Graph Matching 2023, co-located with the 22nd International Semantic Web Conference (ISWC). Corresponding author: Shervin Mehryar (shervin.mehryar@maastrichtuniversity.nl). CEUR Workshop Proceedings. Athens, Greece, Nov. 2023. url: http://ceur-ws.org/Vol-3557/paper5.pdf.
[] MIMIC
[] SEMTAB
[] SDM RDFizer
[] morph-kgc
