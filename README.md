# Solving-Functional-Equations-with-Neural-Networks

Given $g: D \rightarrow \mathbb{R}$ and $h: D \rightarrow \mathbb{R}$ continuous, one-variable functions, $D \subset \mathbb{R}$, we try to approximate an  unknown function $f: g(D) \rightarrow \mathbb{R}$ such that $$g(f(x)) = h(x)$$

This unknown function will be model by a fully-connected neural network in TensorFlow. The idea is the following: Since we assume our functions to be continuous, there exists a sequence $(a_{n})_{n=1}^{\infty}$ such that: 

$$\displaystyle \lim_{n \rightarrow \infty} | f(x)  - \sum_{i=0}^{n} a_{i} x^{i} | = 0$$ i.e. f can be approximated by a polynomial. By assuming $C^{k}$-differentiability then the coefficients  $(a_{n})_{n=1}^{k}$ are the first k Taylor coefficients of f. For now we only assume continuity. The neural network will take as input a single number from the domain D and will output k numbers 

$(a_{i})_{i=1}^{k}$ which will be used to approximate f as 

$$\displaystyle f_{k}(x) \approx \sum_{i=0}^{k} a_{i} x^{i} $$

The loss function for the neural network will be something like $|g(f_{k}(x)) - h(x)|$, which we will try to minimize. If we take a random sample (batch) of n points from the domain D, then the loss function becomes $$\displaystyle \mathbb{E}_{x \sim D} [|g(f(x)) - h(x)|]$$ MSE is also a good candidate. Generalization of this method to multi-variable functions would be an interesting extension.
