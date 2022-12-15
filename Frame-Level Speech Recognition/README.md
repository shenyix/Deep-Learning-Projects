# HW1: Frame-Level Speech Recognition
In this homework, you will be working with MFCC data consisting of 15 features at each time step/frame. Your model should be able to recognize the phoneme occured in that frame.

# README

**Best Model Accuracy: 85.8%**

How to run the model: For Google Colab, simply clicking the right corner Runtime-> Run all will run the model.

**Model Structure:**
6 hidden layer, each has width 2048.
Activation: ReLu
Regularization:Dropout(0.1), BatchNorm1d
Learning rate:0.001
Context:30
Batch size:2048
optimizer: AdamW
Epoch:30
Parameter size:19.0464M

**Experiments:**

Hidden Layer size selection: I started with using multiple hidden layer with small width such as 512 and 256, and it turns out that the accuracy is only 78%, so I decide to try using wider hidden layer. Changing to 2048 increase the parameter size significantly, and the accuracy raise to 82%.

Context: I adjust my context for several experiments(using size 15,30, and 45). Size 30 gives the best result.

optimizer: I first using Adam as my optimizer. After discussing with TA and using AdamW instead, my accuracy increase from 82 to 83.

Epochs:

I start with using 10 epochs only, and it limits the amount of accuracy that the model can reach. After increase the epoch size into 30, My model increase to 85.8 from 83. 


For information related to all the experiments that I run, please visit:
WandB: https://wandb.ai/shenyix/hw1p2
