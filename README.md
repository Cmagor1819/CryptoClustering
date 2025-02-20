# CryptoClustering

# Objective:

In this challenge, you'll use your knowledge of Python and unsupervised learning to predict if cryptocurrencies are affected by 24-hour or 7-day price changes.

We first start the file by importing all the necessary dependencies, loading the data into a dataframe, generate summary statistics, and plotting the data to visualize what's in the DataFrame.

# Part 1: Prep the data

In this section we start by using the StandardScaler() module to normalize the data. We then create a DataFrame of the scaled data, set the index to 'coin_id' and display the DataFrame.

# Part 2: 

In this section we are finding the best value for k using the original scaled DataFrame. We initially create a list with the number of k-values from 1 to 11. Next we create an empty list to store the inertia values and create a for loop to calculate the inertia with each possible value of k.

Next we create a dictionary to be able to plot the elbow curve. Finally, we plot a line chart to display the elbow curve and asses what the best value for k would be.

# Part 3:

For this section, we are clustering cryptocurrencies with k-means using the original scaled DataFrame.

We start by initializing the k-means model using the best value, we fit the model using the scaled DataFrame,

predict the clusters to group the crypto, create a copy of the scaled DataFrame, add a new column to the copied DataFrame, and then finally create a scatter plot of the new DataFrame.

# Part 4:

Here we are optimizing clusters with PCA.

To start, we create the PCA model and set the components to 3. Next, we use the fit_transform to reduce the original scaled DataFrame, retrieve the explained variance, and create a DataFrame with the PCA data, 

# Part 5:

Here we are finding the best value for k using the scaled PCA DataFrame. 

We need to create a k list ranging from 1 to 11, create an empty inertia list, create a for loop to generate the inertia with every possible value of k, create a dictionary to plot the new elbow curve, and then plot the elbow curve using the computed inertia values.

# Part 6:

For this section we are clustering cryptocurrencies with k-means using the scaled PCA DataFrame.

Need to initialize the model using the best value for k(4), fit the model using PCA data, predict the clusters using the scaled PCA DataFrame, create a copy of the PCA DataFrame, and then create a scatter plot of the copied PCA data.

# Part 7:

In the final section we are visually analyzing the clusters analysis results by contrasting the outcome with and without using optimization techniques.

We need to display both of the elbow curves to visualize and display both of the scatter plots to visualize.

We can then answer the analysis question based off what is generated.

I got/referenced the following lines of code from Xpert Learning Assistant/GitHub:

* crypto_data_scaled = StandardScaler().fit_transform(df_market_data[['price_change_percentage_24h', 'price_change_percentage_7d', 'price_change_percentage_14d', 'price_change_percentage_30d', 'price_change_percentage_60d', 'price_change_percentage_200d', 'price_change_percentage_1y']])

* for i in k:
    k_model = KMeans(n_clusters=i, random_state=1)
    k_model.fit(df_market_data_scaled)
    inertia.append(k_model.inertia_)
