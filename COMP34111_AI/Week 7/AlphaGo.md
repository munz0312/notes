![[Pasted image 20251113152709.png]]
#1 is also known as "bootstrapping" estimating over the estimate
#2 instead of looking over all moves sample some of the actions. the policy p is a distribution that tells us how to do this.

![[Pasted image 20251113153142.png]]
Imitation learning - learn from human experts' moves.
Instead of randomly choosing moves like in MCTS, use the fast rollout policy
Instead of playing until the game ends, predict the winner from a given position.
![[Pasted image 20251113153617.png]]
Uses CNN on bottom layers, then at the end a feedforward neural network.
![[Pasted image 20251113153810.png]]
The update rule is SGD.
![[Pasted image 20251113153916.png]]
The policy gradient update aims to maximise the reward.
![[Pasted image 20251113154315.png]]
Account for lack of data by self playing games. Usually generating data is not good in ML applications, but since the game is well-defined, its okay to do.

![[Pasted image 20251113154531.png]]
$p_{\sigma}$ is from the SL policy that selects the move to expand on. p_pi is the rollout policy (choosing the moves to play) 





