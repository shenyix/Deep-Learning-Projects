# HW2P2: Face Classification and Verification

# README:
**Results:**

Best Recognition Accuracy: 89.45%

Best Verification Accuracy: 62.5%

**Architecture:**

I started with ResNet50, and it converges around 0.83. At first I thought it may be the case that I have to train it for longer time, and increase the epochs and manually decrease the learning rate. However, none of these help, so I decide to change into another architecture: ResNet34. ResNet34 requires shorter training time for each epoch (8 min), as it has less layers. The model converges around %88 for 100 epoch. I add center loss to fine tune the model for 30 epochs, and it reaches the final precision for recognition.

I did not tweak the model architecture or data prepocessing part just for verification. In fact, the precision for verification increase as the precision for recognition increase in my experiment. 

**Scheduler:**

I used ReduceLRonPlateu, with patience 3 and factor 0.7. The role of scheduler is very important in this assignment. From what I can recollect, I think the reason that ResNet50 does not work for me is the scheduler I use have a patience of 1 and factor 0.1, which makes it decrease too fast and stucks at a local minimum. 


**How to run the code**:

Just running each cell sequentially.



