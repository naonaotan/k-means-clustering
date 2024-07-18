# Clustering Penguins with k-means

### Database
The analyzed data was 'penguins' of dataset 'palmerpenguins' present in the R Studio. The dataframe has 8 columns and 344 lines.

### Data description
| Variable            | Description          | Type       |
| :---                | :---                 | :---       |
| `species`           | penguin species      | nominal    |
| `island`            | habitat              | nominal    |
| `bill_length_mm`    | bill length in mm    | continuous |
| `bill_depth_mm`     | bill depth in mm     | continuous |
| `flipper_length_mm` | flipper length in mm | continuous |
| `body_mass_g`       | body mass in g       | continuous |
| `sex`               | gender               | nominal    |
| `year`              | year born            | discrete   |

#### The palmer penguins*
![palmer](https://raw.githubusercontent.com/naonaotan/k-means-clustering/main/lter_penguins.png)

#### Bill dimensions*
![culmen](https://raw.githubusercontent.com/naonaotan/k-means-clustering/main/culmen_depth.png)

For this penguin data, the culmen (bill) length and depth are measured as shown above.

#### Flipper dimensions*
![flipper](https://raw.githubusercontent.com/naonaotan/k-means-clustering/main/flipper.png)

### Objective

The aim of the work carried out was to apply clustering to the database to group penguins based on common characteristics, identifying natural groups within the dataset.

### Tools and steps

To perform the clustering and data grouping, we used the K-means clustering method.
The first step was to **prepare the data**. We loaded the libraries factoextra, cluster, and palmerpenguins (which the dataframe was taken), and performed data cleaning following the steps below:

- Removal of blank/null values;
- Removal of non-numeric columns;
- Removal of the year column as it interfered with the analysis of the variables.

Next, we applied the standardization of the dataframe data using the scale(df) command, which centralized and scaled the data, enabling clustering.

The second step was to **determine the ideal number of clusters**. Using the wss method command via the elbow method, we tried to determine the ideal number of clusters for the sample size.

![elbow](https://raw.githubusercontent.com/naonaotan/k-means-clustering/main/elbow%20method.png)

According to this method, the analysis showed that the ideal number of clusters would be 5. Additionally, we also used the GAP method to more precisely determine the best number of clusters and obtained the same result.

![gap](https://raw.githubusercontent.com/naonaotan/k-means-clustering/main/gap.png)

Thus, we proceeded to the third step: **executing the algorithm**. We ensured the reproducibility of the model using the set.seed(1) command and proceeded to the actual clustering, using the ideal value for k = 5.

The fourth step applied was to **visualize the clusters**. We plotted the scatter plot and calculated the means for each cluster.
![cluster]()


