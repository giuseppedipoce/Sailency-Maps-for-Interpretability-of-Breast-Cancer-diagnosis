# Diagnostic Wisconsin Breast Cancer Database
![image](https://github.com/giuseppedipoce/Sailency-Maps-for-Interpretability-of-Breast-Cancer-diagnosis/assets/114066138/1be75565-3698-447b-8b09-af97e21da2fe)\
The data taken into consideration for the task assigned in this homework essentially concerning the detection of malignant or benign breast cancer cells and are in tabular form (569 instances and 30 features).\
Features are computed from a digitized image of a fine needle aspirate (FNA) of a breast mass. They describe characteristics of the cell nuclei present in the image that are in the below form:

![image](https://github.com/giuseppedipoce/Sailency-Maps-for-Interpretability-of-Breast-Cancer-diagnosis/assets/114066138/ed208088-e2b6-4e3f-89f2-f97c7bb6d8bb)\
Basically we have features like *worst values*, *standard error* or *mean* coming from ***compactness, concavity, area, texture*** and other characteristics of breast cell nuclei. In particular standard error in the case provides information about the variability or uncertainty associated with those measurements.
For example, in "compactness_se" and "radius_se." these represent the standard error of the compactness and radius measurements, respectively. The "se" values gives an idea of how much individual measurements of compactness or radius might vary around their mean values within a specific section of the tumor.





From the photo above we can distinguish a different density of cells in the two classification states (benign or malignant). Infact reast density is an intrinsic risk factor for breast cancer and increases the risk 4 to 6 times. Furthermore, breast density can mask the presence of a lump, especially if it is still very small.
Others images can be found at http://www.cs.wisc.edu/~street/images/ \
The feature extraction from images to create this dataset is very interesting and can be found [here](https://www.semanticscholar.org/paper/Nuclear-feature-extraction-for-breast-tumor-Street-Wolberg/53f0fbb425bc14468eb3bf96b2e1d41ba8087f36). Basically data may be considered linearly separable also in a $R^{30}$ space on which our data points lie.\
# About explainability

What do we mean by explainability? Consider the neural network $f(\cdot)$ you just trained, and a prediction $\hat{y} = f(x)$ we want to analyze. **Feature attribution** methods try to assign a weight $w_i$ to each input feature $x_i$, to understand which parts of the input have contributed the most to the explanation.

The simplest feature attribution technique, called **vanilla saliency map**, simply computes the gradient at that point:

$$
  S(x) = \left\lvert \frac{\partial f_c(x)}{\partial x} \right\rvert
$$

where  $c$ is the index corresponding to the predicted class.
# Results 
![image](https://github.com/giuseppedipoce/Sailency-Maps-for-Interpretability-of-Breast-Cancer-diagnosis/assets/114066138/328c0468-834f-4228-acda-521b43ecf4ac)
- MALIGNANT:\
With a visualisation of the type above, it is very clear and obvious that depending on the class to which it belongs, there are data attributes that have different 'weights'. In the case of a malignant tumour, the "concavity mean" turns out to be a very relevant feature, which in fact was the one with a surplus over the calculated difference in the previous largest section. "Area worst" and "simmetry wrost" also prove to be important by having a real black line drawn on the map in their correspondence;
- BENIGNANT:\
"radius se" ,"perimeter mean","area worst" and "area se" appear to be the most relevant for the detection of benignant tumors, that are basically the three black columns that we can distinguish in the right silency map;
