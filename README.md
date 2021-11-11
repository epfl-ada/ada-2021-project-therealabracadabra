# MILESTONE 2

What we should do:
That you can handle the data in its size.\
That you understand what’s in the data (formats, distributions, missing values, correlations, etc.).\
That you considered ways to enrich, filter, transform the data according to your needs.\
That you have a reasonable plan and ideas for methods you’re going to use, giving their essential mathematical details in the notebook.\
That your plan for analysis and communication is reasonable and sound, potentially discussing alternatives to your choices that you considered but dropped.

### Abstract

This project aims at studying the political affiliation of some newspapers based on the dataset set given from 2015 to 2020. The main idea is to choose some newspapers that have a known and clear positioning and then study some “key parameters” through the dataset to check if they support or correlate with our statement (political affiliation). The parameters would have to be defined from the beginning according to the journal’s beliefs. The objective being to analyse which parameters (linguistic differences, topics spoken about, personalities cited, …) would allow to make a difference between them. Once a link is made between the “parameters” and the newspaper positioning, a second goal would be to iterate this work on other journals, less known or not, and see if we could state their political affiliation. Thus, the idea is to realize a clear framework that would allow to compare newspapers and state their political affiliation.

### Research questions

Many questions have to be studied before defining the method. First, some journals have “centered” opinions or shaded positioning. That is why, the focus will be made on polarized newspapers, which will make it easier to study and define the parameters. 

A first question would be: What are the main topics on which the newspaper diverge and do not agree? This one would have to be checked upstream, and then further developed using the dataset. 

A second one would be to make a sentimental analysis of the quotations used in the newspapers and observe if there is any clear difference depending on the political affiliation. A [paper](https://engineering.stanford.edu/magazine/article/what-different-about-how-democrats-and-republicans-talk-online) analyzing the differences between both parties, which had studied tweets from Republicans and Democrats, showed that both don’t use the same sentiments when discussing about guns shooting and also depending on the shooter race.

A third research question would be to verify whether or not the newspapers cite more public figures which share their opinions.
Another questions would be to study if there is any linguistic difference between the newspapers. As in this study about computational linguistics, which showed that Democrats use more modal verbs compared to Republicans to call for action.

Another question would be to verify if our study which will be based only on quotations is accurate or not.

### Methods

For this milestone, two medias have been chosen: Foxnews and The New York Times. Both are polarized, Foxnews is in favor of more conservative political positions and is mainly viewed by Republican partisans (figure below) while [NYT is more left-leaning](https://www.influencewatch.org/for-profit/new-york-times/) and followed mainly by Democrats (figure below).
![alt text](<a href="https://www.statista.com/chart/21328/party-affiliation-by-news-source/" title="Infographic: Party Affiliation Defines News Sources | Statista"><img src="https://cdn.statcdn.com/Infographic/images/normal/21328.jpeg" alt="Infographic: Party Affiliation Defines News Sources | Statista" width="50%" height="auto" style="width: 50%; height: auto !important; max-width:960px;-ms-interpolation-mode: bicubic;"/>)

First of all, the data has to be wrangled. A check-up has to be made, to clean the dataset and remove any anomaly. Lines containing NaN or 0 had been removed as well as duplicates…. (COMPLETE MANU) A new column with the journal name should be added, because the raw data only has the website URL, and this will make it simpler to process the data.
Once these modifications are made, we can start analysing it.
We will first analyse how many quotations are from Republicans and how many from Democrats. To do so,. we will use two different sets, one set with Republicans names and one with Democrats names.

We will also focus on 5 subjects on which Democrats and Republicans seem to disagree on. With an appropriate key word lexic for each to follow:
•	Immigration: “immigration”, “wall”, “mexic”
•	Terrorism/Gun control: “shoot”, “gun”, “kill”, “attack”, “massacre”, “victim”, “black”, “white”, “terroris”,”arm”
•	Climate change
•	Abortion
•	Religion: “God”, “Christian”, “Christianism”
The idea would be to analyse if there is a significant difference in the used terms. Moreover, we would like to highlight the mostly used words by category and by year for both medias.

We also plan to make a sentimental analysis on the newspapers. The emotions categories would be defined as follow: disgust, fear, trust, anger, sadness, positive, negative. The key words for each category will be taken from the annex from the table E of the paper ["Analyzing Polarization in Social Media: Method and Application to Tweets on 21 Mass Shootings"](https://github.com/ddemszky/framing-twitter/blob/master/paper/ddemszky2019analyzing.pdf).

We also would like to see the probability of occurrence of the term “chloroquine” for both journals. As this treatment against Covid-19 is very controversial. Indeed, many researchers came to the conclusion that there is [no scientific evidence about its efficiency](https://www.rts.ch/info/sciences-tech/medecine/11345309-la-chloroquine-augmenterait-le-taux-de-mortalite-des-malades-du-covid.html), while other supports Doctor Didier Raoult and say that it  is a lie.

(Following this paper results, we could also study the difference in the use of modal verbs and check whether our results are in concordance with the paper which had concluded that modal verbs are mostly used by Democrats)

