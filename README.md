# uncertainty-in-image-seg

Experimenting with Uncertainty Quantification in Image Segmentation Tasks. The project is based on the [Satellite Images of Water Bodies](https://www.kaggle.com/christianmolliere/uncertainty-quantification-of-image-segmentation/data) dataset, which is available on Kaggle.

<img src="https://github.com/chrismolli/uncertainty-in-image-seg/raw/main/img/ex4.png" align="center" width="512">

## TL;DR
The predictive uncertainty of a model let's us take insight in the confidence of a model's inference. This enables us to build safer ML systems, and makes entailing decisions more transparent by giving explicit information on how well the input data has been represented during training.

## Theory
The uncertainty of our model is parted in two categories, which sum up to what is called <b>predictive uncertainty (PU)</b>.

- <b>Aleatoric Uncertainty (AU)</b>; Occurring as a noise in our observations, either homogenously or locally.
- <b>Epistemic Uncertainty (EU)</b>; Occurring through biased datasets and can be decreased by adding more samples.

They are various ways to estimate these terms; This notebook uses MC dropout to estimate the present epistemic uncertainty. For more detailed insight on different techniques under research check out [[Abdar2021](https://arxiv.org/abs/2011.06225)].

## Results
A modified version of the U-Net model [[Ronneberger2015](https://arxiv.org/abs/1505.04597)] was used to estimate the epistemic uncertainty present in a Earth Observation dataset. It is enhanced using batch normalization for better performance and combined with spatial dropout to allow for estimation of the <b>EU</b> term. The task of the model is to create a binary classification, segregating water and non-water areas in the input image. The model is trained using BCE loss and a Nadam optimizer.

Some of the results are shown below. Check the [notebook on Kaggle](https://www.kaggle.com/christianmolliere/uncertainty-quantification-of-image-segmentation) for the full results.

<p align="center">
  <img src="https://github.com/chrismolli/uncertainty-in-image-seg/raw/main/img/cbar.png" align="center" width="512">
  <img src="https://github.com/chrismolli/uncertainty-in-image-seg/raw/main/img/ex1.png" align="center" width="512">
  <img src="https://github.com/chrismolli/uncertainty-in-image-seg/raw/main/img/ex2.png" align="center" width="512">
  <img src="https://github.com/chrismolli/uncertainty-in-image-seg/raw/main/img/ex3.png" align="center" width="512">
  <img src="https://github.com/chrismolli/uncertainty-in-image-seg/raw/main/img/ex4.png" align="center" width="512">
  <img src="https://github.com/chrismolli/uncertainty-in-image-seg/raw/main/img/ex5.png" align="center" width="512">
  <img src="https://github.com/chrismolli/uncertainty-in-image-seg/raw/main/img/ex6.png" align="center" width="512">
  <img src="https://github.com/chrismolli/uncertainty-in-image-seg/raw/main/img/ex7.png" align="center" width="512">
  <img src="https://github.com/chrismolli/uncertainty-in-image-seg/raw/main/img/ex8.png" align="center" width="512">
</p>
