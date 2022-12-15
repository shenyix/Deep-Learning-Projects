# README:

For this assignment, 
I have first tried locked drop out and normalization for regularizations. I used the basic model architecture and train it for 70 epochs, which gives me a LD of 13.62. 

To improve the peformance, I add more regularization: (1) weight tying inside the encoder for the embedding layer and classification layer. To ensure that our model is large enougth and not requiring the hidden size and embedding size to be the same, we add another linear layer before the classfication layer. (2)weight initialization mentioned in the paper LAS for LSTM layers with uniform(-0.1,0.1) distribution. I train the model for 70 epochs, and let scheduelr kick in at 40th epoch, which s. This experiment gives a LD of 11.88.

For the third experiment, I tried to used time masking and frequency masking to achieve data augmentation. Moreover, I also increase the hidden size for encoder and decoder for 128. For this experiment, I found that the the attention plot converged into a diagonal much faster. I have achieved a LD around 15 for only 35 epochs, which is much faster than the previous two experiment.

For future experiment, we can increase the hidden size for both encoder and decoder if we have access to better GPU. We can also try to add locked drop out between the layers of LSTMCell in the decoder to achieve a lower LD.





