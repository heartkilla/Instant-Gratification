# Kaggle Instant Gratification Competition
![](https://storage.googleapis.com/kaggle-media/competitions/general/Kerneler-white-desc2_transparent.png) <br>
A solution for Kaggle Instant Gratification competition.

In this competition we were given a synthetic dataset that was generated in an unknown way. The main task was to investigate how the data was generated and use this knowledge to acheive a high score.

This solution scored 0.97164 ROC AUC on Private Leaderboard and reached 118th place (top 7%, bronze medal🥉).

## Brief solution summary
The community quickly found out that the data was probably generated with sklearn's `make_classification` function. This function produces clusters of multivariate Gaussian distributions. Therefore, Quadratic Discriminant Analysis (QDA) and Gaussian Mixture Model (GMM) were the best candidates for solving this task.
In addition, this solution relies heavily on several techniques such as Pseudolabeling (PL), Principal Component Analysis (PCA) and Bootstrap Aggregating (Bagging).

I used a blending (weighted average) ensemble of 4 models:
1. QDA with PL generated from GMM initialized with Graphical Lasso
2. PCA+QDA with PL from GMM
3. QDA with bagging and PL from Model 1
4. QDA with iterative PL

Furthermore, in order to increase the diversity and provide a more stable solution, I made another ensemble but with different hyperparameters. The final submission was an average of two ensembles.
