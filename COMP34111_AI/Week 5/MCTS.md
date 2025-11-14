Monte Carlo methods are a broad class of algorithms that use random sampling to obtain information.
![[Pasted image 20251113145912.png]]
![[Pasted image 20251113145926.png]]
![[Pasted image 20251113145934.png]]
![[Pasted image 20251113150245.png]]
![[Pasted image 20251113150429.png]]
![[Pasted image 20251113150751.png]]
![[Pasted image 20251113150800.png]]
![[Pasted image 20251113150858.png]]
![[Pasted image 20251113151120.png]]

Suppose we let r_i(s,a) = the reward of state s and action a at iteration i.
Q(s, a) = sum of r_i(s,a) / i


Q_n(s,a) = n-1/ n * (Q_n-1(s, a)) + 1/n r(s, a)
We can use the previous Q to update to get the next Q. This allows us to store fewer r's.
![[Pasted image 20251113151620.png]]
*imagine there is a subscript i on the next 2 Q's and r? to denote the most recent iteration*

![[Pasted image 20251113152017.png]]
![[Pasted image 20251113152127.png]]
![[Pasted image 20251113152259.png]]
















