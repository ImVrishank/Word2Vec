# VecStreetBoys
VecStreetBoys is my implementation of the Word2Vec model using the Bag-of-Words algorithm.

Word2Vec is a project i have wanted to work on for a very long time. It was one of the biggest things in the NLP world when it was released back in 2013. Fancy name, big company backing it, it was a runaway hit. Word2Vec bridged the gap between linguistics and mathematics one step closer. 

## What is Word2Vec?
Word2Vec is a model that essentially converts words into meaningful vectors. Sounds trivial, but it helped solve a lot of issues back then and still continues to do so. 

Let us take a deeper dive at what we mean by meaningful vectors. We have many ways we could define the meaning of a word in linguistics. The most common way of doing so is by using a dictionary. In a dictionary, we have word, and a string of words explaining what the initial word meant. This is pretty simple to understand to the human mind. Computers on the other hand cannot really comprehend this. The easiest explanation to why it cant would be, computers cannot understand words in the first place. This entails, we cannot break down the meaning of a word using simpler words, because computers do not understand any words in the first place. 

It is very clear that we cannot use the dictionary approach to teach a computer. Here is where a very famous linguist from born in the late 1800s called J.R Firth comes in to play. Mr. Firth has a very famous quote "*You shall know a word from the company it keeps.*". The underlying meaning is - the meaning of a word is its use in the language. This is the quote that we build this entire model of Word2Vec on. 

## How does the Word2Vec model work?

### Hyperparameters: 
- Vector Size: 60
- Number of Word Vectors: 5000 (4999 + unk)
- Context window: 5


We are building a Bag of Words (BoW) model. Here is how it works in theory. We have a huge corpus of clean text and a pointer which moves from the beginning to the end of the corpus, word-wise. 

We first make a list of the most often used words in the corpus. We grab the first 4999 of these word that occur most often in the corpus. This is our vocabulary. We shall build word vectors for each of these words in the vocabulary. 

Next, we replace every single word that isn't in the top 4999 with a token unk. Now we only have 5000 unique words in the corpus. 

We are now going to train a neural network with 10 (2 x context length) neurons in the input layer. The singular hidden layer has 60(vector size) neurons. Now we have a singular neuron as the output layer. 

Let us assume the pointer is at the *nth* word, we start grabbing the context words surrounding it. Since our context length is 5, we grab 5 words before and 5 words after the word the pointer is pointing to. We are now going to compare each of these words with our vocabulary to make a one-hot encoding vector for each of the 10 words. Now, we add these word vectors element wise, The vector of 5000 cells we get after doing this, will act as our input to the neural network's input layer. The label for the output will be the one hot encoding of the word the pointer is pointing to. 
