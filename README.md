# Are you a Democrat or a Republican newspapers reader ?

[Link to our datastory](https://mmettler21.github.io/political_analysis/)

# Abstract

This project aims at studying the political affiliation of some newspapers based on the dataset set given from 2015 to 2020. The main idea is to choose some newspapers that have a known and clear positioning and then study some “key parameters” through the dataset to check if they support or correlate with our statement (political affiliation). The parameters would have to be defined from the beginning according to the journal’s beliefs. The objective being to analyse which parameters (linguistic differences, topics spoken about, personalities cited, …) would allow to make a difference between them. Once a link is made between “parameters” and newspaper positioning, a second goal would be to repeat this work on other journals, less known or not, and see if we could determine their political affiliation. Thus, the idea is to produce a clear framework that would allow to compare newspapers and state their political affiliation.

# Research questions

- How quotations could reflect the main topics/ points on which newspapers diverge and do not agree.
- Does speakers reflect newspaper political affiliation?
- How do both journals speak about common subjects and events in terms of sentiment and emotions?
- Can we indentify other newspapers political beliefs using the Quote bank data base?

# Methods
First, some journals have “centered” opinions or shaded positioning. That is why, the focus will be made on polarized newspapers, which will make it easier to study and define the parameters
Two medias have been chosen: Foxnews and New York Times. Both are polarized, Foxnews is in favor of more conservative political positions and is mainly viewed by Republican partisans while [NYT is more left-leaning](https://www.influencewatch.org/for-profit/new-york-times/) and followed mainly by Democrats (figure below).

<a href="https://www.statista.com/chart/21328/party-affiliation-by-news-source/" title="Infographic: Party Affiliation Defines News Sources | Statista"><img src="https://cdn.statcdn.com/Infographic/images/normal/21328.jpeg" alt="Infographic: Party Affiliation Defines News Sources | Statista" width="50%" height="auto" align="center" style="width: 50%; height: auto !important; max-width:960px;-ms-interpolation-mode: bicubic;"/></a>.

The steps are described below. Note that several probalistic tests (t test for example) have been applied.

## Wrangling and reading the dataset
Concerning the reading of the data, our first approach was to read the dataset using chunks and then to generate a single pickle file from these chunks. 
The problem was that reading the chunks one after the other from the pickle file generated an extremely heavy file (the operation was stopped when the file size 
exceeded 150 Gigabytes!).
Consequently, an alternative was proposed : the approach was to only keep the two journals data of interest and to save one pickle per chunk. All these pickle files have been saved by year. Then, we also saved lists of quotations for each newspaper we were interested in by year.

## Topic detection and common nouns
For each News paper we used Latent Dirichlet Allocation (LDA) which is an unsupervised method and by specifying the number of topics returns a set of word for each topic. The document, so in our case the quotations of each journal has to be modified into bag of words and the each topic is a probability distribution over words. First, we determined the ideal number of topics for the newspaper, by using a coherence model and iterating over different number of topics (from 2 to 10). Then we have taken the number which corresponds to the highest score and we have plot the topics using PyLDAvis. This has been made in the Topic_detection.ipynb file.
The 30 most used nouns in both journals have been generated using the Analyse 1.ipynb file and have been saved. 

## Subjects occurance
Quotations about some specific subjects have been counted for each journal, a t-test has been applied to see if the difference is significant or not.

•	**Immigration**: “immigration”, “mexic”, "migrant","border","refugees"

•	**Terrorism/Gun control**: “shoot”, “gun”, “kill”, “attack”, “massacre”, “victim”, “terroris”,”arm”,"violen","death"

•	**Climate change** : "flood", "greenhouse effect", "CO2", "global warming","pollution","glacier","ice pake melting","high temperatures", "heat"

•	**Abortion**: "abort", "fetus"

•	**Religion**: “God”, “Christian”, “Christianism”, "Belief", "faith", "prayer", "commitment","islam","buddhism","hinduism","baptism","church","vatican","reincarnation", "jesus"

•	**Racism**: "White", "Black", "Black lives matter", "All lives matter", "discrimination","Segregation","George Floyd","Slaver","White supremacy","Klu Klux Klan","KKK","Gunshot","Trials","Police","Death sentence"

• **covid”**: "covid", "corona", "pandem", "vaccine", "chloroquine", "virus".

## Sentiment analysis
A general sentiment analysis has been made for both newspapers for each year. An emotion analysis has also been made for each subject described above. 
Multiple notebooks have been made because the processing is very long, especially for the text2emotion library, so it helps doing it simultaneously. 
The first type of notebook is comprised of: 2015_2016_2017.ipynb, 2018.ipynb, 2019.ipynb, 2020+graphics.ipynb. On these notebooks the average value for sentiments and emotions by year, by journal is calculated. It was the initial work on the sentiment analysis, to see if it was relevant to continue working on it.
The second type of notebook for the sentiment analysis is compriised of: sent_nltk_by_subject_V2.ipynb, sent_text2_by_subject_V2.ipynb, NLTK_Pvalue_yby.ipynb. This is the continuation of the first part. These contain a sentiment analysis for certain subjects such as immigration and religion. The main difference is that T-test are done on these three notebooks to establish the statiscal significance.
And lastly the Washington_Post.ipynb is a notebook where various types of sentiment analysis done in previous notebooks are done on the third journal, and a comparison with the two other journals with some graphics is also present.

## Verification
At the end, the “parameters” which significantly allow to make the difference between the two journals are applied on a third newspaper. We have chosen the Washington post which has a [lean left bias] (https://www.allsides.com/news-source/washington-post-media-bias) as NY times.

# Proposed timeline and organization within the team
Timeline:
- 29/11 - 5/12: Build all files that will be used for the analysis.
- 26/12 - 12/12: Apply the methods given below and calculate the tests of probabilities.
- 12/12 - 17/12: Plot the graphs and apply the relevant methods on a 3rd newspaper.

Organization:
- François Charroin: Sentiment and emotion analysis
- Manuela Maia: Filtering and creation of new files. Speakers and subjects occurences by years. Sentiment for covid-19 over 2020. 
- Marc Mettler: Website and datastory.
- Sinda M'Saada: Quotations pickle files creation, topic detection and common nouns.

## Files
- Readng_the_Big_Data.ipynb is the code that reads the chunks and saves the data as pickles. It is also where a filtering check is done. 
- Quotes_Analysis_AllYears.ipynb is the code that looks at the number of quotes per topic and for all years. It is also where the number of quotes for democrats and republicans is analysed.
- Yearly_Quotes_Analysis.ipynb is the code that analysis all quotations realted to Fox News and New York Times by year for specific topics. It looks to the number of quotes.
- Covid_Sentiment_Analysis.ipynb is the code of sentiment analysis for the covid topic. 

# Website
[Link to our datastory](https://mmettler21.github.io/political_analysis/)
