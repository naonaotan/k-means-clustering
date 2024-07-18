# Install necessary packages
install.packages("palmerpenguins")
install.packages("factoextra")
install.packages("cluster")

# Load necessary libraries
library(palmerpenguins)
library(factoextra)
library(cluster)

# Load the penguins dataset
df <- penguins

# Remove rows with NA values
df <- na.omit(df)

# Remove non-numeric columns
df <- df[, sapply(df, is.numeric)]

# Remove the 'year' column if it exists
if ("year" %in% colnames(df)) {
  df <- df[, !colnames(df) %in% "year"]
}

# View the cleaned dataframe
head(df)

# Standardize the data
df_scaled <- scale(df)

# Determine the optimal number of clusters using the Elbow method
fviz_nbclust(df_scaled, kmeans, method = "wss")

#graph 2
gap_stat <- clusGap(df, FUN = kmeans, nstart = 25, K.max = 10)
fviz_gap_stat(gap_stat)

# Set a seed for reproducibility
set.seed(1)

# Perform K-means clustering with the optimal number of clusters (e.g., k = 5)
kmeans_result <- kmeans(df_scaled, centers = 5, nstart = 25)

# Visualize the clusters
fviz_cluster(kmeans_result, data = df_scaled)

# Print the cluster centers
print(kmeans_result$centers)

# Add the cluster assignment to the original dataset
df$cluster <- kmeans_result$cluster

# View the first few rows of the dataframe with cluster assignments
df

