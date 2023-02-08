# HMM-annotate-sequence

These IPython notebooks provide a user friendly way to use Hidden Markov Models (HMMs) to annotate protein sequences based on sequence characteristics.

An HMM is trained using labeled training example sequences which can then be used to predict the labels for a new sequence.  

Here, amino acid sequences of proteins have been used however, the functions may be adapted to other types of sequences.

|                                      |                  State sequence                  |
|--------------------------------------|--------------------------------------------------|
| Amino acid sequence (observed states)| ``MSDFHPLWSCNMEAKPEAKKAAKKAPAKKAATKATSAKKAPAPAA``|
| Annotated sequence (hidden states)   | ``FFFFFFFFFFFFFFFFFTTTTTTTTTTTTTTTTTTTTTTTTTTTT``|

In the above example, the objective is to learn state transition probabilities such that hidden states can be predicted using the observed states.  
The pipeline provided in this repository learns state transition probabilities

## More details coming soon...
