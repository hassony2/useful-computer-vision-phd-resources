# Neural networks tricks 

### Working with batchnorm

- At train time batchnorm uses batch statistics, therefore results will be different if you change the batch size
- When finetuning with a different batch-size  (because the original batch size doesn't fit in memory otherwise for instance) this can introduce additional noise and degrade both the train and validation statistics. A solution is to set my network in evaluation mode  (`model.eval()` in Pytorch).
- If training statistics are different from test statistics, this can cause outliers in the test set (predictions are completely wrong). This happened to me for instance with synthetic data when backgrounds were sampled from different sources. The solution might be also to fix the batchnorms (when weights are pretrained on ImageNet or other task) so that these statistics are always used (for jnstance by keeping it in eval() mode).
- Fully **Freezing** batchnorm (meaning same image always gives same output in network that is frozen) requires to put momentum to 0, otherwise running statistics are still updated if you ever put the network in train mode.

```
def rec_freeze(model):
    for name, child in model.named_children():
        for param in child.parameters():
            param.requires_grad = False
    for module in model.modules():
        if isinstance(module, torch.nn.modules.batchnorm._BatchNorm):
            module.momentum = 0
    rec_freeze(child)
```

- Maybe the problems from BatchNorm come from using it in a regression setting ? 

> We found training with batch-normalization [28] to be unstable and applied the weight-normalization technique instead [46].  [DeepSDF: Learning Continuous Signed Distance Functions for Shape Representation](https://arxiv.org/pdf/1901.05103.pdf)


### Working with Adam

- Although I train with Adam and learning rate is adaptative I still observe (positive) jumps in accuracy right after the learning rate decay. It is not clear however whether it improves the final performance
