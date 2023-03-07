**2 Image Classification**

input: image
output: a fixed set of categories
challenge:
	semantic gap
	viewpoint variation
	intraclass variation
	fine-grained categories
	background clutter
	illumination changes
	deformation
	occlusion

Image Classification:
	Very Useful
	Building blocks for other tasks: e.g. object detection, image captioning, playing Go

An Image Classifier
	no obvious way
	Find edges - find corners
	robust, scalable? - machine learning

Machine learning: data-driven approach (a different way to program computer)
	Collect a dataset of images and labels
	Use machine learning to train a classifer
	Evaluate the classifier on new images

Common image classification dataset
	MNIST - do not hold on more complex datasets
	CIFAR10, CIFAR100
	ImageNet - objects
	MIT Places - scenes
	Omniglot - few shot learning

Train & Predict

First Classifier: Nearest Neighbor

Distance Metric to compare images
	pixel-wise absolute value differences
	training - O(1), testing - O(N)
	bad - could afford slow training, but needs fast testing

Nearest Neighbor Decision Boundaries

K-Nearest Neighbor
	smooth out rough decision boundaries
	reduce the effect of outliers
	when K>1, ties between classifiers
	Distance Metric:
		from (Manhattan) distance to (Euclidean) distance (L1 vs. L2)
		right choice of distance metric, can apply to any type of data

Hyperparamters (choices about our learning algorithm)
	Best K, best distance metric
	set them at the start of the learning process 
	problem-dependent, try them out, see what works best

Setting Hyperparameters
	work best on data? - bad, K=1 works perfectly on training data
	split data into train and test, choose hyperparameters that work best on test data - no idea how algorithm will perform on new data
	we cannot use the test set for the purpose of tweaking hyperparameters
	Evaluate on the test set only a single time, at the very end
	split data into train, validation, and test sets
		choos hyperparameters on val
		evaluate on test
	Cross validation: folds
		fold1 - fold2 - fold3 - fold4 -fold5(for validation) - test

K-Nearest Neighbor: Universal Approximation
	training samples to infinity - nearest neighbor can represent any function
	Problem: curse of dimensionality
		for uniform coverage of space, number of training points needed grows exponentially with dimension 
	on raw pixels is seldomly used
		slow at test time
		distance metrics on pixels are not informative
	Nearest neighbor with ConvNet features work well: e.g. image captioning with nearest neighbor