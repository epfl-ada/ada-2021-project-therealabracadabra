
## Wrangling and reading the dataset
Concerning the reading of the data, our first approach was to read the dataset using chunks and then to generate a single pickle file from these chunks. 
The problem was that reading the chunks one after the other from the pickle file generated an extremely heavy file (the operation was stopped when the file size 
exceeded 150 Gigabytes!).
Consequently, an alternative was proposed : the approach was to only keep the two journals data of interest and to save one pickle per chunk. All these pickle files have been saved by year in DATA/ADA_2021/.
Then, we also saved lists of quotations for each newspaper we were interested in by year in DATA/Quotations_Fox_NY/.

## Common nouns
The 30 most used nouns in both journals have been saved generated using the words.ipynb file and have been saved in the DATA/ folder. BLABLA

## Topic detection
For each News paper we used Latent Dirichlet Allocation (LDA) which is an unsupervised method and by specifying the number of topics returns a set of word for each topic. The document, so in our case the quotations of each journal has to be modified into bag of words and the each topic is a probability distribution over words. First, we determined the ideal number of topics for the newspaper, by using a coherence model and iterating over different number of topics (from 2 to 10). Then we have taken the number which corresponds to the highest score and we have plot the topics using PyLDAvis.
