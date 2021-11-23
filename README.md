# Light Field Estimation
## Description
More traditional approaches, such as the one based on simplified Phong model without reflections terms (see [Image Forgery Detection](https://github.com/MatteoRubagotti/light-field-estimation/blob/main/image-forgery-detection.pdf), section “Light direction (2-D)”):
<center>
<img src="https://render.githubusercontent.com/render/math?math=I(x,y)=N(x,y) \cdot L %2B A \qquad (1)"> 
</center>
<p align="justify">
<img src="https://render.githubusercontent.com/render/math?math=I(x,y)"> is the pixel intensity at point <img src="https://render.githubusercontent.com/render/math?math=(x,y)">; <img src="https://render.githubusercontent.com/render/math?math=N(x,y)"> represents the surface normal evaluated at <img src="https://render.githubusercontent.com/render/math?math=(x,y)">, <i>L</i> is the source light vector, which is supposed constant along the image (from the assumption of single infinitely far light source), and <i>A</i> is a term that takes into account the ambient light contribution. 
The unknown parameters of the model must be estimated from the data available in the image.
<p>
<b>Note</b>: <img src="https://render.githubusercontent.com/render/math?math=N(x,y)=[N_1 (x,y),N_2 (x,y),N_3 (x,y)]"> and <img src="https://render.githubusercontent.com/render/math?math=L=(L_1,L_2,L_3)"> are 3D vectors that should be estimated from a 2D image. This is a strongly ill-conditioned problem, as the projection of a 3D scene onto a 2D plane brings to a loss of information.
We can use the following (<b>strong</b>) assumption: <i>the normals evaluated at the boundaries of objects lie in the image plane</i>; in this case the <img src="https://render.githubusercontent.com/render/math?math=N_3"> component is ~ 0, and can be neglected. Thus, the model (1) can be simplified and the parameters that need to be estimated become only three: <img src="https://render.githubusercontent.com/render/math?math=N_x">, <img src="https://render.githubusercontent.com/render/math?math=N_y"> and <img src="https://render.githubusercontent.com/render/math?math=A">. In this project we used two different methods for estimation: <b>Least Squares</b> and <b>RANSAC</b>.
</p>

## Jupyter Notebook
<p align="justify">
A detailed description of all the steps can be found inside the IPython Notebook below:</p>

* [Light Field Estimation](https://github.com/MatteoRubagotti/light-field-estimation/blob/main/Light_Field_Estimation.ipynb)