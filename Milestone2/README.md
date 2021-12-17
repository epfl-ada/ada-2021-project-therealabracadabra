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
Consequently, an alternative was proposed : the approach was to only keep the two journals data of interest and to save one pickle per chunk. All these pickle files have been saved by year in DATA/ADA_2021/.
Then, we also saved lists of quotations for each newspaper we were interested in by year in DATA/Quotations_Fox_NY/.

## Topic detection and common nouns
For each News paper we used Latent Dirichlet Allocation (LDA) which is an unsupervised method and by specifying the number of topics returns a set of word for each topic. The document, so in our case the quotations of each journal has to be modified into bag of words and the each topic is a probability distribution over words. First, we determined the ideal number of topics for the newspaper, by using a coherence model and iterating over different number of topics (from 2 to 10). Then we have taken the number which corresponds to the highest score and we have plot the topics using PyLDAvis.
The 30 most used nouns in both journals have been generated using the words.ipynb file and have been saved in the DATA/ folder. 

## Manu
We will also focus on several subjects on which Democrats and Republicans seem to disagree on. With an appropriate key word lexic for each to follow:

•	**Immigration**: “immigration”, “mexic”, "migrant","border","refugees"

•	**Terrorism/Gun control**: “shoot”, “gun”, “kill”, “attack”, “massacre”, “victim”, “terroris”,”arm”,"violen","death"

•	**Climate change** : "flood", "greenhouse effect", "CO2", "global warming","pollution","glacier","ice pake melting","high temperatures", "heat"

•	**Abortion**: "abort", "fetus"

•	**Religion**: “God”, “Christian”, “Christianism”, "Belief", "faith", "prayer", "commitment","islam","buddhism","hinduism","baptism","church","vatican","reincarnation", "jesus"

•	**Racism**: "White", "Black", "Black lives matter", "All lives matter", "discrimination","Segregation","George Floyd","Slaver","White supremacy","Klu Klux Klan","KKK","Gunshot","Trials","Police","Death sentence"

• **chloroquine”**

## Sentiment analysis
We also plan to make a **sentimental analysis** on the newspapers. The emotions categories would be defined as follow: disgust, fear, trust, anger, sadness, positive, negative. The key words for each category will be taken from the annex from the table E of the paper ["Analyzing Polarization in Social Media: Method and Application to Tweets on 21 Mass Shootings"](https://github.com/ddemszky/framing-twitter/blob/master/paper/ddemszky2019analyzing.pdf).

## Washington post
At the end, we will take the “parameters” which significantly allow to make the difference between the two journals and affiliate them to a political belonging. And we will iterate the process on other journals to determine their political affiliation.

# Proposed timeline and organization within the team
According to the homeworks and projects deliverables. We will have three/four weeks to work on the milestone 3. The work will be split as follow:

• Before the 26/11: Build all dataframes that will be used for the analysis.

• 29/11 - 5/12: Apply the methods given below: make the statistics, ... Begin the analysis of the results (graphs, tests of probability, ...) to select the parameters of interest.

• 6/12 - 12/12: Get the political affiliation of some other journals using the key parameters found.

• 13/12 - 16/12: Make better visualizations and put everything together in a article to facilitate the communication.

The work will be split according to members availability. Each week, a minimum of 2 members will have to work on the project.

# Website

