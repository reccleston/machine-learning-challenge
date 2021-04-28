# Exoplanet Exploration

- - - 
## Models

### Support Vector Machine using a linear kernel
Classifying exoplanets using a support vector machine using a linear kernel produced fruitful results. The model was hypertuned to use C = 50, producing an accuracy of 89%. This appears to be a fair result considering the training period rather brief, 57.9 seconds in total. 

### Support Vector Machine using a gaussian kernel 
Leveraging a support vector machine using a gaussian kernel to provided a slightly more accurate classification of potential exoplanets with an accuracy of 88%. The model was hypertuned to use a C of 100 and and gamma of 0.5. The tradeoff for the 1% increase in accuracy, with respect to the two SVMs, was its training time. This model took nearly twice as long to train, 121.3 seconds as compared to its linear kenerl counterpart.

### Neural Network
This model is comprised of a 40 dimensional input layer, two hidden layers, each with 120 nuerons using the ReLU activation function, and a three dimensional output layer channeling the Softmax activation function. The training time for the model was miniscule in comparison to the the other classifiers: 17.5 sec. This short training time did not appear to have any significant tradeoffs as it yielded an accuracy of 90%, comparable to the linear SVM.

### Comparisons
When comparing these models to one another it is important to consider the distrubution of classes of the dataset. This dataset has the following breakdown: ~25% candidate exoplanets, ~25% confirmed exoplanets, and ~50% false postive exoplanets. Any predictions a model makes will be compared to this originial distribution. If a model is able to predict a given class with an accuracy that is higher than that of the distribution, then the model is able to preform better than a naive model. 

Examining the confusion matrices of the SVMs explains the increase in accuracy of the linear kernel model. The confirmed precision of the linear SVM bested the gaussian SVM by 1%: 82% and 81%, respectively; however, both SVMs had a produced a recall rate of 69%. This implies that the linear SVM was able to produce more relevant results, but both models where able to correctly classify 69% of the data. Despite the similar recall rates, the f1-score of the the linear SVM was 72% whereas the gaussian SVM was 71%, with regard to the confirmed class. 

The deep neural network, again with regard to just the confirmed class, differed from the other models in that its recall rate surpassed the precision with 83% and 79%, respectively. The higher recall and precision of this model naturally produced a relatively higher f1-score of 81%. 
