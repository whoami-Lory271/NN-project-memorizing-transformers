# Memorizing Transformers (https://arxiv.org/pdf/2203.08913.pdf)
**Authors**
* Luigi Antonelli 1851425
* Lorenzo De Santis 1849114

## Brief introduction
Memorizing transformers are decoder-only transformers which have the ability to store in a non-differentiable memory the internal representations of past inputs, allowing to combine local attention with a $k$-nearest neighbors search into the memory. In particular, the architecture of these models uses standard transfomer blocks and a special transformer block that uses this modified version of the attention, taking also into consideration information from previous training steps.

We are proposing two different approaches:
* The first one uses only our **Memorizing Transformer** model with 12 layers of **Transformer Block** where the $9^{th}$ one is a **Memory Block**

* The second one uses the **Bert** model as embedding layer, followed by a **Memorizing Transformer** with 4 layers of **Transformer Block** where the $3^{th}$ one is a **Memory Block**.

## How to run the code
In order to run the notebook you can simply connect the Colab notebook to a runtime and execute its cells.  
You need to modify some parts of the code if you want to run using the first or second pipeline:
* In the first case you need to decomment the section with title *Decomment if you want to use the first method* and set in the *Training* section the `USE_BERT` variable to `False`

* In the Second case you need to decomment the section with title *Decomment if you want to use the second method* and set in the *Training* section the `USE_BERT` variable to `True`
