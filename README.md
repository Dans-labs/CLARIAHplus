=======================================================
CMDI/XML exploration tool
=======================================================

*by Slava Tykhonov, Data Archiving and Networked Services (DANS-KNAW) https://dans.knaw.nl

*Created for CLARIAH+ WP3 https://clariah.nl

*Licensed under GPLv3*

# Usage

```
usage: cmdi2dict.py [-h] [-j] [-s] [-H] [-i inputfile] [-o outputfile] [-D inputfolder] 

optional arguments:
  -h, --help                  show this help message and exit
  -j, --json                  convert CMDI format to JSON
  -s, --stats                 generate statistics of CMDI fields
  -H, --hierarchy             extract hierarchy of CMDI fields 
  -i inputfile, --ifile       Input CMDI file
                              Provide an input file in CMDI/XML format
  -D inputfolder, --idir      Input folder with CMDI files
                              Does processing of all fields in the folder
  -o outputfile, --ofile      Output file 
                              Provide an file to save fields statistics or export metadata 
```

# Test data
Some CMDI examples available for testing purposes in /tests folder

# Collecting statistics of CMDI fields

```
cmdi2dict.py -s -i ./tests/test2.xml
```
Expected result is the frequency statistics of all fields
```
Title 160
Topic 80
Code 64
Country 16
Region 16
Address 16
Continent 16
Location 8
DOCMAP 4
#document 2
None
```

# Convert CMDI to JSON format
cmdi2dict.py -j -i ./tests/test2.xml
```
{'#document': {'DOCMAP': {'Topic': [{'#attributes': {'Target': 'ALL'}, 'Title': 'My Document'}, {'Topic': [{'#attributes': {'Target': 'ALL'}, 'Title': 'Basic Features'}, {'Topic': {'#attributes': {'Target': 'ALL'}, 'Title': 'Platforms Supported'}, '#attributes': {'Target': 'ALL'}, 'Title': 'About This Software'}], '#attributes': {'Target': 'ALL'}, 'Title': 'Overview'}], 'Location': {'Country': {'Code': 'NL'}, 'Region': 'Unknown', 'Continent': {'Code': 'EU'}, 'Address': 'often stated in the first part of the audio recording'}}}}
```
