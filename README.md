# Word2Vec

Word2Vec is a project i have wanted to work on for a very long time. It was one of the biggest things in the NLP world when it was released back in 2013. Fancy name, big company backing it, it was a runaway hit. Word2Vec bridged the gap between linguistics and mathematics one step closer. 

## What is Word2Vec?
Word2Vec is a model that essentially converts words into meaningful vectors. Sounds trivial, but it helped solve a lot of issues back then and still continues to do so. 

Let us take a deeper dive at what we mean by meaningful vectors. We have many ways we could define the meaning of a word in linguistics. The most common way of doing so is by using a dictionary. In a dictionary, we have word, and a string of words explaining what the initial word meant. This is pretty simple to understand to the human mind. Computers on the other hand cannot really comprehend this. The easiest explanation to why it cant would be, computers cannot understand words in the first place. This entails, we cannot break down the meaning of a word using simpler words, because computers do not understand any words in the first place. 

It is very clear that we cannot use the dictionary approach to teach a computer. Here is where a very famous linguist from born in the late 1800s called J.R Firth comes in to play. Mr. Firth has a very famous quote "*You shall know a word from the company it keeps.*". The underlying meaning is - the meaning of a word is its use in the language. This is the quote that we build this entire model of Word2Vec on. 

### Hyperparameters: 
- Vector Size: 60
- Number of Word Vectors: 5000 (4999 + unk)
- Context window: 5


