# Light Field Estimation
## Description
More traditional approaches, such as the one based on simplified Phong model without reflections terms (see [Image Forgery Detection](https://github.com/MatteoRubagotti/light-field-estimation/blob/main/image-forgery-detection.pdf), section “Light direction (2-D)”):

$$ \begin{equation} I(x,y)=N(x,y) \cdot L + A  \end{equation}$$
In the equation $(1)$, $I(x,y)$ is the pixel intensity at point $(x,y)$; $N(x,y)$ represents the surface normal evaluated at $(x,y)$, $L$ is the source light vector, which is supposed constant along the image (from the assumption of single infinitely far light source), and $A$ is a term that takes into account the ambient light contribution. 
The unknown parameters of the model must be estimated from the data available in the image. \
**Note**:  $N(x,y)=[N_1 (x,y),N_2 (x,y),N_3 (x,y)]$ and $L=(L_1,L_2,L_3)$ are 3D vectors that should be estimated from a 2D image. This is a strongly ill-conditioned problem, as the projection of a 3D scene onto a 2D plane brings to a loss of information.
We can use the following (**strong**) assumption: _the normals evaluated at the boundaries of objects lie in the image plane_; in this case the $N_3$ component is ~ $0$, and can be neglected. Thus, the model $(1)$ can be simplified and the parameters that need to be estimated become only three: $N_x$, $N_y$ and $A$. In this project we used two different methods for estimation: **Least Squares** and **RANSAC**.

## Jupyter Notebook
A detailed description of all the steps can be found inside the IPython Notebook below:
* [Light Field Estimation](https://github.com/MatteoRubagotti/light-field-estimation/blob/main/Light_Field_Estimation.ipynb)