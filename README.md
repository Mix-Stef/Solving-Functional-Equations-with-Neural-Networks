# Solving-Functional-Equations-with-Neural-Networks

Given $g: D \rightarrow \mathbb{R}$ and $h: D \rightarrow \mathbb{R}$ continuous functions, $D \subset \mathbb{R}$, we try to approximate an  unknown function $f: g(D) \rightarrow \mathbb{R}$ such that $$g(f(x)) = h(x)$$

This unknown function will be model by a fully-connected neural network in TensorFlow. The idea is the following: Since we assume our functions to be continuous, there exists a sequence $(a_{n})_{n=1}^{\infty}$ such that $$\displaystyle  | f(x)  - \sum_{i=0}^{\infty} a_{i} x^{i} | = 0$$
