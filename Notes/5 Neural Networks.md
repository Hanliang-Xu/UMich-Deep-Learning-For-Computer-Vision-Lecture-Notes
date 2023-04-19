Problem: linear classifiers are not that powerful
One solution: feature transforms
	e.g. Color histogram (color)
	e.g. histogram of oriented gradients (edges)
	e.g. bag of words ("codebook" of "visual words")

Image features & Neural Networks
	before Linear score function: f = Wx
	now 2-layer neural network: f = W2 max(0, W1x)
	in practice: learnable bias

Fully connected neural network
	also, Multi-Layer Perceptron
	first layer is bank of templates, second layer recombines templates
	use different templates to cover multiple modes of a class
	distributed representation

Deep neural networks
	depth: number of layers
	width: size of each layer

Activation function
	ReLU(z) = max(0, z)
	activation function
	without nonlinear function, still linear classifier
	other activation function: sigmoid, tanh, leaky ReLU, maxout, ELU, etc.

Similarity and difference between biological neurons and neurons in a neuron network
	be careful with brain analogies

Space warping
	collapsed version of space
	points are linearly separable in feature space

Setting the number of layers and their size
	don't regularize with size, instead use stronger L2

Universal approximation
	approximate any function with arbitrary precision
	output is a sum of shifted, scaled ReLUs
	bump function
	approximate function with bumps
	reality: networks don't really learn bumps

Convex functions
	intuition: a convex function is a multidimensional bowl
	easy to optimize
	converging to global minimum
	neural network - sometimes really wild, rely on nonconvex optimization

How do we compute gradients