Used GDSC1 and CCLE (Cancer Cell Line Encyclopedia)
GDSC1 has 1074 cell lines with 17419 genes, 367 drugs
CCLE has 1037 with 20042, 24

The study used:
![[Pasted image 20251020224126.png]]
24 drugs from CCLE, 226 drugs from GDSC1

Input layer 756 features (500 gene features + 256 drug features - from Morgan fingerprint)
4 Hidden Layers (1000, 800, 500, 100 neural units)
Uses ELU (exponential linear unit) - chosen for handling the vanishing gradient problem, improved accuracy, and faster convergence. it is f(x) = x for x>0, then f(x) = $\alpha(e^x-1)$  for x < 0, where $\alpha$ is a constant.
Outputs IC50

![[Pasted image 20251020230716.png]]

"Essential Drugs" 
![[Pasted image 20251020232857.png]]


Results
![[Pasted image 20251020232128.png]]

NDCG (Normalized Discounted Cumulative Gain) measured ranking quality of recommended drugs (closer to 1 is better). It emphasises placing more relevant items higher in the list.
Calculate the NDCG score for each cell line based on the predicted drug response values, then average the scores over the entire test dataset to obtain a final NDCG score for the model.

![[Pasted image 20251020234456.png]]
$\hat{r}$ is the predicted rank from Matrix Factorisation, $s_i$ is the drug sensitive score and $r$ is the actual or known rank of the drug of the $i^{th}$  cell line which is calculated on the basis of drug response values.