# Memorizing Transformers
**Authors**
* Luigi Antonelli 1851425
* Lorenzo De Santis 1849114

Memorizing transformers (https://arxiv.org/pdf/2203.08913.pdf) are decoder-only transformers which have the ability to store in a non-differentiable memory the internal representations of past inputs, allowing to combine local attention with a $k$-nearest neighbors search into the memory. In particular, the architecture of these models uses standard transformer blocks and a special transformer block that uses this modified version of the attention, taking also into consideration information from previous training steps.

We are proposing two different approaches:
* The first one uses only our **Memorizing Transformer** model with 12 layers of **Transformer Block** where the $9^{th}$ one is a **Memory Block** (like the authors of the paper suggest)

* The second one uses the **Bert** model as embedding layer, followed by a **Memorizing Transformer** with 4 layers of **Transformer Block** where the $3^{th}$ one is a **Memory Block**.

Finally, we are reporting a comparison between a memorizing transformer and a decoder-only transformer that both use Bert as embedding layer. The task on which the two models were trained on is language modelling so the evaluation metric is the perplexity (https://torchmetrics.readthedocs.io/en/stable/text/perplexity.html?highlight=perplexity).

## How to run the code
In order to run the notebook you can simply connect the Colab notebook to a runtime and execute its cells :)  
You need to modify some parts of the code if you want to run using the first or second pipeline:
* In the first case you need to decomment the section with title *Decomment if you want to use the first method* and set in the *Training* section the `USE_BERT` variable to `False`

* In the Second case you need to decomment the section with title *Decomment if you want to use the second method* and set in the *Training* section the `USE_BERT` variable to `True`

If you want to load our models (either `TransformerDecoder`or `MemorizingTransformer`) trained using the *first method*, you can set in the *Training* section the `LOAD_MODEL` variable to `True`.
