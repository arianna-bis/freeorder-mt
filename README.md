# On the Difficulty of Translating Free-Order Case-Marking Languages 

This repository contains the datasets used in the paper:

"[On the Difficulty of Translating Free-Order Case-Marking Languages]()"\
A. Bisazza, A. Ustun, S. Sportel. To appear in TACL (2021). 

Using a variety of synthetic languages, we studied whether free-order case-marking languages (such as Russian, Turkish or Tamil) are more difficult to machine-translate than their fixed-order counterparts (e.g. English). For details and findings on Neural Machine Translation models (specifically, bi-LSTM and Transformers) see the paper.

## Dataset 1: Challenge Set

This is a benchmark of 7,200 English-French sentence pairs generated by a simple (synchronous) context-free grammar.
Each sentence is created so that swapping subject and object leads to another plausible sentence, for example:

* The president thanks the minister. / *Le président remercie le ministre.* 
* The minister thanks the president. / *Le ministre remercie le président.*

Each English sentence and its reverse are included in the test set together with the respective translation.

The idea is to make it impossible for the MT model to rely on semantic and collocational cues to disambiguate the role of an argument during translation. Thus only syntactic cues like word order or inflection can be used.

**challenge-orig/** contains the original English-French sentences\
**challenge-variants/** contains a number of English variants, namely:

* different (fixed) orders of main constituents (svo, sov, vso, vos)
* random order of main constitutents (random)
* shuffle all words (shuffle)
* with case marking
  * na-d: nominative/accusative deterministic (overt suffixes)
  * na-d-f:  nominative/accusative deterministic (fusional/implicit suffixes)
  * na-d-f3: nominative/accusative deterministic (fusional/implicit suffixes with 3 declensions)
  * na-a: nominative/accusative ambiguous or syncretic (overt suffixes)
* no case marking (none)

For the random and shuffle conditions two versions obtained with different random seeds are provided (seed5, seed10).
