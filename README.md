# Recurrent-Neural-Network-Natural Language Processing

SOURCES:

-Use torch text from https://pytorch.org/text/stable/index.html  

-use repository from https://github.com/bentrevett/pytorch-sentiment-analysis  and open simple sentiment analysis in google colab

- building a machine learning model to detect sentiment (i.e. detect if a sentence is positive or negative) using PyTorch and TorchText. This will be done on movie reviews, using the IMDb dataset (http://ai.stanford.edu/~amaas/data/sentiment/).

1-Download Data

2- Preparing Data (Tokenize Data using https://spacy.io/) , use Dat.field and split data to train and test and split train data to train and validation. For each word, you will have index and one-hot vector.

     Note: you have more than 100K unique words in the dataset. 100K*n (a vector for each word), this will results in large training time. So, select the most used 25K Words and if a word in sentence was not in dictionary of 25K, tag it as UN or unknown. To build 25K dictionary, use text.build.vocab.
     

3- Use RNN
  
  Before using RNN, Embedding was used to transform One-hot vector to a dense vector. dense vector is input of RNN. Embedding reduces dimention of one-hot vector. Acually, some words are synonym. so, a fully conection NN is used to reduce size and map sysnonym words to the same value.
  
  Each sentence has M words and each word has D embedding dim. assume batchsize e.x. 64. So we have a batch of 64 + or - which each sentence has length 100 and each word has embedding in size of D. We have 100 RNN. X1 is a embedding vector of a word.

If size of sentences are not same. So sentences with smaller size will be padding.


  For RNN:

-In pytorch website, go to Doc section, in search box , type rnn, you will see RNN-cell, LSTM cel, GRU cell,etc. The way, you need define RNN and each cell were described.
https://pytorch.org/docs/stable/generated/torch.nn.RNN.html?highlight=rnn#torch.nn.RNN

-In all recurrent NN, you work with a sequence (e.x. a sentence of words). Each word is a vector of size n. You will have input and hidden state and output in each RNN.

