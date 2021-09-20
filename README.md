# Recurrent-Neural-Network-Natural Language Processing


simple sentiment analysis:

-----------------------------

SOURCES:

-Use torch text from https://pytorch.org/text/stable/index.html  

-use repository from https://github.com/bentrevett/pytorch-sentiment-analysis  and open simple sentiment analysis in google colab

- building a machine learning model to detect sentiment (i.e. detect if a sentence is positive or negative) using PyTorch and TorchText. This will be done on movie reviews, using the IMDb dataset (http://ai.stanford.edu/~amaas/data/sentiment/).

1-Download Data

2- Prepairing Data (Tokenize Data using https://spacy.io/) , use Dat.field and split data to train and test and split train data to train and validation. For each word, you will have index and one-hot vector.

     Note: you have more than 100K unique words in the dataset. 100K*n (a vector for each word), this will results in large training time. So, select the most used 25K Words and if a word in sentence was not in dictionary of 25K, tag it as UN or unknown. To build 25K dictionary, use text.build.vocab.
     

3- Use RNN
  
  Before using RNN, Embedding was used to transform One-hot vector to a dense vector. dense vector is input of RNN. Embedding reduces dimention of one-hot vector. Acually, some words are synonym. so, a fully conection NN is used to reduce size and map sysnonym words to the same value.
  
  Each sentence has M words and each word has D embedding dim. assume batchsize e.x. 64. So we have a batch of 64 + or - which each sentence has length 100 and each word has embedding in size of D. We have 100 blocks. X1 is a embedding vector of a word.
If size of sentences are not same, sentences with smaller size will be padding.

BTW, we do not need to build blocks of RNN or input word by word. We will input sentences to RNN. 

RNN are fully connected networks. Assume you have 500 hidden neuron. so,  64 *500 is input for each block and if sentence lenght is 100, so output is 64*500*100

  For RNN:

-In pytorch website, go to Doc section, in search box , type rnn, you will see RNN-cell, LSTM cel, GRU cell,etc. The way, you need define RNN and each cell were described.
https://pytorch.org/docs/stable/generated/torch.nn.RNN.html?highlight=rnn#torch.nn.RNN

-In all recurrent NN, you work with a sequence (e.x. a sentence of words). Each word is a vector of size n. You will have input and hidden state and output in each RNN.


The accuracy of this NN is around 47%. We need to improve network.  Follow next steps.


simple sentiment analysis upgrade:

-----------------------------

Since accuracy of previous model was very low. so we will go on with

https://github.com/bentrevett/pytorch-sentiment-analysis/blob/master/2%20-%20Upgraded%20Sentiment%20Analysis.ipynb

you will see GloVe
https://nlp.stanford.edu/projects/glove/

which is unsupervised training method to get vector represenattion for words. This gives embedding layer a good initialization as it does not have to learn these relations from scratch

-using a different RNN architecture called a Long Short-Term Memory (LSTM)
https://colah.github.io/posts/2015-08-Understanding-LSTMs/

-using convolutional setiment analysis

https://github.com/bentrevett/pytorch-sentiment-analysis/blob/master/4%20-%20Convolutional%20Sentiment%20Analysis.ipynb

-multiclass sentiment analysis

https://github.com/bentrevett/pytorch-sentiment-analysis/blob/master/5%20-%20Multi-class%20Sentiment%20Analysis.ipynb

were uploaded.




