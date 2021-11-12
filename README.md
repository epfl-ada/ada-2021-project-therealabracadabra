# MILESTONE 2

### Abstract

This project aims at studying the political affiliation of some newspapers based on the dataset set given from 2015 to 2020. The main idea is to choose some newspapers that have a known and clear positioning and then study some “key parameters” through the dataset to check if they support or correlate with our statement (political affiliation). The parameters would have to be defined from the beginning according to the journal’s beliefs. The objective being to analyse which parameters (linguistic differences, topics spoken about, personalities cited, …) would allow to make a difference between them. Once a link is made between the “parameters” and the newspaper positioning, a second goal would be to repeat this work on other journals, less known or not, and see if we could determine their political affiliation. Thus, the idea is to produce a clear framework that would allow to compare newspapers and state their political affiliation.

### Research questions

Many questions have to be studied before defining the method. First, some journals have “centered” opinions or shaded positioning. That is why, the focus will be made on polarized newspapers, which will make it easier to study and define the parameters. 

A first question would be: What are the main topics on which the newspaper diverge and do not agree? This one would have to be checked upstream, and then further developed using the dataset. 

A second one would be to make a sentimental analysis of the quotations used in the newspapers and observe if there's any clear difference depending on the political affiliation. This [paper](https://engineering.stanford.edu/magazine/article/what-different-about-how-democrats-and-republicans-talk-online) analyzing the differences between both parties, which had studied tweets from Republicans and Democrats, showed that both don’t use the same sentiments when discussing about guns shooting and also depending on the shooter race.

A third research question would be to verify whether or not the newspapers cite more public figures which share their opinions.
Another questions would be to study if there's any linguistic and semantic difference between the newspapers. As in this study about computational semantics of language, which showed that Democrats use more modal verbs compared to Republicans to call for action.

A fourth approach would be to determine the the importance of certain topics, depending on the political position of the journals. This would be done by looking at the percentage of quotes using a certain vocabulary. 

Another question would be to verify if our study which will be based only on quotations is accurate or not.

### Methods

For this milestone, two medias have been chosen: Foxnews and New York Times. Both are polarized, Foxnews is in favor of more conservative political positions and is mainly viewed by Republican partisans while [NYT is more left-leaning](https://www.influencewatch.org/for-profit/new-york-times/) and followed mainly by Democrats (figure below).

<a href="https://www.statista.com/chart/21328/party-affiliation-by-news-source/" title="Infographic: Party Affiliation Defines News Sources | Statista"><img src="https://cdn.statcdn.com/Infographic/images/normal/21328.jpeg" alt="Infographic: Party Affiliation Defines News Sources | Statista" width="50%" height="auto" align="center" style="width: 50%; height: auto !important; max-width:960px;-ms-interpolation-mode: bicubic;"/></a>

First of all, data has to be wrangled. A check-up has to be made, to clean the dataset and remove any anomaly. A new column with the journal name should be added, because the raw data only has the website URL, and this will make it simpler to process the data.

Once these modifications are made, we can start analysing it.

We will first analyse how many quotations are from Republicans and how many from Democrats. To do so, we will use two different sets, one set with Republicans names and one with Democrats names.

We will also focus on several subjects on which Democrats and Republicans seem to disagree on. With an appropriate key word lexic for each to follow:

•	**Immigration**: “immigration”, “mexic”, "migrant","border","refugees"

•	**Terrorism/Gun control**: “shoot”, “gun”, “kill”, “attack”, “massacre”, “victim”, “terroris”,”arm”,"violen","death"

•	**Climate change** : "flood", "greenhouse effect", "CO2", "global warming","pollution","glacier","ice pake melting","high temperatures", "heat"

•	**Abortion**: "abort", "fetus"

•	**Religion**: “God”, “Christian”, “Christianism”, "Belief", "faith", "prayer", "commitment","islam","buddhism","hinduism","baptism","church","vatican","reincarnation", "jesus"

•	**Racism**: "White", "Black", "Black lives matter", "All lives matter", "discrimination","Segregation","George Floyd","Slaver","White supremacy","Klu Klux Klan","KKK","Gunshot","Trials","Police","Death sentence"

• **chloroquine”**

The idea would be to analyse if there's a significant difference in the used terms. Moreover, we would like to highlight the mostly used words by category and by year for both medias.

We also plan to make a **sentimental analysis** on the newspapers. The emotions categories would be defined as follow: disgust, fear, trust, anger, sadness, positive, negative. The key words for each category will be taken from the annex from the table E of the paper ["Analyzing Polarization in Social Media: Method and Application to Tweets on 21 Mass Shootings"](https://github.com/ddemszky/framing-twitter/blob/master/paper/ddemszky2019analyzing.pdf).

Once all these steps made, we will have to apply a probalistic test (t test for example), to calculate the p-value and look if there's a significant difference between both medias for each topic. To determine wich indicators are the most powerful, we will use a PCA algorithm, it will also be a way to test all of our hypothesis.

At the end, we will take the “parameters” which significantly allow to make the difference between the two journals and affiliate them to a political belonging. And we will iterate the process on other journals to determine their political affiliation.

### Proposed timeline and organization within the team
According to the homeworks and projects deliverables. We will have three/four weeks to work on the milestone 3. The work will be split as follow:

• Before the 26/11: Build all dataframes that will be used for the analysis.

• 29/11 - 5/12: Apply the methods given below: make the statistics, ... Begin the analysis of the results (graphs, tests of probability, ...) to select the parameters of interest.

• 6/12 - 12/12: Get the political affiliation of some other journals using the key parameters found.

• 13/12 - 16/12: Make better visualizations and put everything together in a article to facilitate the communication.

The work will be split according to members availability. Each week, a minimum of 2 members will have to work on the project.

### Questions
How will we be sure that the factors founded will have the same impact on other journals? Will we have to select journals from the same country ? Or maybe try to treat the problem as an observational study and match the newspapers together as a function of their covariates?
