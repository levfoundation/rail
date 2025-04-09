# PubMed Metadata Retriever

## Overview

This script enriches datasets containing PubMed IDs (PMIDs) by retrieving comprehensive metadata for each article, including:

## Title and abstract

 -Author information (names and affiliations)
 
 -MeSH terms
 
 -Publication dates (including electronic publication date [edat])

The tool is specifically designed to run in Google Colab with GPU acceleration for optimal performance when processing large datasets.
Features

 -GPU-Accelerated Processing: Automatically connects to a GPU runtime for faster execution
 
 -Parallel Data Retrieval: Uses multithreading to fetch multiple articles simultaneously
 
 -Batch Processing: Processes PMIDs in batches to respect NCBI's API rate limits
 
 -Comprehensive Metadata: Retrieves all essential PubMed article information
 
 -Error Handling: Robust error handling ensures the process continues even if some API calls fail
 
 -Progress Tracking: Detailed progress reporting during processing
 
 -Multiple Output Formats: Saves results in both CSV and JSON formats

## Requirements

 -Google Colab environment
 
 -Internet connection
 
 -NCBI E-utilities access (free, but requires email address)

 -CSV file containing PMIDs (one PMID per row, with a column header "pmid")

## Usage Instructions

 -Open Google Colab: Go to Google Colab and create a new notebook
 
 -Script: Copy the entire script into a single cell in your Colab notebook
 
 -Configure Settings: Modify the following parameters at the top of the script:

### Required

EMAIL = "your.email@example.com"  # Replace with your email address

### Optional

BATCH_SIZE = 20      # Number of PMIDs to process per batch

MAX_WORKERS = 4      # Number of parallel workers

RATE_LIMIT_DELAY = 0.3  # Delay between API calls in seconds

LIMIT = None         # Set to a number to limit processing (None = process all)

 -Run the Script: Execute the cell by clicking the play button or pressing Shift+Enter
 
 -Upload Your CSV: When prompted, upload your CSV file containing the PMIDs
 
 -Monitor Progress: The script will display detailed progress as it processes your data
 
 -Download Results: After processing completes, run the provided commands to download:

 -CSV file with flattened metadata
 -JSON file with complete metadata



## Output Files
The script generates two output files:

pubmed_metadata.csv:

 -Flattened structure suitable for data analysis
 
 -Contains basic fields (title, abstract, dates)
 
 -Includes up to 5 authors and 10 MeSH terms per article


pubmed_metadata_full.json:

 -Complete metadata in hierarchical JSON format
 
 -Contains all authors, all MeSH terms, and full details
 
 -Recommended for comprehensive analysis or database import



