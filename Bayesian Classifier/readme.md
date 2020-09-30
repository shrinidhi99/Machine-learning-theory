## Naive Bayes
`Bayes’ Theorem` provides a way that we can calculate the probability of a piece of data belonging to a given class, given our prior knowledge. Bayes’ Theorem is stated as:

```
    P(class|data) = (P(data|class) * P(class)) / P(data)
```
Where P(class|data) is the probability of class given the provided data.

1. Separate By Class
We will need to calculate the probability of data by the class they belong to, the so-called base rate. This means that we will first need to separate our training data by class. A relatively straightforward operation.

2. Summarize Dataset
We need two statistics from a given set of data.
We’ll see how these statistics are used in the calculation of probabilities in a few steps. The two statistics we require from a given dataset are the mean and the standard deviation (average deviation from the mean). The mean is the average value and can be calculated as:

    ```C++
    mean = sum(x)/n * count(x)
    ```
    Where x is the list of values or a column we are looking.

    The sample standard deviation is calculated as the mean difference from the mean value. This can be calculated as:

    ```C++
    standard deviation = sqrt((sum i to N (x_i – mean(x))^2) / N-1)
    ```

3. Summarize Data By Class

4. Gaussian Probability Density Function

    A Gaussian distribution can be summarized using only two numbers: the mean and the standard deviation. Therefore, with a little math, we can estimate the probability of a given value. This piece of math is called a Gaussian Probability Distribution Function (or Gaussian PDF) and can be calculated as:
    ```C++
    f(x) = (1 / sqrt(2 * PI) * sigma) * exp(-((x-mean)^2 / (2 * sigma^2)))
    ```
    Where sigma is the standard deviation for x, mean is the mean for x and PI is the value of pi.

5. Class Probabilities
    The probability that a piece of data belongs to a class is calculated as follows:
    ```C++
    P(class|data) = P(X|class) * P(class)
    ```
