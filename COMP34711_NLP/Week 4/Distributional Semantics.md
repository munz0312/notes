The basic idea :
- Generate a multi-dimensional feature vector to characterise the meaning of a linguistic item
- Subsequently, the semantic similarity between the linguistic items can be quantified in terms of vector similarity, using measures like cosine or inner product between vectors.

Distributional hypothesis suggests that one can infer the meaning of a word just by looking at the context it occurs in.
Distributional semantics assumes that contextual information alone constitutes a viable representation of linguistic items, in contrast to formal linguistics and formal theory of grammar.

Vector Space Model (VSM)
![[Pasted image 20251021122056.png]]
![[Pasted image 20251021122652.png]]
This model produces high-dimensional sparse vectors.
- Very high dimensions, eg 20,000 - 50,000
- Very sparse with most elements equal to zero

Low-dimensional dense vectors would be more desirable
- Lower dimensions 50-1000
- Mostly non-zero elements
	- Easier to be used as features for ML models
	- Less noisy

We have predictive word embedding models
- Calculate word embeddings by performing prediction tasks formulated based on context information
	- Define your context
	- Define your prediction task
		- Whether a word appears in a context of a target word (word2vec)
		- How many times a word appears in the context of a target word.

![[Pasted image 20251022142859.png]]
![[Pasted image 20251022142921.png]]

Then, feature extraction. The $h_i$:

![[Pasted image 20251022143043.png]]
It copies the word embedding vectors for the context words from the rows of the embedding matrix, and averages them.

The Skip-Gram Model is trained to be able to classify each target word to one of its context word.

![[Pasted image 20251022152033.png]]



