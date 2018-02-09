# Recurrent Neural Networks

### 1
Suppose your training examples are sentences (sequences of words). Which of the following refers to the jth word in the ith training example?
> x(i)<j>

### 2
Consider this RNN:
![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/WVhjoPCuEee5Rg5IFJ7l8g_a7b6030c6e5a53b431fee7aaabecd9bd_Screen-Shot-2018-01-03-at-5.48.26-PM.png?expiry=1518307200000&hmac=EnOADmaRCNDcqgj5JRdfM23Mza_H5XOqwxA9Nyc4lQ0)
This specific type of architecture is appropriate when:

> Tx = Ty

### 3
To which of these tasks would you apply a many-to-one RNN architecture? (Check all that apply).
![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/K59CdPCvEee7LQrRPHr2wA_4549ad1b1b590371eb3502e158a02447_Screen-Shot-2018-01-03-at-5.54.27-PM.png?expiry=1518307200000&hmac=iv9deWL3ZaQ9DVO-G_xfyfh-mz8nk1OfR_Ffzc6NuFo)

> Sentiment classification (input a piece of text and output a 0/1 to denote positive or negative sentiment)

> Gender recognition from speech (input an audio clip and output a label indicating the speaker’s gender)

### 4
You are training this RNN language model.
![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/cxeeLPCvEee7YRLKCWJ4hg_bca1b05c70eece156b470abb2d0f0cad_Screen-Shot-2018-01-03-at-5.56.30-PM.png?expiry=1518307200000&hmac=m6ifH9iaPhmZs41pE4dJsJ8ykVH1tIa33sIHk1e3OAY)

> Estimating P(y<t> | y<1>, y<2>,..., y<t-1>)

### 5

You have finished training a language model RNN and are using it to sample random sentences, as follows:
![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/zOkWE_CvEee5Rg5IFJ7l8g_f36533d67eb6590d5bcb7021d88493eb_Screen-Shot-2018-01-03-at-5.58.53-PM.png?expiry=1518307200000&hmac=78twMrV-rt4_bzRrRBL4r8JS9p2n8eGvTXbjtln24BQ)

What are you doing at each time step t?

> (i) Use the probabilities output by the RNN to randomly sample a chosen word for that time-step as y_hat<t>. (ii) Then pass this selected word to the next time-step.

### 6

You are training an RNN, and find that your weights and activations are all taking on the value of NaN (“Not a Number”). Which of these is the most likely cause of this problem?

> Exploding gradient problem

### 7
Suppose you are training a LSTM. You have a 10000 word vocabulary, and are using an LSTM with 100-dimensional activations a<t>. What is the dimension of Γu at each time step?

> 100

### 8
Here’re the update equations for the GRU.
![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/y-VsavCwEeeVOQpGYM3DAA_b10afdb5d35702d711338d5b72ce5be7_Screen-Shot-2018-01-03-at-6.05.56-PM.png?expiry=1518307200000&hmac=vX2INxLuV_nTKjysRXOPjf96waGDZu6HtqSSGkrmLII)
Alice proposes to simplify the GRU by always removing the Γu. I.e., setting Γu = 1. Betty proposes to simplify the GRU by removing the Γr. I. e., setting Γr = 1 always. Which of these models is more likely to work without vanishing gradient problems even when trained on very long input sequences?

> Betty’s model (removing Γr), because if Γu approximately equals 0 for a timestep, the gradient can propagate back through that timestep without much decay.

### 9
Here are the equations for the GRU and the LSTM:
![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/ZJgnEfCxEeeVOQpGYM3DAA_2552c64114ba9a4a065a54e8e4855b39_Screen-Shot-2018-01-03-at-6.10.24-PM.png?expiry=1518307200000&hmac=ra2iU4doRnX0FCt79M4PToR_On3FND0twEUJTDNdgps)
From these, we can see that the Update Gate and Forget Gate in the LSTM play a role similar to _______ and ______ in the GRU. What should go in the the blanks?

> Γu and 1 - Γu

### 10

You have a pet dog whose mood is heavily dependent on the current and past few days’ weather. You’ve collected data for the past 365 days on the weather, which you represent as a sequence as x<1>,...,x<365>. You’ve also collected data on your dog’s mood, which you represent as y<1>,...,y<365>. You’d like to build a model to map from x->y. Should you use a Unidirectional RNN or Bidirectional RNN for this problem?

> Unidirectional RNN, because the value of y<t> depends only on x<1> through x<t>, but not on x<t+1> through x<365>
