# Beautiful visualizations

This page is an effort to gather the advice I can find on how to create ans share beautiful visualizations to convey your results.

## Beautiful figures

[Inkscape](https://inkscape.org/) with [latex equation extensions](https://writetex.tk/)

## Beautiful 3d visualizations

- Avoid matplotlib when working with 3D meshes, I found it has troubles reasoning about visibility for multiple meshes
- in [jupyter notebooks](http://jupyter.org/), a good option in [pythreejs](https://github.com/jupyter-widgets/pythreejs), note that it is not available in pure python outside jupyter.
- to share obtained visualization
  - save the jupyter notebook **make sure to save using Save with widgets**
  - host the .ipynb file to www.some/address
  - share using  [nbviewer](https://nbviewer.jupyter.org/) by giving it the www.some/address url


<details> <summary> Saving with widgets </summary>

Ctrl+Shift+F and then

![image](https://user-images.githubusercontent.com/10189060/48339686-113d8880-e669-11e8-8750-b294ce0f6c3c.png)

</details>

