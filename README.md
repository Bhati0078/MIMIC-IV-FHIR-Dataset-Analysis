# MIMIC-IV FHIR Dataset Analysis

This repository contains Python code for analyzing the MIMIC-IV FHIR dataset. The dataset consists of several `.ndjson` files, each representing a different type of healthcare data, such as patient information, conditions, encounters, etc.

## Files of Interest

The main files of interest are:
1. `Patient.ndjson`: Contains all the patients in the MIMIC-IV demo dataset. Each line of this file represents an individual patient JSON file.
2. `Condition.ndjson`: Contains diseases that were assigned to patients. Each line of this file represents a JSON referencing a specific disease that was assigned to a patient. The JSON object also references an encounter that was associated with each such condition.
3. `Encounter.ndjson`: Contains the details of an encounter in each line.
4. `EncounterICU.ndjson`: This file has the same format as `Encounter.ndjson`.

## Assignment

The goal of this assignment is to:
1. Get familiar with the JSON object format contained in each line of the 4 files.
2. For each patient, create an array of conditions associated. The expected output for this is a dictionary with `patient_id` as key and an array of `Condition` JSON as value.
3. For each condition, assign an estimated time for the condition using the corresponding encounter in the `Encounter.json` or `EncounterICU.ndjson`. Choose the `start_time` in the `Encounter` to associate time to each condition.
4. Finally, create a CSV file with the following columns:
   - Patient_id (Column name: `pid`)
   - Timestamp (unix format) (Column name: `time`)
   - Condition code (Column name: `code`)
   - Condition string (Column name: `description`)

## Checking the Output

To check if the output is correct, you can manually inspect the generated CSV file. You can also write additional Python code to cross-verify the data with the original `.ndjson` files. For example, you can check if all patient IDs in the CSV file exist in the `Patient.ndjson` file, or if all condition codes in the CSV file exist in the `Condition.ndjson` file. 

## Code

The Python code for this assignment is provided in the repository. It reads the `.ndjson` files, processes them according to the assignment requirements, and writes the output to a CSV file. The paths for the files are specified in the code. Please ensure to update these paths as per your local setup before running the code. 
