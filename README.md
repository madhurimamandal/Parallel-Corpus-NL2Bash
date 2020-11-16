# A-natural-language-to-bash-commends-parallel-corpus
An effort to create a natural language to bash command parallel corpus.

Datasets retrieved from [StackExchange](https://data.stackexchange.com/help), which is licensed under [CC BY-SA](https://creativecommons.org/licenses/by-sa/4.0/legalcode).

The .txt files provide the SQL commands used to retrieve data from [StackExchange Data Dump Explorer](https://data.stackexchange.com/help).

Query_Results_Merged.csv contains the merged and de-duplicated results from the queries.

download.ipynb explains how the answer and question bodies were retrieved using the posts ids obtained from Query_Results_Merged.csv.

merge.ipynb explains initial efforts to reduce noise in the obtained answer bodies.
