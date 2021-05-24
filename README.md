# cse284_SP21_final

(can be used in paper and presentation)

First we try the variance filter. We notice that some dimensions have variance close to 0, which means most of the values on each of those SNPs are similar 0/1/2. But we can’t just ignore those SNPs, since they may still contribute to the population prediction. So the variance filter won’t drop too much dimensions. If we only filter a few dimensions, this won’t contribute to the prediction too much. Our experiment shows that subsequent methods can include the work of variance filter.

Then we choose chi2 selection method to select K best dimensions. After the feature selection, we get 5000 SNPs from 28622 SNPs and reach a good accuracy 0.90 using a simple_svm classifier.

We also test PCA for comparison. The simple_svm can reach the same accuracy with fewer features/dimensions extracted from PCA. In our case, 28622 SNPs can be extracted to 4 dimensions and the simple_svm have a good accuracy 0.92.
The problem is: after feature extraction, the feature space is changed as well. One of the new features may contain the information from many old features. If we don't care about the relationship between SNPs and populations, we can just use PCA to make the prediction easier.
Also, PCA is not fast enough. And it takes longer time to get more dimensions, which is not very efficient for experiments.

...

Format:  
snp number  
(left: random; middle: info_gain; right: chi2) accuracy  
0 svm_linear  
1 KNeighbors  
2 LogisticRegression  
3 RandomForest  
4 DecisionTree  
5 AdaBoost  
6 Bayes  

10  
0.44 0.51 0.59  
0.32 0.37 0.52  
0.44 0.48 0.58  
0.37 0.46 0.58  
0.34 0.46 0.54  
0.18 0.36 0.44  
0.41 0.46 0.48  

50  
0.64 0.72 0.74  
0.57 0.60 0.69  
0.66 0.72 0.74  
0.51 0.61 0.69  
0.42 0.50 0.64  
0.51 0.16 0.45  
0.65 0.72 0.70  

100  
0.71 0.75 0.73  
0.69 0.70 0.69  
0.72 0.76 0.72  
0.62 0.63 0.72  
0.50 0.52 0.65  
0.22 0.29 0.44  
0.78 0.79 0.73  

500  
0.79 0.79 0.78  
0.84 0.84 0.81  
0.79 0.81 0.79  
0.73 0.72 0.77  
0.62 0.64 0.72  
0.33 0.39 0.82  
0.87 0.89 0.85  

1000  
0.82 0.82 0.84  
0.84 0.87 0.82  
0.83 0.85 0.83  
0.75 0.75 0.78  
0.66 0.67 0.75  
0.53 0.54 0.50  
0.87 0.90 0.89  

...
