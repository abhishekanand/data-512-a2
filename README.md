### A2: Bias in data (Explore the concept of 'bias' through data on Wikipedia articles - specifically, articles on political figures from a variety of countries.)


### Data Source & License
1. Generated using Wikimedia Foundation API and distributed on Figshare under [CC-BY-SA 4.0 license]
  * Source Location  : [Politicians by Country from the English-language Wikipedia](https://figshare.com/articles/Untitled_Item/5513449)
 * Local Copy  : [Raw Data](https://github.com/abhishekanand/data-512-a2/blob/master/rawdata/country.zip)
 * File  Name : [page_data.csv](https://github.com/abhishekanand/data-512-a2/blob/master/page_data.csv)

2. The population data [Population Research Bureau website](http://www.prb.org/DataFinder/Topic/Rankings.aspx?ind=14)
 * Source : [Population Research Bureau website](http://www.prb.org/DataFinder/Topic/Rankings.aspx?ind=14)
 * Local Copy : [Raw](https://github.com/abhishekanand/data-512-a2/blob/master/Population%20Mid-2015.csv)

Note  : No License detail present . Please refer datasheet](http://www.prb.org/wpds/2015/) for more details on use and source .

3. Article quality predictions data set collected using a Wikimedia API endpoint for a machine learning system called ORES ("Objective Revision Evaluation Service").
 * API Details : https://ores.wikimedia.org/v3/#!/scoring/get_v3_scores_context_revid_model

Data collected from [Wikimedia Foundation](https://en.wikipedia.org/wiki/Wikimedia_Foundation) is [licensed](https://en.wikipedia.org/wiki/Wikimedia_Foundation#Projects_and_initiatives) for redistribution under [v3.0](https://creativecommons.org/licenses/by/3.0/) .


###  Data descriptions

#### 1.Politicians by Country from the English-language Wikipedia
File  : page_data.csv
  * "country", containing the sanitised country name, extracted from the category name;
  * "page", containing the unsanitised page title.
  *  "last_edit", containing the edit ID of the last edit to the page.

page,country,rev_id
Template:ZambiaProvincialMinisters,Zambia,235107991

 #### 2.The population data
 File :Population Mid-2015.csv
  * Location : Contains Country Name
  * Location Type : Location Classifier  (Country)
  * TimeFrame  : Mid -2015
  * Data Type : Data Classifier (Number )
  * Data : Population   
  * Footnotes : --

Location,Location Type,TimeFrame,Data Type,Data,Footnotes
Afghanistan,Country,Mid-2015,Number,"32,247,000",

#### 3.Articles Quality

ORES assigns a series of probabilities that the article is in one of 6 quality categories. The options are, from best to worst:

FA - Featured article
GA - Good article
B - B-class article
C - C-class article
Start - Start-class article
Stub - Stub-class article

~~~~
  "757539710": {
                "wp10": {
                    "score": {
                        "prediction": "Start",
                        "probability": {
                            "B": 0.0950995993086368,
                            "C": 0.1709859524092081,
                            "FA": 0.002534267983331672,
                            "GA": 0.005731369423122624,
                            "Start": 0.7091352495053856,
                            "Stub": 0.01651356137031511
                        }
                    }
                }
            },
~~~~

#### 4 . Final Data Set  
Created using above three data set .  
  *  country
  *   article_name
  *   revision_id
  *   article_quality
  *   population

Example:
country,article_name,revision_id,article_quality,population
Zambia,Template:ZambiaProvincialMinisters,235107991,Stub,15473900

NOTE : Final Dataset exclude all entries where we matching data was not available in both population and Article Count on Wikipedia.

### Tools Used  :

1. Jupyter Notebook (Python 3.X Anaconda Distribution)
2. Python  Libraries (CSV, Paadas, matplotlib)

### Analysis & Write Up


10 highest-ranked countries in terms of number of politician articles as a proportion of country population
~~~~
COUNTRY                          PROPORTION
-------------------------------------------
Andorra                           0.043590
Federated States of Micronesia    0.036893
Iceland                           0.062268
Liechtenstein                     0.077189
Marshall Islands                  0.067273
Monaco                            0.105020
Nauru                             0.488029
San Marino                        0.248485
Tonga                             0.060987
Tuvalu                            0.466102
~~~~


10 lowest-ranked countries in terms of number of politician articles as a proportion of country population
~~~~
COUNTRY              PROPORTION
--------------------------------
Bangladesh            0.000202
China                 0.000083
Congo Dem. Rep. of    0.000194
Ethiopia              0.000107
India                 0.000075
Indonesia             0.000084
Korea North           0.000156
Thailand              0.000172
Uzbekistan            0.000093
Zambia                0.000168
~~~~


10 highest-ranked countries in terms of number of GA and FA-quality articles as a proportion of all articles about politicians from that country
~~~~
COUNTRY                      Percentage
----------------------------------------
Abkhazia                     6.250000
Bhutan                       9.090909
Central African Republic     7.352941
Dominica                     8.333333
Gambia                       7.317073
Guinea-Bissau                9.523810
Korea North                 17.948718
Saudi Arabia                10.084034
South African Republic       6.666667
Uzbekistan                  10.344828
~~~~

10 lowest-ranked countries in terms of number of GA and FA-quality articles as a proportion of all articles about politicians from that country
~~~~
COUNTRY         Percentage
---------------------------
Czech Republic    0.393701
Hungary           0.488599
Italy             0.483092
Lithuania         0.403226
Mexico            0.462535
Morocco           0.480769
Norway            0.455927
Peru              0.282486
Serbia            0.454545
Tanzania          0.245098
~~~~


**Uzbekistan  and  North  Korea** are  present in both  10 lowest-ranked countries in terms of number of politician articles as a proportion of country population  10 highest-ranked countries in terms of number of GA and FA-quality articles as a proportion of all articles about politicians from that country .

Above outcome just focused on top 10 and bottom 10 . This data set has been collected from only English Wikipedia which undermines the effectiveness of Analysis on Global base.
