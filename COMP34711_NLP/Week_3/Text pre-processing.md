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

![[Pasted image 20251014120709.png]]

Then with the test data, use this vocabulary to tokenise the text. We can use this on unseen words. If we came across 'l o w e r_', this would be tokenised as 'low' and 'er_', and we'd be able to estimate the definition of this word.

---

## Part of Speech (POS)
These are things like nouns, verbs, adjectives. Features of the grammar of a language.
![[Pasted image 20251014121624.png]]
'Open' and 'closed' word classes. Open word class get new words - 'covid', 'Internet'
Closed does not. 'the', 'if', 'he', 'she'

![[Pasted image 20251014121934.png]]

Words can be ambiguous so POS tagging can be used to alleviate this. It can be simple tags - verbs, adjectives, nouns etc... but there are more complex tag sets C5, C7, Penn Treebank
![[Pasted image 20251014122724.png]]

### Rule-based tagging
- Start with a dictionary
- Assign all possible tags to words from the dictionary/ vocabulary
- Apply rules to selectively eliminate tags, leaving the correct tag for each word
### Stochastic tagging
- Probabilistic approach - how often does a word appear in its different forms
- How likely is that word to appear as one of its forms, given that the previous word is (for example) a pronoun, determiner
![[Pasted image 20251014123121.png]]
Calculating the probabilities:
	What is the probability of word i given that it has tag i, multiplied by the probability of seeing tag i given the previous word had tag i-1.
![[Pasted image 20251014124424.png]]

![[Pasted image 20251014123516.png]]
![[Pasted image 20251014124219.png]]

Transformation based learning:
- Start with a simple solution to the problem
- iteration: apply transformations to get best results, eg by correcting errors (from the simple solution)
- stop when no more (or little) improvement can be made

The transformation rules are automatically induced from training.

![[Pasted image 20251021110906.png]]
![[Pasted image 20251021111306.png]]
![[Pasted image 20251021111317.png]]
![[Pasted image 20251021111333.png]]
*example transformation table*

Once the rules/transformations are learnt:
- Apply the initial tagging
	- Most frequent POS tags
- Apply the rewrite rules based on the training data.