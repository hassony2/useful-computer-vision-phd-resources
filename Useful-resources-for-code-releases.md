# Advice for better code releases

This page is an effort to gather resources and advice on how to prepare your code for a release, and how to release it. 

Releasing your code is critical to maximize the impact of your research.
The easier it is to run and understand your code, the more it will be used.

</details>

## Useful resources

- [Papers with code advice on releasing research code](https://github.com/paperswithcode/releasing-research-code), targetted specifically for [NeurIPS 2020](https://nips.cc/Conferences/2020) but directly applicable to CVPR, ICCV, ECCV

<details> <summary> Personal comments </summary>

#### Handling dependencies

I typically use a conda environment with an environment.yml file so that the user can run

`conda env create -f environment.yml` to install all required dependencies. 

#### Releasing models

Github-releases is a great way to host your trained models.

I found the [github-release](https://github.com/aktau/github-release) tool useful for uploading models directly from the command line.

</details>

## Personal notes

#### Scripts

Decide which scripts you are going to publish.

Typically I like publish the following scripts:
- training/evaluation script, which allows to train a model in the same setting as reported in your paper
- demo script, which runs a forward pass on the model and visualizes the predictions
- any data preprocessing scripts that allow to transform datasets to the format expected by your training/evaluation/demo code


#### Cleaning code

##### Find and remove dead code

First **commit all your code** to make sure you don't loose anything useful in case you accidently delete files/snippets !

For future users, **dead code**, which isn't used anywhere, will be confusing (they will wonder if it is actually used somewhere or not, and will waste time trying to decipher the structure, and navigating larger files).

Dead code in python can be detected using [vulture](https://github.com/jendrikseipp/vulture) which can be installed with `pip install vulture`.

Suppose your structure looks something like :

```
train.py
eval.py
demo.py
src/
  models/
  scripts/
  ...
```

Run `vulture train.py eval.py demo.py src/`.

Vulture returns confidence scores that a given attribute/function is dead.

Check all the flagged functions/snippets/attributes and if they are indeed not needed, remove them !

I usually find that I can safely delete everything vulture flags as dead with confidence score higher than 50%.

Once you have finished deleting your dead code, check that your train/evaluation/demo scripts are still working.
