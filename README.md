# clinical_note_splitter
split_clinical_notes

Hospital-specific Data Processing Script
Disclaimer: This script is tailored for specific hospital sites and is not part of the main repository.

Introduction
This Python script focuses on processing clinical notes from certain hospital sites. The primary goal is to extract relevant information from the notes and structure them into manageable chunks. The script utilizes the Pandas library for data manipulation and Regex for pattern matching.

Features
1. Date-based Chunk Extraction
The script includes a function, find_date(txt), that identifies date-based chunks within the clinical notes. It scans for a specific pattern indicating the start of a chunk and extracts the text within a defined window. The timestamp within each chunk is then validated, and the chunks are organized with additional metadata.

2. Clinical Note Splitting
The split_clinical_notes(clin_note) function processes a DataFrame containing clinical notes. It iterates through each note, calls the find_date function to extract chunks, and structures the data for further analysis. The resulting DataFrame includes information such as client ID, body text, timestamp, and more.

3. Data Integration
The split_and_append_chunks(docs, verbosity=0) function combines the processed clinical notes with non-clinical notes. It involves the following steps:

Separating clinical and non-clinical notes from the input DataFrame.
Renaming the '_id' column to 'id' for consistency.
Utilizing the split_clinical_notes function to process clinical notes.
Concatenating the processed clinical notes with the non-clinical notes.
Resetting the index for the final DataFrame.
Usage
To integrate and process your data, follow these steps:

Ensure you have the required libraries installed:

```bash
pip install pandas regex
```
Import the script into your project:

```python
from data_processing_script import split_and_append_chunks
```
Call the split_and_append_chunks function with your DataFrame:

```python
processed_data = split_and_append_chunks(your_data_frame)
```

```python
split_and_append_chunks(docs = dataframe_containing_documents)
```

Adjust the verbosity level if needed.

Notes
The script assumes a specific structure for the clinical notes and may require adjustments for different formats.
Review the output DataFrame (processed_data) to ensure proper integration and chunk extraction.
Feel free to adapt and extend the script based on your specific requirements. If you encounter issues or have suggestions, please let us know.
