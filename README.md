# What is Deep-Insight

 **A methodology to transform a non-image data to an image for convolution neural network architecture** 
![DI.png](OYu6RzwyNMSM)

We can read the details from the [Research paper](https://www.nature.com/articles/s41598-019-47765-6) and [YouTube Video](https://www.youtube.com/watch?v=411iwaptk24).



## Transform the data: Normalize between 0-1

Described as norm-2 in the DeepInsight paper supplementary information. 
 EDITED THE DENOMINATOR: ADDED 1 TO IT FOR MAKING ALL ZERO VARIABLES NOT THROW AN ERROR

```math
{\displaystyle \log (x+x.min+1) / (x.max +1) }
```

<div class="alert">LogScaler.fit ( X :  np array or pandas df)</div>
<div class="alert">LogScaler.fit_transform (X :  np array or pandas df)</div>
<div class="alert">LogScaler.transform ( X/Y :  np array or pandas df)</div>

| Parameters         |      |
| ------------ |------------ |
| ``` X ```      | Train data with all Xs      |
| ```X/Y```      | Train/Valid/Test data with all Xs   |  




## Initializing the Image transformer 

<div class="alert">ImageTransformer  ( feature_extractor : string or a class instance , pixels : int for square matrix, tuple with height and width for rectangular matrix , random_state: int, n_jobs : int  ) </div>

| Parameters         |      |
| ------------ |------------ |
| ``` feature_extractor ```      |  string of value ('tsne', 'pca', 'kpca') or a class instance with method "fit_transform" that returns a 2-dimensional array of extracted features       |
| ```pixels```      | the size of the image matrix    |  
| ```random_state```        |  Determines the random number generator   | 
| ```n_jobs```       | Don't set to -1 for Dataikuu   |  


## Fit the Image transformer 

<div class="alert">ImageTransformer.fit (X : array-like or sparse matrix, plot : boolean) </div>

<div class="alert">image_trans.transform(X : array-like or sparse matrix, format : 'rgb' / 'scalar') </div>


| Parameters         |      |
| ------------ |------------ |
| ```X ```      | shape (n_samples, n_features), output of normalization       |
| ```plot```      | whether to produce a scatter plot showing the feature reduction, hull points, and minimum bounding rectangle    |  
| ```format```      | The format of the image matrix to return. 'rgb': 3 channels, 'scalar': 1 channel    |  



## Know the feature denisty 

Generate image matrix with feature counts per pixel.

<div class="alert">ImageTransformerInstance.feature_density_matrix()




<marquee direction="right">&lt;&gt;&lt;&nbsp;&hellip;</marquee>
<marquee direction="right">&lt;&gt;&lt;&nbsp;&hellip;</marquee>




# Appendix: How to use above? 
Please refer the example notebook.
[DI_TRAINING](jupyter_notebook:DI_TRAINING)

## Reference: 
 _Research Paper_ : https://www.nature.com/articles/s41598-019-47765-6
  _Git Repo_ : https://alok-ai-lab.github.io/DeepInsight/
  
  

