# Customer_segmentation.

### (unsupervised  machine learning modeling) 

![](https://github.com/evgenygrobov/Customer_clustering./blob/main/images/product-service-segmentation-28071896.jpg)


---

### Scenario:

Our client is an Insurance company that has provided Health Insurance to its customers now they want to expand line with  Vehicle Insurance products. For this reason existing cuatomers were surveyed about their potential interest in buying Vehicle insurance policy by the same company. Customer's response were collected and framed in single file. 
We were asked to provide segmentation amongst customers who showed an interest in buying the new product. The project we are working on will reveal simillarities and dissimillarities customers share in clusters they will be assigned to. Thus, our client will be able to better distinguish between customers profiles,  and biuld and conduct marketing campany more effictievly.  

---

## Data

The data was taken at Kaggle  https://www.kaggle.com/anmolkumar/health-insurance-cross-sell-prediction?select=sample_submission.csv

***Data set paramenters are: [Id', 'Gender', 'Age', 'Driving_Licensse', 'Region_Code', 'Previously_Insured','Vehicle_
Age', 'Vehicle_Damage', 'Annual_Premium', 'Policy_Sales_Channel','Vintage','Response']***
       

---

## Principal Components Analysis(PCA)
PCA is a method of extracting important variables from a large set of variables available in a data set. It extracts low dimensional set of features from a high dimensional data set with a motive to capture as much information as possible.

### Visualisation.

1.Scree plot

It can be seen from plot that, PCA-1 explains (41.65%) most of the variance than subsequent components. In other words, most of the features are explained and encompassed by PCA1. The rule of thumb is to capture 70-80%,thus we pick first 3 of the 11 PC. Great move, we reduce data set dimensonality in four times

![](https://github.com/evgenygrobov/Customer_clustering./blob/main/images/PCA__scree-1.png)  

---

2.Effect of features on each components

We can see the influence on each of the components by features. PCA 1 places more weight on Age, and approximately equal weight on Vehacle Age (1-2 and more than 2 years), with much less weight on Vehacle Age less than a year. Hence this feature roughly correspond to overall customer desicion.PCA 2 places most weight on Vintage, and PCA 3 on Previuosly Insured feature. But we remember that the PCA 1 bears the most variance.

![](https://github.com/evgenygrobov/Customer_clustering./blob/main/images/PCA_componets_heatmap.png)

---

3. PCA Biplot

Biplot is an interesting plot. It contains lot of useful information. Since, our customer is based in USA, we are wondering they want to know feature distribution.
Overall, we see that Age, Vehacle Demage and Vehacle Age (1-2 years) are located close to each other, and Vintage is far from these three.This indicates that the variables are correlated with each other- the older populaton the their cars demaged more oftenly in age between 1-2 year,and Vintage is less correlated with them.
We also can examine difference between states. The states with the largest first scores of the PCA 1, such as Maryland, West Virginia and Alabama have more population in older age with demaged car in first 1-2 years,while Wisconsin, Oregon and New York with negative scores of PCA 1 - have relatively more yanger people own cars less then a 1 year. 

![](https://github.com/evgenygrobov/Customer_clustering./blob/main/images/Bi_plot.png)

---

## KMeans clustering

Silhouettee score and Yellowbrick score clearly determinded  optimal number of clusters. Lets see.

### Visualization

1. Scatter plot shows how the customers are clustered.

![](https://github.com/evgenygrobov/Customer_clustering./blob/main/images/PCA_labled__YES_customers.png)

2. I assigned cluster's ID to the data set observations. Now we can check relations of  most weighted features given from PCA.

**Scatter plot Age & Vehicle age 1-2 years**

We can observe positive correlation between Age and Vehicle age. With increase in Age we are eyebolling an increase in portion of Vehicles in age 1-2year.

![](https://github.com/evgenygrobov/Customer_clustering./blob/main/images/Age_PairWith_Vehicle_Age_1-2%20Year.png)


**Scatter pair plot Age & Vehicle damage**

 We also observe a positive correlation between Age and Vehicle Demage.With increase in Age the rate of demaged vehicle rise up as well.

![](https://github.com/evgenygrobov/Customer_clustering./blob/main/images/Age_PairWith_Vehicle_Damage.png)


3. Lets see proportions between clusters we obtained from data set. The most populated cluster #0.

![](https://github.com/evgenygrobov/Customer_clustering./blob/main/images/Pie_chart__Clusters_%25.png)

---

## All custmers who answered Yes were grouped by clusters. We also can see clusters distribition nationwide. is not great?


|    Cluster # 0   | Cluster # 2         |   Cluster # 1           | 
|:-----------------|:-------------------:|:-----------------------:|
| Arkanzas         | Alabama             | Arizona                 | 
| California       | Alaska              | Colorado                | 
| Delaware         | Maryland            | Connecticut             | 
| Florida          | Michigan            | Georgia                 | 
| Hawaii           | Tennessee           | Illinoise               | 
| Idaho            | Puerto Rico         | Indiana                 |        
| Kentucky         | West Virginia       | Iowa                    |
| Luisiana         |                     | Kansas                  |
| Maine            |                     | Massachusetts           |
| Minissota        |                     | Nebraska                |
| Mississippi      |                     | New Jersey              |
| Missouri         |                     | New York                |
| Monatana         |                     | North Dakota            |
| Nevada           |                     | Oklahoma                |
| New Hampshire    |                     | Oregon                  |
| New Mexico       |                     | Utah                    |
| North Carolina   |                     | Wysconsin               |
| Ohio             |                     |                         |
| Pennsilvania     |                     |                         |
| South Carolina   |                     |                         |
| Texas            |                     |                         |
| Vermont          |                     |                         |
| Virginia         |                     |                         |
| Washington       |                     |                         |
| Wyoming          |                     |                         |
