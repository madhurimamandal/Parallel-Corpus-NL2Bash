# A-natural-language-to-bash-commends-parallel-corpus
An effort to create a natural language to bash command parallel corpus.

Datasets retrieved from [StackExchange](https://data.stackexchange.com/help), which is licensed under [CC BY-SA](https://creativecommons.org/licenses/by-sa/4.0/legalcode).

QueryFile 1.txt to QueryFile 6.txt files provide the SQL commands used to retrieve data from [StackExchange Data Dump Explorer](https://data.stackexchange.com/help). Specifically from [AskUbuntu](https://askubuntu.com/) and [Unix and Linux](https://unix.stackexchange.com/).

[Data](https://drive.google.com/drive/folders/1BGcCoJ48bwVv_mYgzEGTn08cNh2dp1o6?usp=sharing) folder has all the intermediate data files and also the final dataset.

The files Dataframe_Linux.csv and Dataframe_AskUbuntu.csv under the Data folder linked above are the results obtained from the above queries. 

[download_answers.ipynb](https://github.com/madhurimamandal/Natural-Language-to-Bash-Commands-Parallel-Corpus/blob/main/download_answers.ipynb) is used to download answers form stackexchange by sending http get requests, according to Ids obtained above in Dataframe_Linux.csv and Dataframe_AskUbuntu.csv files. These are dumped using pickle into files posts_from_unix.txt and posts_from_askubuntu.txt, located under Data folder.

Then the obtained answers are filtered according to various rules, using [Filter_Dataframe_AskUbuntu.ipynb](https://github.com/madhurimamandal/Natural-Language-to-Bash-Commands-Parallel-Corpus/blob/main/Filter_Dataframe_AskUbuntu.ipynb) and [Filter_Dataframe_Linux.ipynb](https://github.com/madhurimamandal/Natural-Language-to-Bash-Commands-Parallel-Corpus/blob/main/Filter_Dataframe_Linux.ipynb). The results are dumped into filtered1.txt and filtered2.txt files using pickle, located under Data folder.

The filtered answers further processed using [create_final.ipynb](https://github.com/madhurimamandal/Natural-Language-to-Bash-Commands-Parallel-Corpus/blob/main/create_final.ipynb).

The answers are further filtered depending on whether or not [bashlint](https://github.com/madhurimamandal/Natural-Language-to-Bash-Commands-Parallel-Corpus/tree/main/bashlint) parser can parse them. This parser can only parse single line bash commands in correct format. This is used to convert the commands into a standard template form. This code is available in [parse_and_filter.ipynb](https://github.com/madhurimamandal/Natural-Language-to-Bash-Commands-Parallel-Corpus/blob/main/parse_and_filter.ipynb). Bashlint parser is obtained from [IBM/clai](https://github.com/IBM/clai/tree/nlc2cmd) repository, available under utils, [here](https://github.com/IBM/clai/tree/nlc2cmd/utils/bashlint).

Now Dataset.csv file under Data folder containes the final clean corpus containing 10,260 natural language and bash code pairs, which is close to corpus provided by [IBM nlc2cmd competition](https://github.com//TellinaTool//nl2bash) providing 9,305 pairs. Both the corpuses can be mixed as a possible corpus for code generation task. Dataset_multiple.csv under Data folder contains a noisy version of this data, with multiple code lines per natural language description.

The natural language descriptions can be tokenized simply by whitespace or by subword and fed to code generation model. [Tokenizer](https://github.com/IBM/clai/blob/2ad172acbed0c1ec870cc39f47635adea39f19c0/utils/bashlint/data_tools.py#L46) for bash is provided by [IBM/clai](https://github.com/IBM/clai/tree/nlc2cmd) repository which can be used to tokenize the bash commands to supervise the above task.
