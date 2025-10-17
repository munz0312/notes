Matrix form to represent games
![[Pasted image 20251014092031.png]]
To generate this sort of tree:
	1. Enumerate through all strategies for each player
	2. For each combination of strategies:
		- Follow the unique path through the game tree
		- Overlay all strategy subtrees
		- Find where they all overlap (unique path)
		- Read off the payoffs at the leaf
	3. Fill in the payoff table

For games with chance
1. For each reachable final node:
	- Calculate probability: Multiply all probabilities along the path
	- Multiply the probability by the payoff -> expected payoff
2. Sum all the values from 1.

![[Pasted image 20251016151841.png]]
![[Pasted image 20251016151852.png]]

![[Pasted image 20251014093217.png]]

For 2-player zero sum games, a simplified version can be used because Player 2's payoffs are just the negative of Player 1.
![[Pasted image 20251014094312.png]]
![[Pasted image 20251014094232.png]]

![[Pasted image 20251014094120.png]]

Game trees grow exponentially - tree of height $m$ has $>= 2^{m+1}-1$ positions.
Strategies grow even faster.
![[Pasted image 20251014095154.png]]

In a 2-player zero sum game:
A winning strategy is one that gives a payoff > 0, regardless of how the opponent plays
A drawing strategy is one that gives a payoff $\ge$ 0

![[Pasted image 20251014095421.png]]
