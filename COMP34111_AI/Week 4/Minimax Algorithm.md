![[Pasted image 20251028094239.png]]
![[Pasted image 20251028094441.png]]

The algorithm computes the largest expected payoff that player i can guarantee even in the worst case - assume that the other players are:
- playing to maximise their own payoff 
- trying to minimise our payoff.

It is a recursive algorithm:
1. Calculate values of all immediate successors
2. To calculate those, need values of their successors
3. Continue recursively until reaching final positions
4. At final positions, read value off the payoff function

Bottom up - start from leaves and work upward
Depth-first - start from the root and calculate on the way back up.

For 2 person zero-sum games of perfect information, minimax finds equilibrium strategies.

Provides security strategy
Works even when equilibrium is hard to find
But
May be overly conservative
Doesn't find equilibrium payoffs
Assumes opponent is adversarial

DOES NOT APPLY TO IMPERFECT INFORMATION GAMES
In imperfect information games, positions in the same info set have the same immediate moves but these will lead to different game trees down the line.
How can we know which move will maximise our payoff, if we don't know which node we're making a move from?





