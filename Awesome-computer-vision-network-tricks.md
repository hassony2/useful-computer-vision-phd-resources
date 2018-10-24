# Neural networks tricks 

### Working with batchnorm

- At train time batchnorm uses batch statistics, therefore results will be differnt if you change the batch size
- When finetuning with a different batch-size this can instroduce additional noise and degrade both the train and validation statistics (because it doesn't fit in memory otherwise for instance) a solution is to set my network in evaluation mode  (`model.eval()` in Pytorch)
- If training statistics are different from test statistics, this can cause outliers in the test set (predictions are completely wrong). This happened to me for instance with synthetic data when backgrounds were sampled from different sources. The solution might be also to fix the batchnorms (when weights are pretrained on ImageNet or other task) so that these statistics are always used.

