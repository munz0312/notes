It is an optimisation technique to avoid searching parts of the tree that can't lead to a better payoff. It returns the same answer as minimax and can be enormously faster on large game trees.

$\alpha$ is the lower bound (the best maximum we can guarantee so far) which is updated at max nodes, initialised at $\\- \infty$ to represent the worst possible pay off for player 1.     
$\beta$ is the upper bound (the best minimum we can guarantee so far) which is updated at min nodes, initialised at $\ \infty$ to represent the worst possible pay off for player 2.     

We are only interested in values within the range $[\alpha, \beta]$ 
![[Pasted image 20251104120511.png]]
