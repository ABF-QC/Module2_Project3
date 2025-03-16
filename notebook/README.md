---
# Food and their Environmental Footprint


## Objective
The goal is to find the best unsupervised clustering algorithm that will group food by their Environmental Footprint. Once the best clustering algorithm is found, the clusters will be used to investigate which diet has a larger Environmental Footprint and  how can someone can modify their diet to reduce their Environmental Footprint.


## Data source
[ABRIBALYSE](https://doc.agribalyse.fr/documentation-en/agribalyse-data/data-access) dataset will be used for this project.

AGRIBALYSE® is the most comprehensive French public database of environmental indicators for agricultural and food products based on Life Cycle Assessment.
It provides indicators of the environmental impact of :

   - The main agricultural products produced in France,

   - The main food products consumed in France.


The [database](https://entrepot.recherche.data.gouv.fr/dataset.xhtml?persistentId=doi:10.57745/XTENSJ)) contains data on over 200 agricultural products and over 2,500 ready-to-eat foods.


---
## Step 1: Data Cleaning,

Data cleaning is crucial for data analysis. The cleaned data can be found here [Cleaned Dataset](data/AGRIBALYSE3.2_Synthese_cleaned.xlsx)

1. Each column type will be analyzed.
2. Columns that provide no valuable information will be discarded.
3. Columns will be renamed to their English translation.
4. Missing values will be found and replaced.

---
## Step 2 : Data Analysis

Data Analysis is necessary to understand 
   - the dataset
   - the various trends
   - the distribution
     
of the various information available in the dataset.

Since the goal is to create clusters that will group food that has a similar Environmental Footprint together, we will be analyzing the relationship of the various columns with the Environmental Footprint Score to find the most important trends and relationships.


---
## Step 3 : Feature Engeneering

Most clustering models can only accept numeric values. Therefore, feature engineered is a crucial step to transform categorical columns into numerical columns.  The featured engineered data can be found here [Engineered Dataset](data/AGRIBALYSE3.2_Synthese_cleaned_featEng.xlsx)

In addition, this is where we will be performing a Principal Component Analysis to evualuate the appropriate amount of component to use in our clustering model. 

Two dataset will be compare here
1. The full dataset
2. A subset of the dataset 

---
## Step 4 : Clustering Models

Three clustering models will be compared. Here are the three types of clustering model we will be evaluating.

1. KMeans Clustering Model
2. Agglomerative Clustering Model
3. Density-Based Spatial Clustering of Applications with Noise (DBSCAN) Model

All modules originate from the SciKit Learn module.

---
## Step 5 : Validation of the Clustering Models
An subjective evaluation will be performed to access how well each clustering algorithm has grouped the food by Environmental Footprint. 


## Step 6 : Analysis of the best Clustering Model (Agglomerative Clustering)
---
More detailed results can be found here [Results](Notebook/Results.md)


Using the data subset, the Agglomerative Clustering algorithm successfully identified the key elements to group food data by their Environmental Footprint.

![Clusters_EF_Score](../graph/Clusters_AC.png)

<center>
    
| Cluster | Environmental Footprint          | Key Characteristics |
|---------|----------------------------------------|----------------------|
| 4       | Lowest      | - Lowest Fine Particles  <br> - Lowest Ecotoxicity for Freshwater Aquatic System  <br> - Low Land Use  <br> - Lowest Energy Resource Depletion  <br> - Lowest Climate Change Impact |
| 1       | Low         | - Low Fine Particles  <br> - Low Ecotoxicity for Freshwater Aquatic System  <br> - Moderate Land Use  <br> - Low Energy Resource Depletion  <br> - Low Climate Change Impact |
| 5       | Low           | - Moderate Photochemical Ozone Formation  <br> - Low Water Eutrophication  <br> - High Water Resource Depletion  <br> - Low Mineral Resource Depletion  <br> - Low Climate Change Impact |
| 8       | Moderate-Low | - Low Land Use  <br> - High Energy Resource Depletion  <br> - Low-Moderate Climate Change |
| 2       | Moderate    | - High Photochemical Ozone Formation  <br> - High Fine Particles  <br> - Low Ecotoxicity for Freshwater Aquatic System  <br> - Low Land Use  <br> - Second Lowest Water Resource Depletion  <br> - Moderate Energy Resource Depletion  <br> - Low-Moderate Climate Change |
| 7       | Moderate       | - Highest Water Eutrophication  <br> - High Land Use  <br> - Low Water Resource Depletion  <br> - Moderate Energy Resource Depletion  <br> - Moderate Climate Change |
| 0       | Moderate-High | - High Ecotoxicity for Freshwater Aquatic System  <br> - Second Highest Land Use  <br> - Moderate Water Resource Depletion  <br> - Second Highest Climate Change Impact |
| 3       | High         | - Highest Freshwater Eutrophication  <br> - Extreme Water Resource Depletion |
| 6       | High          | - High Ecotoxicity for Freshwater Aquatic System  <br> - Highest Land Use  <br> - Highest Climate Change Impact |
| 9       | Highest       | - Highest Photochemical Ozone Formation  <br> - Highest Ecotoxicity for Freshwater Aquatic System  <br> - Highest Energy Resource Depletion  <br> - Highest Mineral Resource Depletion |

</center>

</br></br>




    





