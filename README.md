# specieurope_v3.0_cleanup

## Description

`specieurope_v3.0_cleanup` is designed to clean the `SPECIEUROPE v3.0` database up.
`SPECIEUROPE` is a database of European air pollution source profiles, designed for source apportionment and emission analysis, with species encoding aligned to the US EPA SPECIATE system. It contains ca. 200 particulate chemical profiles (organic and inorganic) derived from measurements, source apportionment studies, composites, and theoretical estimates.
More information is available at https://source-apportionment.jrc.ec.europa.eu/Specieurope/index.aspx.

## What does the script do

Main cleanup steps:

1. Rename columns to follow other similar databases, e.g., Relative Mass to weight_fraction.

2. Check Name and CAS for odd characters and edit values.

3. Format CAS and ensure text format to avoid unwanted Excel conversion.

4. Save unique Name and CAS# set for PubChem InChIkeys and other useful data retrieval:

- Retrieve data using PubChem_Retriever (available at https://github.com/r3bryk/PubChem_Retriever).
- Update SPECIEUROPE with the retrieved data using Data_Retriever (available at https://github.com/r3bryk/Data_Retriever).

5. Write filtered SPECIEUROPE (intermediate) to CSV file if needed.

6. Load SPECIEUROPE updated with PubChem InChIKeys and other data.

7. Remove compounds:

- With no InChIKey values.
- With specific InChIKey values (e.g., mixtures, inorganic compounds & inorganic mixtures, etc.).
- With unwanted keywords (e.g., mixtures, minerals, inorganic compounds & inorganic mixtures, etc.).

8. Sort and save filtered CPDat as CSV file.

## Prerequisites

1. The script is written in Python 3; https://www.python.org/downloads/windows/.
2. The script is run in JupyterLab Notebook; https://jupyter.org/.

## How to use the script

Run the script cell by cell in JupyterLab Notebook.

## License

[![MIT License](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/license/mit)

Intended for academic and research use.
