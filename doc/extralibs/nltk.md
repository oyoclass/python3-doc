## nltk

nltk, or **Natural Language Toolkit**, is a natural language processing library for Python. It allows you to take normal written sentences or passages and **tokenize** them. After a passage has been tokenized, you can further analyze it for data and even identify parts of speech for individual words.

### Examples

#### Tokenizing a Sentence

The most basic thing we can do is **tokenize** a sentence. This will take an input string and break it down into an array of identifiable words:

```python
import nltk
# Depending on which functions you're using, nltk will require you to download
# certain resources. The errors in the console will tell you which ones you
# need
nltk.download('punkt')

sentence = '''
It's time to go to school! Grab your bag and get on the bus.
'''
tokens = nltk.word_tokenize(sentence)

print(tokens)
```

Output:

```text
['It', "'s", 'time', 'to', 'go', 'to', 'school', '!', 'Grab', 'your', 'bag',
'and', 'get', 'on', 'the', 'bus', '.']
```

Note that nltk may identify certain words we may not normally consider to be their own words like **'s** or punctuations.

#### Tag Parts of Speech

After we break our sentence down to a token array, we can use nltk to further
analyze the sentence by marking parts of speech:

```python
import nltk
# Depending on which functions you're using, nltk will require you
# to download certain resources. The errors in the console will tell
# you which ones you need
nltk.download('punkt')
nltk.download('averaged_perceptron_tagger')

sentence = '''
It's time to go to school! Grab your bag and get on the bus.
'''
tokens = nltk.word_tokenize(sentence)
tagged = nltk.pos_tag(tokens)

print(tagged)
```

Each word in our array will now be a tuple of the original word, and the part of speech it represents:

```
[('It', 'PRP'), ("'s", 'VBZ'), ('time', 'NN'), ('to', 'TO'), ('go', 'VB'), ('to', 'TO'), ('school', 'NN'), ('!', '.'), ('Grab', 'VB'), ('your', 'PRP$'), ('bag', 'NN'), ('and', 'CC'), ('get', 'VB'), ('on', 'IN'), ('the', 'DT'), ('bus', 'NN'), ('.', '.')]
```

There are many supported parts of speech, but for this example the tags that appear in order are:

1. PRP - Personal Pronoun
2. VBZ - 3rd Person Singular Verb
3. NN - Singular Noun
4. TO - The word "to"
5. VB - Verb
6. . - Punctuation
7. PRP$ - Posessive Pronoun
8. CC - Conjunction
9. IN - Preposition
10. DT - Determiner

You can find a complete list in nltk's documentation

#### Identify Proper Nouns

Note: This example requires [NumPy](/extralibs/numpy) to be installed in your project.

We can tokenize a sentence, then use nltk to extract named entities from the sentence:

```python
import nltk
# Depending on which functions you're using, nltk will require you to download
# certain resources. The errors in the console will tell you which ones you
# need
nltk.download('punkt')
nltk.download('maxent_ne_chunker')
nltk.download('averaged_perceptron_tagger')
nltk.download('words')

sentence = '''
Mr. Brown went to the store to buy a TV, but forgot his wallet at home.
Christina came to give it to him.
'''
tokens = nltk.word_tokenize(sentence)
tagged = nltk.pos_tag(tokens)
entities = nltk.chunk.ne_chunk(tagged)

print(entities)
```

Will give the following output, where we can see all parts of the sentence relating to named people has the PERSON label:

```text
(S
  (PERSON Mr./NNP)
  (PERSON Brown/NNP)
  went/VBD
  to/TO
  the/DT
  store/NN
  to/TO
  buy/VB
  a/DT
  TV/NN
  ,/,
  but/CC
  forgot/VBD
  his/PRP$
  wallet/NN
  at/IN
  home/NN
  ./.
  (PERSON Christina/NNP)
  came/VBD
  to/TO
  give/VB
  it/PRP
  to/TO
  him/PRP
  ./.)
```

### Reference

-   [Natural Language Processing with Python](https://www.nltk.org/book/), the full O'Reilly published book at _nltk.org_
