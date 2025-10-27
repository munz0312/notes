Word sense refers to one of the meanings of a word.
Word sense disambiguation is the NLP task of selecting the correct sense from a set of multiple possibilities, given the text it appears in.

Applications of WSD
- Machine translation 
- Search engines

There are two typical types of approach for WSD:
- Knowledge-based - use external lexical resources eg. dictionaries, thesaurus.
- Supervised machine learning - use labelled training data

Most dictionaries have a machine-readable format
WordNet is a large lexical database of English

Lesk Algorithm is used to disambiguate the word sense using the context with the dictionary definitions.
- Retrieve all word senses of the word to be disambiguated from the dictionary
- Calculate the overlap or similarity between each sense definition and the current context
- Choose the sense that leads to the highest overlap
![[Pasted image 20251021112723.png]]
![[Pasted image 20251021112858.png]]
![[Pasted image 20251021113155.png]]
![[Pasted image 20251021113553.png]]
![[Pasted image 20251021113819.png]]
![[Pasted image 20251021114830.png]]

Sequence labelling is the task of assigning the sense labels to words.
![[Pasted image 20251021120248.png]]
![[Pasted image 20251021120229.png]]





