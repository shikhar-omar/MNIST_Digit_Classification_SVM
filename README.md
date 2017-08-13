# **MNIST_Digit_Classification_SVM**

#### **Classifying digits in the MNIST dataset with SVM classifiers using kernel-trick(RBF kernel) and kernel approximation(Nystroem approximation method)**


Support vector machines are supervised machine learning algorithms that are used for classification and regression analysis.
Originally they are linear classifiers but as we know most of the classification problems need non-linear classifiers, SVMs
can also be used efficiently for non-linear classification by using **kernel-trick**. In kernel-trick, the input data is implicitly mapped into a higher dimension space
where it is linearly separable by hyperplanes which results in non-linear decision boundaries in the original dimensions.


The kernel that is used for the classification in this project is **RBF(Radial Basis Function) kernel**. The runtime and space complexity of the kernelized algorithm do
not change with the dimensionality of the input data, but it increase with the number of the samples. The data set that
is being used here is **MNIST** digit dataset that contains 70k images. One other way for classification is to explicitly calculate
feature map and then apply a linear classifier to that,  but that would do even worse as compared to kernelized SVM as we will be
mapping data into a R<sup>N</sup> dimensional space(N being the number of the samples), space spanned by all the data points. So now all we want is to have mapping in a reasonably sized space
so that we can apply a linear filter to it. As RBF kernel works well, it will be better to compute the mapping there and then use just
a subset of that mapping and keeping the number of the sample same.This results in a approximation that is independent of the size of the dataset
and this is what **Nystroem approximation method** does.This technique really speeds up the process as the training is done on a linear classifier but comes at a cost of little dip in the accuracy.

