# unsupervised_learning
Repo for HW 20 - Unsupervised Machine Learning!

Everything for this assignment is completed within the "cryptoLearning" Jupyter Notebook

* First we read in the CSV data file
* We use .unique() on the Algorithm column to see all the different algorithms being used
* We use .value_counts() on the IsTrading column to see how many of the coins are trading and how many are not
* Next, we use a df.loc[] to filter the dataset to only the coins that *are* trading, then we we drop the IsTrading column as it's no longer necessary
    * This brings our number to 1144
* Next, we use .dropna() to drop any rows with null values
    * This brings our number to 685
* Next, we use .sort_values() on the TotalCoinsMined column values to see the highest and lowest values
    * Doing this shows there is one negative and a number of zeros
    * We then filter the dataframe to only rows with a TotalCoinsMined value > 0
    * This brings our number to 532
* Next, we delete the CoinName column, as it is not needed
* The final data cleanup is to use pd.get_dummies() for our columns with string values

* Now we use the StandardScaler() to fit our dataframe that has the dummy variables

* Next, we need to reduce the dataset dimension with PCA
* For this we use 90% of the data (n_components = .90)
* Then we create our principal components variable, which is the PCA-fit of the scaled data
* We reduce the dimensions using t-SNE
* Then we plot the data

* Next, we identify clusters using k-means
* To do this, we first create an empty list for inertia and a "k" list of numbers 1 - 10
* Then we iterate through the k list
    * For for 10 times, we use KMeans to cluster and fit principal components, then append the results to the inertia list
* We then take the k and inertia lists and create an elbow plot from them

* Through both this elbow plot and the previous t-SNE scatter plot, we see a lack of meaningful clustering
* This means that there is a lack of detectable, meaningful trends within the dataset
* This could indicate a volitility and unreliablity for the cryptocurrency market



