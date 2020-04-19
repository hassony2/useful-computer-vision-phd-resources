# Advice for better code releases

This page is an effort to gather resources and advice on how to release code. 

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

#### Scripts

- training script, which allows to train a model in the same setting as reported in your paper
- demo script, which runs a forward pass on the model and visualizes the predictions

</details>

