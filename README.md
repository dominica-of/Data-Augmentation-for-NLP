# Data-Augmentation-for-NLP
This Python script performs a few different tasks related to text processing or text augmentation. It uses the NLTK (Natural Language Toolkit) library to aid in its processes.


1. **Synonym Replacement (synonym_replacement function)**: This function takes a list of words and a number 'n' as inputs. It creates a set of unique words that are not in the NLTK's list of English stopwords (common words like 'is', 'the', 'and', etc. that are often filtered out before processing). It then shuffles this list and iteratively replaces 'n' number of words in the original list with one of their synonyms, if any exist. The synonym is randomly chosen from a list of synonyms returned by the 'get_synonyms' function. If 'n' words have been replaced, it breaks from the loop. Finally, it rejoins the list into a sentence, splits it back into a list of words and returns it.

2. **Get Synonyms (get_synonyms function)**: This function takes a word as input and finds its synonyms using the WordNet lexical database of English words available in NLTK. It iterates over all the synonyms (synsets) of the word and for each synonym, it cleans it (replaces "_" and "-" with a space, converts to lowercase, and only retains alphabets) and adds it to a set. If the input word is in the set of synonyms, it removes it. It finally returns the synonyms as a list.

3. **Random Deletion (random_deletion function)**: This function takes a list of words and a probability 'p' as inputs. It creates a new list containing those words that pass a random selection test (a random number between 0 and 1 must be greater than 'p'). If no words pass the test, it returns a list containing one randomly chosen word from the original list. Otherwise, it returns the new list.

4. **Random Swap (random_swap function)**: This function takes a sentence (list of words) and a number 'n' as inputs. It swaps the positions of two randomly chosen words in the sentence, 'n' times. It then returns the sentence (list of words) with swapped words. 

Note: This code does not include the import statements for 'random' and 'wordnet' from NLTK, which are needed for the code to run. You'd typically see these at the top of the file:
```python
import random
from nltk.corpus import wordnet
```
