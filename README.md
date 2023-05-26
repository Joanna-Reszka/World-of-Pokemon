# World-of-Pokemon

## What can we learn by looking at pokemon data?
#### An exploratory data analysis of dataset from Kaggle:
https://www.kaggle.com/datasets/rounakbanik/pokemon
<br />
#### Team project at Data Science bootcamp at InfoShare Academy 
https://github.com/infoshareacademy/jdszr12-databenders

## Introduction



## Dataset

#### The dataset consistsof 1 table with 801 records and 40 columns. 7 were excluded from further analysis as irrelevant ('abilities', 'base eggs steps', 'base happieness', 'classification', 'japanese name', 'percentage male' and 'pokedox number'). The 'name' column with a name of each pokemon was used as an index.The following 18 columns contain a multiplier used to calculate the damage given pokemon will take in a combat against certain type of attack, which will be most probably given by attacking pokemon of certain type. So for example water pokemon will be more resistant to fire type of attack than for example electric type of attack. Next group of columns is related to combat statistics such as 'attack', 'defense', 'special attack', 'special defense', 'speed' (attack speed), 'hp' (hit points) and 'base total' (the summary of basic combat statistics). Column 'capture rate' describes how hard or easy it is to catch certain pokemon and 'experience growth' describes how fast pokemon can gain experience. The remaining columns describe parameters such as 'height', 'weight', 'generation' the pokemon was released and if it belongs or not to 'legendary' pokemon. Two very important columns are 'type 1' and 'type 2', type one describes primary type of pokemon, and type 2 secondary type of pokemon. There are 18 types of pokemon. Some pokemon are only single typed and some double typed, and combination of types can help in lowering the risk of damage by certain combination of multipliers. 

## Data cleaning, preparation and transformation

#### Most missing values (384) were present at "type2" column, because many pokemon are only of single type, the missing valueswere replaced with "None". Remaining two columns with missing values were "Height_m" and "Weight_kg", and 20 missing values are for the same pokemon for both columns. They were replaced with median weight and height for given type. 
#### In order to obtain one column with each type for each pokemon dataframe was transformeed by duplicating each row and replacing duplicated "type1" value with "type2" value. This allowed for grouping values of combat statistics such as "base_total", "attack", "defence", "speed", "hit_points", "capture_rate", "Weight", "height" by type.

## Questions

#### Through the analysis of this dataset we want to shed light on the following issues:

#### 1. Generations, types and combat statistics frequency distributions (histograms and barplots)
##### -   Are pokemon evenly distributed across generations?
##### -   Are pokemon evenly distributed across types?
##### -   What is the frequency distribution of all combat statistics and other relevant features?
#### 2. Best types at certain combat statistics (boxplots):
##### -   how much better are legendary pokemon from non legendary pokemon??
##### -   what are the best types at attack, defense, attack speed, hit points?
##### -   are the best types at combat statistics the same for both legendary and non legendary pokemon?
##### -   is between type variation bigger than within type variation for most combat statistics?
#### 3. Feature correlations (scatterplots, heatmaps and clusterplot):
##### -   how strong are the correlations between features?
##### -   which features are correlated?
##### -   how do pokemon types cluster together based on median of combat statistics and other features?
#### 4. Balanced or specialised (stacked barplots and spiderplots with plotly):
##### -   are there different types of strategies among pokemon?
##### -   what is the distribution of those strategies among poluplation?
#### -   are some strategies more frequent in some types than others?
#### 5.  Examples of 4 strongest and 4 weakest pokemon  (spiderplots with plotly)
<br />  

## Insights from the exploratory data analysys 
###
### 1. Generations, types and combat statistics frequency distributions:


