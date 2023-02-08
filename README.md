# HMM-annotate-sequence

These IPython notebooks provide a user friendly way to use Hidden Markov Models (HMMs) to annotate protein sequences based on sequence characteristics.

An HMM is trained using labeled training example sequences which can then be used to predict the labels for a new sequence.  

Here, amino acid sequences of proteins have been used however, the functions may be adapted to other types of sequences.

|                                      |                  State sequence                  |
|--------------------------------------|--------------------------------------------------|
| Amino acid sequence (observed states)| ``MSDFHPLWSCNMEAKPEAKKAAKKAPAKKAATKATSAKKAPAPAA``|
| Annotated sequence (hidden states)   | ``FFFFFFFFFFFFFFFFFTTTTTTTTTTTTTTTTTTTTTTTTTTTT``|

In the above example, the objective is to learn state transition probabilities such that hidden states can be predicted using the observed states.  
The pipeline provided in this repository learns state transition probabilities from the true pairs of amino acid sequences and the corresponding annotated sequences.  
The trained HMM model can then be used to predict hidden state sequences (annotated sequences) of newer amino acid sequences.  

Here, the states 'F' and 'T' in the annotated sequence denote folded and tail regions respectively. Thus the model built in this repository can be used to identify folded and tail regions in protein sequences. It is important to note that the definition of tail in this region is very specific. There could be many types of tails in the protein sequences. The definition used here is that of PAK-tails as described by Khare et al 2017 (https://pubs.rsc.org/En/content/articlelanding/2017/mb/c7mb00412e/unauth)  


## More details coming soon...
