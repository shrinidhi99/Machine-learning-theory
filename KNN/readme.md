## KNN
`k-Nearest Neighbors`

First we will develop each piece of the algorithm in this section, then we will tie all of the elements together into a working implementation applied to a real dataset in the next section.

1. Calculate Euclidean Distance

    We can calculate the straight line distance between two vectors using the Euclidean distance measure. It is calculated as the square root of the sum of the squared differences between the two vectors.
    ```C++
    Euclidean Distance = sqrt(sum i to N (x1_i – x2_i)^2)
    ```
    Where x1 is the first row of data, x2 is the second row of data and i is the index to a specific column as we sum across all columns.

    With Euclidean distance, the smaller the value, the more similar two records will be. A value of 0 means that there is no difference between two records.

2. Get Nearest Neighbors

    To locate the neighbors for a new piece of data within a dataset we must first calculate the distance between each record in the dataset to the new piece of data. We can do this using our distance function prepared above.

    Once distances are calculated, we must sort all of the records in the training dataset by their distance to the new data. We can then select the top k to return as the most similar neighbors.

    We can do this by keeping track of the distance for each record in the dataset as a tuple, sort the list of tuples by the distance (in descending order) and then retrieve the neighbors.


3. Make Predictions.

    The most similar neighbors collected from the training dataset can be used to make predictions.

    In the case of classification, we can return the most represented class among the neighbors.

    We can achieve this by performing the max() function on the list of output values from the neighbors. Given a list of class values observed in the neighbors, the max() function takes a set of unique class values and calls the count on the list of class values for each class value in the set.
    