![image](https://github.com/Joanna-Reszka/World-of-Pokemon/assets/97312220/7a721e6a-e11c-49d3-a5c5-1b583ea8d0b4)

#### Almost 60 % of pokemon come from first, fifth and third generation, and only 20 % of pokemon come from sixth and seventh generation.

![image](https://github.com/Joanna-Reszka/World-of-Pokemon/assets/97312220/af328ac4-dfc7-40a7-a21e-4273dc9e3df4)

#### The proportion of single type versus double type pokemon is balanced, 52%  of pokemon are double typed and 48% are single type.

![image](https://github.com/Joanna-Reszka/World-of-Pokemon/assets/97312220/465e4ce6-c47d-4c09-a08d-1e56f9c1ee1b)

#### Most frequent types are *Water*, *Normal*, *Grass* and *Flying*. The least frequent types are *Ice*, *Ghost* and *Dragon*.



Frequency distribution of pokemon by primary and secondary type with distinction between 7 generations 

![obraz](https://github.com/Joanna-Reszka/World-of-Pokemon/assets/97312220/758cf2f9-76b2-446c-b395-0406967d4f4d)

#### Some pokemon types have equal representaion in primary and secondary types (*Poison*, *Ground*, *Dark*, *Fighting*) while others are dispropotionally more frequent in primary or secondary type (*Normal*, *Bug*, *Flying*, *Fairy*).The most frequent primary types are *Water*, *Normal*, *Grass*, and *Bug* while the rarest primary type is *Flying*. The most frequent secondary type is *Flying* and the rarest secondary types are *Normal* and *Bug*

#### Looking at the combat statistics distribution it is interesting to include the distinction between legendary and non legendary pokemon, since legendary pokemon (that constitute 9,44% of all pokemon) are usually the strongest with best combat statistics. 

![image](https://github.com/Joanna-Reszka/World-of-Pokemon/assets/97312220/1934bab2-3234-44f1-91e0-4a10423798d7)

#### Most of combat statistics have continous, bell- resembling but right skewed distributions, with exception of "base_total" which seems to be bimodal, and "capture_rate" which has non continous but sequential step values of capture rate. Indeed as expected, the central tendency for legendary pokemon is shifted to the right for most combat statistics and to the left in case of 'capture rate', since legendary pokemon are harder to catch with extremely low capture rates.

![image](https://github.com/Joanna-Reszka/World-of-Pokemon/assets/97312220/503c653a-a3a3-4f7c-affe-fd6c3f5aae79)

#### Weight and height are heavily right skewed with few extreme values on the right. Legendary pokemon seem to be enerally bigger (taller and heavier)

### 2. Best types at certain combat statistics

![image](https://github.com/Joanna-Reszka/World-of-Pokemon/assets/97312220/7069f118-99f7-48a1-bdd0-30f82e38945a)

#### Comparing median values of combat statistics by type for all pokemon (without discerning by legendary and non legendary pokemon) we can see strongest and weakest types at each combat statistic. *Dragon* and *Ice* seem to have consistently high values of combat statistics, while *Bug* seem to have consistenly low values of combat statistics. Other types seem to have some values of combat statistics much higher that others, for example *Steel* and *Rock* have high values of **Defense** and **Attack** and lower values of remaining statistics, while *Fighting* type has much higher value of **Attack** than remaining statistics

### Looking at between and within type variance for combat statistics and other features with distinction on legendary and non legendary pokemon:
![image](https://github.com/Joanna-Reszka/World-of-Pokemon/assets/97312220/b96f450f-2c16-4652-a69d-a77a8f8df574)

![image](https://github.com/Joanna-Reszka/World-of-Pokemon/assets/97312220/de430c3e-9ea3-4251-a4a3-2dc70f5eea27)

![image](https://github.com/Joanna-Reszka/World-of-Pokemon/assets/97312220/635bbed5-095c-431d-aaea-f73f3302a51d)

#### For most types legendary pokemon have significantly higher values of combat statistics, lower values of capture rate and bigger size (weight and hight), so while looking at best types at certain combat statistics it is important to discern between legendary and non-legendary pokemon


### **Attack** and **Defense** by type for non legendary and legendary pokemon
![image](https://github.com/Joanna-Reszka/World-of-Pokemon/assets/97312220/966a1634-fd63-48f7-b711-4d8edb5bb824)

#### **Attack**: The strongest non legendary type is *Fighting* and the weakest by amost 50% is *Fairy*. The best legendary types are *Ground*, *Bug* and *Normal*, and almost three times weaker is *Poison*.
#### **Defense**: The strongest non legendary type are *Steel* and *Rock* by around 30% better than the rest. The best legendary types are *Ground*,*Steel*, *Fairy* and *Normal* and again around three times weaker is *Poison*. This is the first feature so far that we see the same type with highest values among legendary and non legendary types (*Steel*).

### **Special Attack** and **Special Defense** by type for non legendary and legendary pokemon
![image](https://github.com/Joanna-Reszka/World-of-Pokemon/assets/97312220/856dda5d-e59c-4eb7-bacd-1101d85c5e96)

#### **Special Attack**: The strongest non legendary type are *Electric* , *Fire*, *Psychic* and *Ghost*, and the weakest by around 30% - *Ground* and *Bug*. The best legendary types are *Dragon* and *Ghost* while the weakest by almost 100% are *Normal* and *Grass*.
#### **Special Defense**: There is much higher within than between type variation for non legendary pokemon for this feature, while opposite is true for legendary pokemon.The best at **Special Defense** are *Poison* and *Ice* and the worst (about 2 x weaker) is *Bug*

### **Attack Speed** and **Hit Points** by type for non legendary and legendary pokemon
![image](https://github.com/Joanna-Reszka/World-of-Pokemon/assets/97312220/5a50fbd5-db51-4519-8a49-fbaa14c30b16)

#### **Speed** (Attack speed): The fastest attackin non legendary type is *Flying* that attacks almost 50% faster that the slowest attacking non legendary type- *Rock*.  at **Special Defense** are *Poison* and *Ice* and the worst (about 2 x weaker) is *Bug*
#### **HP** (Hit Points): There is much higher within than between type variation for non legendary pokemon for this feature and most of median values are within same range, while opposite is true for legendary pokemon. The types with highest **HP** are  *Ghost* and *Dark* and the lowest (about 2 x) is *Fairy*

### **Base Total** and **Capture Rate** by type for non legendary and legendary pokemon
![image](https://github.com/Joanna-Reszka/World-of-Pokemon/assets/97312220/9cb36025-fc75-4e8c-8c80-7bf81a7fd21e)

#### **Base Total**(summary of other combat statistics):  There is much higher within than between type variation for non legendary pokemon for this feature. Most legendary pokemon have similar value of median and only four types stand out with much higher **Base Total** namely *Ground*, *Dragon*, *Ghost* and *Normal*
#### **Capture Rate**(how easy it is to catch the pokemon, higher value translates to easy catch):  Again, for most non legendary types there is much higher within than between type variation, but we can see that *Rock* as the easiest to catch is almost 2 x easier to catch than *Electric* or *Fairy*. Most legendary pokemon are extremely hard to catch with **Capture Rate** close to zero, with one exception of *Bug* type which has very high within type variance for this particular trait.

### **Weight** and **Height** by type for non legendary and legendary pokemon
![image](https://github.com/Joanna-Reszka/World-of-Pokemon/assets/97312220/4e95980f-eea3-4f2b-b2ec-2fc192cd57d5)

#### **Weight**:  There are types with higher and lower within type variance, and for most types there are extreme outliers present.The heaviest non legendary pokemon are *Ground*, *Steel*, *Rock*, *Dragon* and *Ice*, and *Fairy* is the lightest type. Among the legendary pokemon the heaviest types are *Dragon*, *Normal* and *Ground*, and the lightest *Grass*, *Psychic* and *Fairy*. This is the second feature so far that we see the same types with highest and lowest values among legendary and non legendary types.
#### **Height**: Again, there is much higher within than between type variation for non legendary pokemon for this feature,while opposite is true for legendary pokemon.The highest legendary pokemon types are *Dark*, *Dragon* and *Ghost* and the shortest (about 5 x shorter) are *Grass* and *Psychic*

### General insights

#### Clearly the variation between types for most of the combat statistics and other features is much higher in legendary than non legendary pokemon, except for **Capture rate** that is extremely low for all legendary pokemons, the only one with strong within type variation is *Bug*.The variation within types is usually much smaller for legendary pokemon, which can be explained by smaller group size (legendary pokemon constitute around 9% of all pokemon). The variation within types for non legendary pokemon is in most cases so high that it cancels out variation between types, especially for the features in which the median for almost all the types is almost equal, like **Height**, **Hit Points**, **Base Total** or **Special Defence**. Also comparing the same combat statistics and features between legendary and non legendary pokemons we can clearly see that the types with highest and lowest values are not the same ones as legendary types in most cases, which means that the pokemon type is generally a weak predictor of certain statistics unless a discrimination for legendary and non legendary pokemons will be included.
    
### 3. Feature correlations

### **Base Total** against other features
![image](https://github.com/Joanna-Reszka/World-of-Pokemon/assets/97312220/a35c35b9-1e94-40fd-8418-620a7b5c078d)

### **Attack** against other features
![image](https://github.com/Joanna-Reszka/World-of-Pokemon/assets/97312220/7825fc55-a564-476a-b8b5-71331c63e1f5)
### Feature correlations
![image](https://github.com/Joanna-Reszka/World-of-Pokemon/assets/97312220/3224ea22-b5a4-4f47-a2ee-b6709aa00294)

#### Obviously **Base Total** as a feature calculated as sum of other combat statistics will be strongly to moderately correlated with **Attack**, **Special Attack**, **Defense**, **Special Defense**, **Hit Points** and **Speed**. It is also strongly negatively correlated with **Capture Rate** meaning the higher **Base Total** value the harder the pokemon will be to catch.
#### The remaining combat statistics and features are weakly to mildly correlated, with only exception of quite expected strong correlation between weight and height.
### Type clustering by medians of features
![image](https://github.com/Joanna-Reszka/World-of-Pokemon/assets/97312220/3c9f98d5-31d2-4e10-942f-339ab30deb6e)

#### Pokemon cluster in 3 groups:
-  First group consisting of *Steel*, *Rock*, *Fighting*, *Dark* and *Dragon* with higher **Weight**, strong **Attack** and **Defense** and low **Capture Rate**
-  Second group consisting of *Flying*, *Fire*, *Electric*, *Psychic*, *Ghost* and *Fairy* with low **Weight**, strong **Special Attack** and **Special Defense**
-  Third group consisting of *Water*, *Ice*, *Grass*, *Ground*, *Poison*, *Bug* and *Normal*   with high **Capture Rate** and low **Defense**


### 4. Balanced or specialised?
#### By balanced we mean more or less equal distribution of combat statistics values, and specialized would mean disproportionate distribution of combat statistics values.

#### The 6 combat statistics values were normalized to 0-100 scale and than for each pokemon the difference between max and min value of all 6 statistics was calculated as difference "diff". This is the frequency distribution histogram for the calculated difference including distinction on legendary and non legendary pokemon:
![image](https://github.com/Joanna-Reszka/World-of-Pokemon/assets/97312220/1157cfe0-06fd-4eb7-9d05-26dd1c40d5a0)

#### Than one of five strategies was assigned to each pokemon based on the value of difference such that:
-  **Strongly balanced**  less than 15
-  **Balanced** between 15-25
-  **Mixed**  between 25-45
-  **Specialist** between 45-65,
-  **Extreme Specialist** between 65-100
-  
### Frequency of each strategy in pokemon population with distinction on legendary and non legendary pokemon
![image](https://github.com/Joanna-Reszka/World-of-Pokemon/assets/97312220/074a1539-67ca-41a5-bc33-4d0bffd67091)
#### It seems that there is a slight shift towards **generally balanced strategy** in *non legendary pokemon* (32% in total of 8% strongly balanced and 24% balanced) compared to *legendary pokemon* (16% balanced in total of 2% strongly balanced and 14% balanced). It also seems that there is a slight shift towards **generally specialist strategy** in *legendary pokemon* (30% in total of 20% specialist and 10% of extreme specialist) compared to *non legendary pokemon* (17% in total of 15 % specialist and 2% of extreme specialist). This might be due to generally higher combat statistic values in legendary pokemon- maybe with high combat statistics one can afford to be highly specialized?

### Proportion of each strategy in each type
![image](https://github.com/Joanna-Reszka/World-of-Pokemon/assets/97312220/921f6c1f-e4e2-4cab-8a3a-6560f38375c0)
#### Although there are no types with only one dominant strategy and all strategies are present in most of the types with different proportions. **Generally balanced strategy** seem to be dominant in * Grass* and *Water* types and quite substantial in *Bug*, *Fairy*, *Poison* and *Psychic*. The types with high proportion of **Generally specialist strategy** are *Rock*, *Steel* and *Fighting*.
-  **Strongly balanced** seems to be more frequent in types with generally lower combat statistics like *Ice*, *Fairy*, *Grass*, and *Water*, and completly absent in *Steel*, *Fire* and *Electric*.
-  **Balanced**  seems to be more frequent again in *Water*, *Grass*, as well as *Poison* and *Bug*.
-  **Mixed** is the most frequent strategy in all types, but especially dominant in *Electric* and *Dark*, and least frequent in *Ice*
-  **Specialist** seems to be most frequent in *Fighting* and *Rock* types, that have generally high values of either **Attack** or **Defense** combat statistics. It is least frequent in *Grass*, *Poison* and *Normal* - again types with generally lower combat statistis.
-  **Extreme Specialist** seems to be most frequent in *Steel* and *Rock* types which have high **Defense** statistics (so we can observe an example of an extreme specialist in **Defense**), and suprisingly also in *Bug* - which is the example of an extreme specialist in **Attack**. This strategy is least frequent in *Fire* - completely absent as well as the types with generally low combat statistics such as *Water*, *Grass*, *Poison*, *Ground* as well as *Flying*.

#### Chosen examples of 5 strategies:
![image](https://github.com/Joanna-Reszka/World-of-Pokemon/assets/97312220/21f6a071-9e43-49c4-a6f6-b6bfe4f8ea8a)

### 5.  Examples of 4 strongest and 4 weakest pokemon 
![image](https://github.com/Joanna-Reszka/World-of-Pokemon/assets/97312220/4a345dc2-92d9-4136-8bbe-258d8b9dcc74)
![image](https://github.com/Joanna-Reszka/World-of-Pokemon/assets/97312220/eb7b9990-18d6-4b55-a957-de134c692bcc)

## Conclusions and reccomendations

#### The fascinating world of pokemon has revealed some of its secrets, but it would be interesting to check how the different strategies (balanced versus specialised) translate to combat skills, resiliancy and attack resistance.
