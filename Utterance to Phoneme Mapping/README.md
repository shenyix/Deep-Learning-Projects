#README:

The parameter I found essential to adjust is the hidden-size of lstm. I started with 256 3 layers, which is too small and insufficient to pass through the information. I trained the model for 50 epochs and achieved the Levenshtein distance of 14.

I slightly increase it to 512, which still needs to be bigger; the Levenshtein distance is 13, which is only a small improvement.

After I increased the Levenshtein distance to 700, the largest size my GPU can handle, the Levenshtein distance of the first epoch had already reached 8, and I trained it for ten epochs and reached the high cutoff.  One thing that needs to be mentioned is that I also dropped \<eos\> and <sos> for this experiment, which might be another reason my model improved significantly. 

The learning rate for the three experiments is 2e-3, and it doesn't take the scheduler to kick in to reach the high cutoff, so I will not introduce the scheduelr that I used. I did not use any transformation because the dataset is large enougth. The optimizer I used is Adamw. 
