# README:

For this assignment, 
I first tried locked drop-out and normalization for regularizations. I used the basic model architecture and trained it for 70 epochs, which gives me an LD of 13.62. 

To improve the performance, I add more regularization: (1) weight tying inside the encoder for the embedding layer and classification layer. To ensure that our model is large enough and not requiring the hidden size and embedding size to be the same, we add another linear layer before the classification layer. (2)weight initialization mentioned in the paper LAS for LSTM layers with uniform(-0.1,0.1) distribution. I train the model for 70 epochs and let the scheduler kick in at the 40th epoch, which s. This experiment gives an LD of 11.88.

For the third experiment, I used time and frequency masking to achieve data augmentation. Moreover, I also increase the hidden size for the encoder and decoder to 128. For this experiment, I found that the attention plot converged into a diagonal much faster. I have achieved an LD of around 15 for only 35 epochs, which is much faster than the previous two experiments. The final LD that I achieved was 10.14, which is the best distance that I got.

For future experiments, we can increase the hidden size for both the encoder and decoder if we have access to a better GPU. We can also add a locked drop-out between the layers of LSTMCell in the decoder to achieve a lower LD.





