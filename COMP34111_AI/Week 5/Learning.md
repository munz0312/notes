Minimax may not be good if:
- Good heuristics can't be found
- Branching factor is very high
- Equlibria are hard to compute (games of incomplete information, general-sum, many players)

Many important games have very large trees to search completely (eg. Chess, Go, Othello, Hex)

So instead, we can try 'learning' (eg while playing)
Feedback from outcome of the game reveals whether or not you played right or wrong, but not WHAT you did right or wrong - you don't know the crucial moves that lead to the outcome

## Exploration vs Exploitation

Exploitation is to make the best decision given current information
Exploration is to gather more information

The best long-term strategy may involve short-term sacrifices - gather enough information to make the best overall decisions.

For example, imagine going out to eat at a restaurant - you could go to your favourite restaurant (exploitation), or you could try a new one (exploration).

![[Pasted image 20251104143159.png]]
![[Pasted image 20251104143224.png]]
![[Pasted image 20251104143242.png]]

Greedy algorithms estimate Q(a). It selects the action with the highest estimate of Q(a) at time/step t.

![[Pasted image 20251104201642.png]]
![[Pasted image 20251104202543.png]]
