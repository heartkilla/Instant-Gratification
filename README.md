# Instant Gratification
![](https://storage.googleapis.com/kaggle-media/competitions/general/Kerneler-white-desc2_transparent.png) <br>
A solution for Kaggle Instant Gratification competition.

This solution scored 0.97164 ROC AUC on Private Leaderboard and reached 118th place (top 7%, bronze medal🥉).

## Brief solution summary
The solution heavily uses several techniques such as Quadratic Discriminant Analysis(QDA), Gaussian Mixture Model(GMM), pseudolabeling(PL), Principal Component Analysis(PCA) and Bootstrap Aggregating(bagging).

I used a blending(weighted average) ensemble of 4 models:
1. QDA with PL generated from GMM initialized with Graphical Lasso
2. PCA+QDA with PL from GMM
3. QDA with bagging and PL from Model 1
4. QDA with iterative PL

Furthermore, in order to increase the diversity and provide a more stable solution, I made another ensemble but with different hyperparameters. The final submission was an average of two ensembles.
