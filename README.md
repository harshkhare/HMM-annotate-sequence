# HMM-annotate-sequence

These IPython notebooks provide a user friendly way to use Hidden Markov Models (HMMs) to annotate protein sequences based on sequence characteristics.
Pomogranate package has been used to build HMM model (https://pomegranate.readthedocs.io/en/latest/HiddenMarkovModel.html)    

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

In many cases it is useful to group various amino acids based on their stereo-chemical properties. For example, all hydrophobic amino acids may be clubbed in one group while the hydrophilic in another. Such categorization might give different insights into the functions of various regions in a protein sequence based on the properties of those regions. To tell the HMM model about this grouping based on properties, one has to convert the raw amino acid sequences into sequences that use different letters to denote different groups of amino acids. This repository allows to do this by defining dictionary of amino acid letters and their corresponding translations to new letter as follows.    

```python
# Amino acid code single letter
aa_code1 = ['A','C','D','E','F','G','H','I','K','L','M','N','P','Q','R','S','T','V','W','X','Y']

# Amino acid categories i.e. the observed states for HMM
aa_code_cat = ['P','A','K','T','O']

# Amino acid category mapping dictionary
aa_code_cat_dict = { 'P':'P',
                     'A':'A',
                     'K':'K',
                     'T':'T',
                     'C':'O', 'D':'O', 'E':'O', 'F':'O', 'G':'O', 'H':'O', 'I':'O', 'L':'O',
                     'M':'O', 'N':'O', 'Q':'O', 'R':'O', 'S':'O', 'V':'O', 'W':'O', 'X':'O', 'Y':'O'}
```
This dictionary can then be used to convert a sequence of amino acids to a sequence oc amino acid categories (P, A, K, T and O in this case). More details on this can be found in the notebook along with the code.    

