RNNs can suffer from information bottleneck.
![[Pasted image 20251111112536.png]]

![[Pasted image 20251111113426.png]]
![[Pasted image 20251111114714.png]]
Q, K, V

![[Pasted image 20251111120048.png]]

![[Pasted image 20251111114749.png]]
![[Pasted image 20251111114758.png]]
Initialise the weight matrices to random values (maybe) then train them using some optimisation technique.

The transformer uses the attention mechanism.
![[Pasted image 20251111121313.png]]
![[Pasted image 20251111121330.png]]
![[Pasted image 20251111121403.png]]
![[Pasted image 20251111122124.png]]

![[Pasted image 20251111132939.png]]
G is the output from adding the positional encoding to the word embeddings, which is then inputted to the multi-head attention module. Take the G then multiply (in parallel) by each of the Q, K and V vectors to get the \[q_1 .. q_n]\[k_1 .. k_n]\[v_1 .. v_n]. This is known as self attention.

In the transformer architecture, we can see that the add & norm module is added after most of the steps.
Add the input and output of the previous layer together
Normalise the sum by re-centering and rescaling.
![[Pasted image 20251111134020.png]]

For example, after the multi-head attention step, we have add & norm. We would add the output of multi-head attention with the output of adding positional encoding (you can also think of it as just adding the input to the output of a particular module).
This prevents information loss/change caused by a layer.

The feedforward neural network consists of an input layer, a hidden layer using ReLu activation and an output layer with linear activation. Keep in mind that these steps are applied to each token independently, so the feedforward NN will have inputs and output vector $1 \times d_{model}$.   

Anothe type of attention is known as cross attention, also known as encoder-decoder attention. It uses H = \[h_1, ... ,h_n] from the encoder to properly learn to complete the translation.
![[Pasted image 20251111150744.png]]
As with any particular attention module, initialise new $W^{Q, K, V}$ weights to optimise. The K and V weights are multiplied with H from the encoder, whilst the Q weight is multiplied with $\hat H$ which comes from the decoder's previous layers.

That being said, the decoder does have self attention, but with masking so that the decoder can only consider current and previous state:

![[Pasted image 20251111153054.png]]
Mathematically you would add a matrix that adds 0 for every element up to and including the token of interest and for every token after that, add $-\infty$. When we're trying to train, the sequence is provided and so the decoder would be able to 'cheat' by looking ahead.

Now, about the decoder's input. It seems that we take the ground truth, remove the last word, then prefix the beginning with \<start\> tag. This is known as "teacher forcing", where we feed it the correct previous tokens.
```
Decoder Input:  <start>  这   是
                  ↓      ↓    ↓
Target Output:     这    是   猫
```
'这' is correct (i.e. should be found in our translation) but in this position i - 1 (the start), so in this position i we should have the next word '是'.
Similarly '是' should be found in the previous position. In this position, the model should predict '猫'.