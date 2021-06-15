# Headline_Generator

### Description  
In this model, our predictor will be quite simple, but it will provide some simple exposure to language processing, sequence data, and one of the classic architecture elements used to train sequences, recurrent neural networks or RNNs.  
Elements in the data have a relationship with what comes before and what comes after, and this fact requires a different approach. We're gonna generate headlines as the application of sequence data.  

### Steps Involved  
#### Reading the data  
Our dataset consists of headlines from the New York Times newspaper over the course of several months. We'll start by reading in all the headlines from the articles.  

#### Cleaning the data  
An important part of natural language processing (NLP) tasks (where computers deal with language), is processing text in a way that computers can understand it. We're going to take each of the words that appears in our dataset and represent it with a number. This will be part of a process called tokenization.  

#### Tokenization  
We separate a piece of text into smaller chunks (tokens), which in this case are words. Each unique word is then assigned a number, as this is a way that our model can understand the data.  

#### Creating Sequences  
We've tokenized the data, turning each word into a representative number, we will create sequences of tokens from the headlines. These sequences are what we will train our deep learning model on.  

#### Padding Sequences  
This sequences are of various lengths. For our model to be able to train on the data, we need to make all the sequences the same length. To do this we'll add padding to the sequences.  

#### Creating Predictors and Target  
We also want to split up our sequences into predictors and a target. The last word of the sequence will be our target, and the first words of the sequence will be our predictors.  
#### Creating the Model  
For our model, we're going to use a couple of new layers to deal with our sequential data.  
1. Embedding Layer :  
This layer will take the tokenized sequences and will learn an embedding for all of the words in the training dataset. Mathematically, embeddings work the same way as a neuron in a neural network, but conceptually, their goal is to reduce the number of dimensions for some or all of the features. In this case, it will represent each word as a vector, and the information within that vector will contain the relationships between each word.  

2. Long Short Term Memory Layers
Traditional RNNs suffer from the issue of more recent information contributing more than information from further back. LSTMs are a special type of recurrent layer that are able to learn and retain longer term information.  

#### Compiling the Model  
We compile our model with categorical crossentropy, as we're categorically predicting one word from our total vocabulary.  

#### Training the model  
We will train our model with 30 epochs.  

#### Making Predictions  
We will make the predictions for single words first.  

#### Generate New Headlines  
We're able to predict new words, we will make a function that can predict headlines of more than just one word.  

### Results  
The results may be a bit underwhelming after 30 epochs of training. We can notice that most of the headlines make some kind of grammatical sense, but don't necessarily indicate a good contextual understanding. The results might improve somewhat by running more epochs.


