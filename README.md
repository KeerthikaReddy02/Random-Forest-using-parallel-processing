# Random-Forest-using-parallel-processing
Optimization of Random Forest Algorithm using parallel processing

## Abstract
The random forest approach, which aggregates decision trees made from random features, can be used to generate machine learning models. A predictive model that links data observations to specific inferences about the data is built using trees. Excessive processing times are a common problem that frequently occurs when random forest is applied since it requires a large amount of data and develops several tree models in order to create random trees utilising a single processor. We aim to accelerate random forest using R programming and parallel computing. The model will be speed tested against conventional Random Forest using the dhfr datasets. Findings from the entire study will show that running a random forest in parallel requires less processing time than doing so on a single processor.

## About the dataset
### Dhfr dataset
Values for 325 chemicals are included in this data set. 228 molecular descriptors have been derived for each molecule. Each sample is also categorised as "active" or "inactive." A column called Y with the outcome classification can be found in the data frame dhfr. The remaining columns provide values for molecular descriptors.

## Proposed work
Each tree is built serially in a standard Random Forest. Time complexity: O(t|K|nlogn), with t equal to the number of trees. K: the number of selected features n is the size of the practise set. Although adding more trees can increase accuracy, it can also extend training time. Consequently, we employ parallel processing when programming in R.

rf <- randomForest(x=data, y=classes, ntree=5000, ...) The ntree parameter, which informs us of how many trees the forest would have, contains the parallelism in this situation. The trees are evenly distributed among the available processes in our task parallel approach, which then creates these sub forests in parallel before combining them into a bigger forest that is returned on the master process.  Speed up can be achieved by two-folds.
