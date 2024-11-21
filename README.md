# Marcovaldo-GPT
GPT-style transformer model trained on Italo Calvino's _Marcovaldo_ to generate text in the author's distinctive style.
## Overview
To gain a deeper understanding of state-of-the-art transformer models, I decided to implement a decoder-only transformer that autoregressively predicts the next token (in this case: character) in a sequence.  
The model is trained to predict each successive token in parallel across the entire sequence, using causal self-attention to ensure that future tokens do not influence the predictions of previous ones.  
This autoregressive approach allows the model to generate new sequences by sampling from the token predictions, creating (in this case) entirely novel text.

Slightly more technical details:

- Character-level tokenisation.
- Prenorm convention for LayerNorm placement (with an additional LayerNorm before the final output layer).
- Dropout layers to reduce overfitting, applied to the attention matrix, MLP block output, and attention block output.
- Developed using PyTorch.  Einops library for efficient tensor reshaping.

## Dataset
_Marcovaldo_ is a collection of short stories by Italo Calvino, focused on the humorous adventures of Marcovaldo, a man living in a modern city. Calvino's unique writing style, which I first encountered in my high school literature classes, inspired this project. I aimed to explore whether the combination of large-scale matrix multiplications and simple nonlinearities could replicate, to some extent, the author's distinctive comedic register. 

## Results
I like to believe that the answer to the previous question is _partially yes_. Here are some of my favourite results:

``` 
Per il sacciapiose nuovo aveva di qualci dove le sinteoso era signor Rizzaggiù;
dava in per la sua spetta il magrando in città
se la viusi arrabile di sbola agli seccari che viata,
e bastato era dall’uspasso vaderebbi il cortilime Lo di davano e intantatura!
Fininieraia, qua, tra quando sempre una che la scacciostunza alla bicella mocchia,
agli atte un suoio dalla mangia il gattuzziondo siletro ò gli anche avversi inventi
dar svolta di vigi o lo questi e il torno camminare muro di fiori seg
```

```
Risformo nelluri eraggiri li pretripese di essera prusto solliana, di sfitta per appettincarono la 
bene e conto. 

E questanicò Marcovaldo! 
Coccati, piatendone a magirò. 

Lì di netto il che movo: nel cortello e lava non stonta è Il mianghiettino pioggiara e 
di mezza
```


## Sources
- https://archive.org/details/marcovaldo (Raw Dataset)
- https://github.com/karpathy/nanoGPT
