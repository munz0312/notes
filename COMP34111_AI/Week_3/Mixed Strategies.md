Some games have no pure strategy equilibrium - rock paper scissors payoff table has entry which is both a row minimum and column maximum

For every pure strategy, there is a counter strategy.

One solution is to randomise the strategy - play unpredictably.

In the rock paper scissors game, we would use all 3 strategies equally as often.

![[Pasted image 20251023150640.png]]

In practice, use a random device that outputs number i with probability $q_i$. Play the pure strategy corresponding to i.

A pure strategy is a special case of the above definition where strategy i is represented as:
(0, ..., 0, 1, 0, ... , 0)
Where the 1 appears in position i. It's a mixed strategy that uses only one strategy.

As we're working with probabilities, we can evaluate a strategy by calculating the expected payoff.
![[Pasted image 20251023151354.png]]
![[Pasted image 20251023151418.png]]

![[Pasted image 20251023152155.png]]


If Player i's strategy gives at least as high a payoff as any of their pure strategies, then it's a best response.

A tuple of mixed strategies is an equilibrium if and only if for every player, their payoff is at least as high as with any of their pure strategies.
![[Pasted image 20251023152801.png]]

So, to prove that a mixed strategy is better than a pure one, just compare the mixed one with the pure.

![[Pasted image 20251023153108.png]]

Every game with finitely many pure strategies for each player has at least one mixed strategy equilibrium point.

Significance:
- Guarantees solutions always exist
- Even games without pure strategy equilibria have mixed equilibria

![[Pasted image 20251023153738.png]]
![[Pasted image 20251023154303.png]]
![[Pasted image 20251023154321.png]]
