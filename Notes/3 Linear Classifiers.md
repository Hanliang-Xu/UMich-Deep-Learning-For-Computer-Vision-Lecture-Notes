the basic blocks of neural network are linear classifiers

Three ways to think about Linear Classifier
parametric approach
f(x, W) = Wx + b
	W - paramters or weights
	**algebraic viewpoint** (f(x, W) = Wx) - predictions are linear
	**visual viewpoint** (One template per class) - template matching
		a single template cannot capture multiple modes of the data (e.g. horse template has two heads)
	**geometric viewpoint** (Hyperplanes cutting up spaces)
		hyperplanes carving up a high-dimensional space
	Limitations:
		linear model could not learn XOR

How can we actually select a W
	loss function
	optimization

Loss Function (objective function, cost function, etc.)
	how good our current classifier is
	Multiclass SVM Loss: "hinge loss"
	debugging technique: think about the loss when numbers are small
	Q1: What happens to the loss if the scores for the cars changed a bit
	Q2: what are the min and max possible loss
	Q3: if all the scores were random, what loss would we expect
	Q4: what would happen if the sum were over all classes?
	Q5: What if the loss used a mean instead of a sum
	Q6: What if we put a square over the max value
	Q7: What if we found some W with L = 0. Is it unique?
	Q8: How should we choose models if they perform the same

Regularization: beyond training error
	L(W) = Data loss (model prediction should match training data) + Regularization (prevent the model from doing too well on training data)
	Purpose of regularization
		preferences among models
		prefer simpler model: avoid overfitting

Cross Entropy Loss (multinomial logistic regression)
	to probabilities
		softmax function
		unnormalized log-probabilities / logits
		unnormalized probabilities
		probabilities
	Maximum Likelihood Estimation
	Kullback-Leibler divergence
	Cross Entropy
	If all scores are random values, the loss is log(C)

Softmax & SVM & Full Loss - different loss functions that quantify preferences