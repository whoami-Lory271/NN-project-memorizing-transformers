# Re-implementation of [Memorizing Transformers](https://openreview.net/pdf?id=TrjbxzRcnf-)
**Authors**
* Luigi Antonelli 
* Lorenzo De Santis 1849114

## Used Methods
Memorizing transformers are decoder-only transformers which have the ability to store in a non-differentiable memory the internal representations of past inputs, allowing to combine local attention with a $k$-nearest neighbors search into the memory. In particular, the architecture of these models uses standard transfomer blocks and a special transformer block that uses this modified version of the attention, taking also into consideration information from previous training steps.

We propose two different pipelines
* The first one use only our **Memorizing Transformer** model with 12 stacked layers of **Transformer Block** one of which (the $8^{th}$) is a **Memorizing Block** (that will be described better inside the notebook)

* The second one use the **Bert** model as embedding layer, then we pass its output to a **Memorizing Transformer** with 4 layers of **Transformer Block** one of which (the $2^{nd}$) is a **Memorizing Block**

## How to run the code
In order to run the notebook you can simply connect the Colab to a GPU runtime and run all!  
You need to modify some part of the code if you want to run using the first or second pipeline
* In the first case you need to decomment the section with title *Decomment if you wont tu use the first method* and set in the *Training* section the `USE_BERT` variable to `False`

* In the Second case you need to decomment the section with title *Decomment if you wont tu use the second method* and set in the *Training* section the `USE_BERT` variable to `True`
