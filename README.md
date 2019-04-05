# Face-Recognition-Using-Eigenfaces
# Description
* PCA and LDA are implemented to perform dimensionality reduction on the dataset and K-NN classifier is used for classification
# Principal Component Analysis
1. Data is split into training set and test set with 50-50% split
2. Every image is converted into a vector 
3. Preprocessing is performed on the training set by performing Mean Normalization to center the data and scale it to prevent the principal components to be skewed towards a certain feature
4. The covariance matrix is computed from the training set and eigenvectors are computed from it
5. The first K eignevectors are chosen to retain 90% of the total variance and used as the projection matrix
6. The training set is projected to the lower dimensional space and used to train the K-NN classifier
7. The test set is then projected on the lower dimensional space and used to report accuracy of the classifier
# Linear Discriminant Analysis
* As LDA fails to find the lower dimensional space if the dimensions
are much higher than the number of samples in the data matrix. Thus, the
within-class matrix becomes singular, which is known as the small sample
size(SSS) problem, so PCA is performed before LDA to regularize the problem and
avoid over-fitting.
1. Data is split into training set and test set with 50-50% split
2. Every image is converted into a vector 
3. PCA is perfromed on the training set and the number of PCs chosen equals the rank of the within-class matrix before PCA
4. The training set is then projected on the lower dimensional space
5. The training set is splitted by class label
6. The mean vector for every class is computed
7. Using the mean vector of every class the between-class matrix is computed
8. The eignevectors of <a href="https://www.codecogs.com/eqnedit.php?latex=S^{-1}.B" target="_blank"><img src="https://latex.codecogs.com/gif.latex?S^{-1}.B" title="S^{-1}.B" /></a> are computed
9. The first 39 eignevectors are chosen to used as the projection matrix
10. The training set is projected to the lower dimensional space and used to train the K-NN classifier
11. The test set is then projected on the lower dimensional space and used to report accuracy of the classifier
