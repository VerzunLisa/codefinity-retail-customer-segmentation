-e This file is a merged representation of the entire codebase, combined into a single document

## Purpose
This file contains a packed representation of the entire repository's contents.
It is designed to be easily consumable by AI systems for analysis, code review,
or other automated processes.

## File Format
The content is organized as follows:
1. This summary section
2. Repository information
3. Directory structure
4. Multiple file entries, each consisting of:
  a. A header with the file path (## File: path/to/file)
  b. The full contents of the file in a code block or first three lines for files with .csv extensions

## Usage Guidelines
- This file should be treated as read-only. Any changes should be made to the
  original repository files, not this packed version.
- When processing this file, use the file path to distinguish
  between different files in the repository.
- Be aware that this file may contain sensitive information. Handle it with
  the same level of security as you would the original repository.

## Notes
- This file includes only .ipynb and .csv file contents in full or partial form
- All other file types are represented only through the directory structure
- Binary files are not included in this packed representation. Please refer to the Repository Structure section for a complete list of file paths, including binary files

# Directory Structure

````
./
fs_report.md
.gitkeep
notebook.ipynb
Online_Retail.csv
````
-e 
# Files
-e 
## File: Online_Retail.csv
````
InvoiceNo,StockCode,Description,Quantity,InvoiceDate,UnitPrice,CustomerID,Country
540267,21240,BLUE POLKADOT CUP,96,06.01.2011 11:12,0.72,12415.0,Australia
567085,23293,SET OF 12 FAIRY CAKE BAKING CASES,16,16.09.2011 12:38,0.83,12434.0,Australia
````
-e 
## File: notebook.ipynb
````
{"nbformat":4,"nbformat_minor":5,"metadata":{"kernelspec":{"display_name":"Python 3 (ipykernel)","language":"python","name":"python3"},"language_info":{"name":"python","version":"3.8.10","mimetype":"text/x-python","codemirror_mode":{"name":"ipython","version":3},"pygments_lexer":"ipython3","nbconvert_exporter":"python","file_extension":".py"}},"cells":[{"source":"## Data Loading & Cleaning","metadata":{},"id":"7907a26a-d033-4ff1-9e18-c5c0a60a062c","cell_type":"markdown"},{"source":"import pandas as pd\n\nretail_df = pd.read_csv(\"Online_Retail.csv\")\nretail_df = retail_df.dropna(subset=[\"CustomerID\"])\nretail_df = retail_df[retail_df['Quantity'] >= 0]\nretail_df['TotalSum'] = retail_df['Quantity'] * retail_df['UnitPrice']\nretail_df['InvoiceDate'] = pd.to_datetime(retail_df['InvoiceDate'], format=\"%d.%m.%Y %H:%M\")\nprint(retail_df.info())","metadata":{},"id":"510b73f8-df0e-4811-b3ae-b39b3e601725","cell_type":"code","execution_count":1,"outputs":[{"output_type":"stream","name":"stdout","text":"<class 'pandas.core.frame.DataFrame'>\nIndex: 26373 entries, 0 to 36109\nData columns (total 9 columns):\n #   Column       Non-Null Count  Dtype         \n---  ------       --------------  -----         \n 0   InvoiceNo    26373 non-null  object        \n 1   StockCode    26373 non-null  object        \n 2   Description  26373 non-null  object        \n 3   Quantity     26373 non-null  int64         \n 4   InvoiceDate  26373 non-null  datetime64[ns]\n 5   UnitPrice    26373 non-null  float64       \n 6   CustomerID   26373 non-null  float64       \n 7   Country      26373 non-null  object        \n 8   TotalSum     26373 non-null  float64       \ndtypes: datetime64[ns](1), float64(3), int64(1), object(4)\nmemory usage: 2.0+ MB\nNone\n"}]},{"source":"## RFM Calculation","metadata":{},"id":"87d9bd7d-b0e0-451f-82b1-d1752df1f12a","cell_type":"markdown"},{"source":"# Write your code below","metadata":{},"id":"c49d0171-01ca-400f-8957-bdfeeee5125f","cell_type":"code","execution_count":1,"outputs":[]}]}````
