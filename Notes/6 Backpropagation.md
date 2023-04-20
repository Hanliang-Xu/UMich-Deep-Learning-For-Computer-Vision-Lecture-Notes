(Bad) idea: Derive ∇WL on paper
	tedious
	want to change loss?
	not feasible for complex models
	
Better idea: computational graph
	Deep network (AlexNet)
		input image
		weights
		loss
	Neural Turing Machine

Backpropagation: simple example
	f(x, y, z) = (x+y)z
	chain rule
		downstream gradient
		local gradient
		upstream gradient
	computational graph is not unique: we can use primitives that have simple local gradients
	patterns in gradient flow
		add gate: gradient distributor
		copy gate: gradient adder
		mul gate: swap multiplier
		max gate: gradient router
	"flat" gradient code

Backpropagation implementation: mudular API

So far: backprop with scalars
What about vector-valued functions?

Jacobian is sparse: off-diagonal entries all zero! Never explicitly form Jacobian, instead use implicit multiplication
	examples - matrix multiplicaitons

Reverse-Mode Automatic Differentiation
Forward-Mode Automatic Differentiation
	Avoid matrix-matrix products, only needs matrix-vector

Backprop: Higher-Order Derivatives

Summary:
	Represent complex expressions as computational graphs
	downstrea gradients = upstream gradients multiply local gradients