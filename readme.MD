

# Introduction
  

This repository contains code and data for my article "[Clinical Trial Search with Google Spanner: Graph, SQL, Vector, and LLM All in One Query](https://medium.com/@dgg32/clinical-trial-search-with-google-spanner-graph-sql-vector-and-llm-all-in-one-query-5ada29f840cd)". 



  

# Prerequisite

UMLS free tier

GCP account with Spanner

Enbale Vertex AI API in the GCP project, increase its quota if possible (default 5)


# Run
0. If you want to reannotate the drugs in the trial data, create a config.yaml in the directory and fill in the following information:

> >  umls_token: [YOUR_UMLS_TOKEN]
> > google_sheet_id: [YOUR_MANUAL_CURATION_SHEET_ID]
> >  google_sheet_node_name: [YOUR_MANUAL_CURATION_SHEET_NAME]

>The Google sheet is used to correct some mismapping of UMLS. It contains three columns: "substance", "correct_cui", and "preferred_umls_name". The substance contains the  drugs that you want to manually correct. Correct_cui contains a semicolon delimited list of CUI that you want the drugs map to. And the preferred_umls_name is a semicolon delimited list of names that correspond to the CUI. An example is 

>| substance    | correct_cui | preferred_umls_name |
>| -------- | ------- |
>| lapatinib plus capecitabine  | C1506770;C0671970   | lapatinib;capecitabine |

1. Fill in the database details in Cell 5 in setup_spanner.ipynb, and run it
  
2. Check the data integrity on your Spanner console 


## Authors

  

*  **Sixing Huang** - *Concept and Coding*

  

## License

  

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details
