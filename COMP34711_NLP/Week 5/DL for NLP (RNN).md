Recap of NN. A neuron's value is calculated by summing the values of the inputs from the previous layer multiplied by their respective weights, plus a bias. The value sent to the next layer is first passed through an activation function. Put many of these neurons together to form a layer, put many layers together to produce multi-layer perceptron.

![[Pasted image 20251028120346.png]]
![[Pasted image 20251028120420.png]]![[Pasted image 20251028120427.png]]

The representation vector $h_3$ encodes the information provided by 'natural language system'
Note that the same $f$ is applied for each state
W stores the RNN parameters

Vanishing gradient problems
![[Pasted image 20251028121506.png]]
When the weights are small, $G_{ki}$ can become very small for long-distance past states. Consequently, they do not contribute to learning the correct weights.

This then leads to dependency loss between the current and long-distance past states.
![[Pasted image 20251028121652.png]]
Here, the choice between "is" and "are" should be determined by "writer", but it is more biased to "books" because its the more recent past state.

Compared to gradient explosion, vanishing gradient is challenging to fix:
![[Pasted image 20251028122125.png]]

The idea is that we use 'gates' which are learned from data, to select various things such as which previous past content we should use.

### RNNs in NLP tasks
![[Pasted image 20251028123323.png]]
![[Pasted image 20251028123332.png]]

### Advanced RNN architectures
Bi-directional RNNs are used to consider both left and right context as the representation vector of a state is affected by its left and right states.

Concatenate hidden representations computed by two RNNs using the original and reversed sequences as the input, respectively.

![[Pasted image 20251028123711.png]]

So far, the RNNs we've seen are 'single-layer'. We can compute more complex representation vectors and improve model performance. Stack multiple layers of RNN.
![[Pasted image 20251028123953.png]]











