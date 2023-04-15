Question: how to fit the data to our training set - Optimization

w* = arg min(w) L(w)

Idea #1. Random search

Idea #2. Follow the slope
	derivative of a function
	gradient
		How to calculate?
			- numeric gradient (slow, approximate)
			- analytic gradient
			- in practice, we use backpropogation
		in practice: always use analytic gradient, but check implementation with numeric gradient. This is called gradient check

Gradient Descent
	iteratively step in the direction of the negative gradient
	hyperparameters:
		weight initialization method
		number of steps
		learning rate
	features:
		doesn't go straight to the bottom
		starts out going fast, later slow
	Batch Gradient Descent
		problem: full sum expensive when N is large
	Stochastic Gradient Descent
		approximate sum using a minibatch of examples 32 / 64 / 128
		need 2 more hyperparameters: batch size and data sampling
		think of loss as an expectation over the full data distribution p data
		approximate expectation via sampling
	Problems with SGD
		loss function has high condition number
		local minimum or saddle point (zero gradient)
		our gradients come from minibatches, so they canbe noisy!

SGD + Momentum
	build up "velocity" as a running mean of gradients
	Rho gives "friction", typically = 0.9 or 0.99
	Nesterov Momentum (look ahead to the point where updating using velocity would take us)
	features: overshoot & comeback

AdaGrad, RMSProp - adaptive learning rate
	progress along steep directions is damped
	progress along flat directions is accelerated

Adam (almost): RMSProp + Momentum + Bias correction

So far: first-order optimization

second-order optimization
	use gradient and Hessian to make quadratic approximation
	step to minimize the approximation
	second order Tylor expansion
	however, impractical: inverting takes O(N^3)

In practice
	Adam - good default choice
	SGD + Momentum - can outperform, require tuning
	full batch updates - L-BFGS