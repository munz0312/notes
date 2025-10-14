## Tokenisation

Several problems with tokenisation. How do we know what counts as 1, 2 or 3 tokens. Using the simple whitespace delimited sequence is too simplistic.
Some languages don't have whitespace, some are read right-to-left and left-to-right or both.
![[Pasted image 20251014111729.png]]
![[Pasted image 20251014111744.png]]

Tokenisation should be simple and quick. It's more about where to split, not where to combine.

## Normalisation
Parsnips and parsnip have the same meaning, so they shouldn't take up two tokens.

Normalise words:
- different tenses {walks, walked, walking, walk} -> walk
- abbreviations/acronyms {B.B.C, BBC} -> BBC
- punctuation {multinational, multi-national} -> multinational
- different spellings/forms {Duesseldorf, Düsseldorf, Dusseldorf} -> Dusseldorf

Case folding - sending every word to lower/uppercase. Could be good, could be bad as we could lose meaning (names, organisations, places).

Lemmatisation - reduction to dictionary 'headword' to form a lemma. 
We could use a dictionary, but lookup may be slow. 
Morphological analysis - break down a word to get its stem and affixes (prefix, suffix) 
unhappiness -> un + happy + ness

![[Pasted image 20251014112824.png]]
'lives' could be 'life', the noun in plural, or 'live', the verb in present tense, 3$^{rd}$ person. Context dependent.

Stemming - chops the ends of words to remove suffixes (ness in unhappiness) to turn similar forms to a canonical form. 

However it can yield things which aren't words. Understemming can fail to group together related forms. Overstemming can group unrelated forms.

![[Pasted image 20251014113510.png]]

Character ngrams can be used for alternative methods of tokenisation.
- Character-level tokenisation: character n-grams (character substrings)
- Subword tokenisation: tokens can be parts of words as well as whole words
We can use a dictionary of suffixes/prefixes to identify them.

The BPE token learner lets us use the data to learn how to tokenise. Look for the most common adjacent pairs of letters from the alphabet eg. 'A' 'B'.
For every text in the corpus, replace adjacent instances of 'A' 'B' to 'AB', and add 'AB' to the vocabulary.

![[Pasted image 20251014114616.png]]

Repeat these 'merges' for some number of times.
This results in:
- Most words and subwords (affixes?) will be represented in the vocabulary as complete symbols.
- Very rare words (including unknown words) will be represented by their partss (subwords)
- Can control k to control size of vocabulary

We can use this on unseen words. If we come across "unlikeliest" and we don't have it in our vocabulary, we can break it down, and these words/subwords may be in our vocab 'un' + 'likely' + 'est'.

Then with the test data, the BPE segmenter
