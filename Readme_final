
## Wrangling and reading the dataset
Concerning the reading of the data, our first approach was to read the dataset using chunks and then to generate a single pickle file from these chunks. 
The problem was that reading the chunks one after the other from the pickle file generated an extremely heavy file (the operation was stopped when the file size 
exceeded 150 Gigabytes!). Consequently, an alternative was proposed : the approach was to use only one chunk per pickle by reading the files of each year and combining 
them together. Then, we were able to generate a dataframe for each newspaper we were interested in, which whole quotations between 2015 and 2020.
