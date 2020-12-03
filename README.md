# A-natural-language-to-bash-commends-parallel-corpus
An effort to create a natural language to bash command parallel corpus.

Datasets retrieved from [StackExchange](https://data.stackexchange.com/help), which is licensed under [CC BY-SA](https://creativecommons.org/licenses/by-sa/4.0/legalcode).

QueryFile 1.txt to QueryFile 6.txt files provide the SQL commands used to retrieve data from [StackExchange Data Dump Explorer](https://data.stackexchange.com/help). Specifically from [AskUbuntu](https://askubuntu.com/) and [Unix and Linux](https://unix.stackexchange.com/).

[Data](https://drive.google.com/drive/folders/1BGcCoJ48bwVv_mYgzEGTn08cNh2dp1o6?usp=sharing) folder has all the intermediate data files and also the final dataset.

The files Dataframe_Linux.csv and Dataframe_AskUbuntu.csv under the Data folder linked above are the results obtained from the above queries. 

[download_answers.ipynb](https://github.com/madhurimamandal/Natural-Language-to-Bash-Commands-Parallel-Corpus/blob/main/download_answers.ipynb) is used to download answers form stackexchange by sending http get requests, according to Ids obtained above in Dataframe_Linux.csv and Dataframe_AskUbuntu.csv files.

