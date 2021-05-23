# cse284_SP21_final

(can be used in paper and presentation)

First we try the variance filter. We notice that some dimensions have variance close to 0, which means most of the values on each of those SNPs are similar 0/1/2. But we can’t just ignore those SNPs, since they may still contribute to the population prediction. So the variance filter won’t drop too much dimensions. If we only filter a few dimensions, this won’t contribute to the prediction too much. Our experiment shows that subsequent methods can include the work of variance filter.

Then we choose chi2 selection method to select K best dimensions. After the feature selection, we get 5000 SNPs from 28622 SNPs and reach a good accuracy 0.90 using a simple_svm classifier.

We also test PCA for comparison. The simple_svm can reach the same accuracy with fewer features/dimensions extracted from PCA. In our case, 28622 SNPs can be extracted to 4 dimensions and the simple_svm have a good accuracy 0.92.
The problem is: after feature extraction, the feature space is changed as well. One of the new features may contain the information from many old features. If we don't care about the relationship between SNPs and populations, we can just use PCA to make the prediction easier.
Also, PCA is not fast enough. And it takes longer time to get more dimensions, which is not very efficient for experiments.

...
