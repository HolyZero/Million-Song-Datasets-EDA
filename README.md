# A Million Song Dataset
Ziyue JIN, Ziyue WU, Yimin ZHANG, Jingying ZHOU and Yibo ZHU
 
#[To view our full report please click here! ](https://zac2116.github.io/)

## Data
##### Source 1. Sound Analysis
* [Million Song Dataset](http://labrosa.ee.columbia.edu/millionsong/)
* Format: .h5 [Hierarchical Data Format](https://en.wikipedia.org/wiki/Hierarchical_Data_Format)  
* How we utilized our data:   
1) Made exploratory data analysis on the metadata for all 1,000,000 songs (Meta Data: 300 MB)  
2) Extracted sound analysis data from a random subset, consiting of 10,000 songs (Sound Analysis: 1.8 GB)  
          - Temporal structures: eg.beats/bar lengths distribution  
          - Loudness, timbre and pitches  
*A brief glimpse of all the blood and tears we've been through...*
```
          group                       name       otype   dclass       dim
0             /                   analysis   H5I_GROUP                   
1     /analysis            bars_confidence H5I_DATASET    FLOAT       194
2     /analysis                 bars_start H5I_DATASET    FLOAT       194
3     /analysis           beats_confidence H5I_DATASET    FLOAT       979
      ...         ...         ...         ...         ...
21    /metadata            similar_artists H5I_DATASET   STRING       100
22    /metadata                      songs H5I_DATASET COMPOUND         1
23            /                musicbrainz   H5I_GROUP                   
24 /musicbrainz              artist_mbtags H5I_DATASET   STRING         0
25 /musicbrainz        artist_mbtags_count H5I_DATASET  INTEGER         0
26 /musicbrainz                      songs H5I_DATASET COMPOUND         1

```
##### Source 2. User Preference
* [Echo Nest Tase Profile Data](The Echo Nest Taste Profile Subset)
* Format: Play count per song per user:
* How we utilized our data:  
We used this play-count data to generate a "user defined" song similiarity mesure, and then tried random forest and LASSO to select the sound features (from dataset 1) that play the most important roles in determining thi

##### Source 3. Lyrics Bag-of-Words
* Source: [musiXmatch dataset](http://labrosa.ee.columbia.edu/millionsong/musixmatch)
* Format:.db(BoW)
* How we utilized our data:   
We implemented a topic model using Laten Dirichlet Allocation with 10 and 15 topics. This cluster is generated purely independently from the rest of the clusters, and we would like to see if the clusters generated from the sound features are indeed "literally" different from each other.

##### Source 4. Genre
* [Tagtraum Genre Annotations](http://www.tagtraum.com/msd_genre_datasets.html)
* Format: .cls 
* How we utilized... Fancy Plots!

## Methodology
#### To make a long story short,  
* We clustered our songs based purely on the song features
* Using the lyrics Bag-of-Words data, we did topic modelling and looked into how these two cluster results differ/resembles each other!
* Lastly, We used playcount data to select song features that play an important role in deciding the "crowd defined similarity", we then clustered our songs again using only the selected sound features
Based on the results we made our conclustion.

#[To view our full report please click here! ](https://zac2116.github.io/)

