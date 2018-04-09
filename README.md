# Chest X-ray Classifier using Convolutional Neural Networks

<br>
<br>
<p align="center">
  <img src="https://github.com/rdamehta/Capstone/blob/master/readmeX.PNG" 
       width="200" height="250">
  <img src="https://github.com/rdamehta/Capstone/blob/master/readmeCHECK.PNG" 
       width="210" height="250">
</p>
<br>

<a id = 'over'></a>

## Table of Contents
- [Introduction](https://github.com/rdamehta/capstone#introduction)

- [Prerequisites](https://github.com/rdamehta/capstone#prerequisites)

- [Model Topology](https://github.com/rdamehta/capstone#model-topology)

- [Model Comparison and Results](https://github.com/rdamehta/capstone#model-comparison-and-results)

- [Final Thoughts and Future Considerations](https://github.com/rdamehta/capstone#final-thoughts-and-future-consideration)

### Introduction
---
Chest x-rays are one of the most ubiquitous medical imaging procedures and can reveal essential clinical information about a patient for physicians and medical proffesionals. The goal of this project was to build a model that could predict whether or not disease was present in an frontal Chest Xray using various convolutional neural networks 
#### Data
The ChestXnet Dataset was released in Fall of 2017 and gave the public access to over 100, 000 Chest Xrays image. The full dataset is available on [kaggle](https://www.kaggle.com/nih-chest-xrays/data), and the sample dataset of as well as a sample set of over 5000 Xrays is available [here](https://www.kaggle.com/nih-chest-xrays/sample/data).

There is also a csv available with each row corresponding to each image and each column either patient or image data corresponding to each image. The [csv](https://www.kaggle.com/nih-chest-xrays/data/downloads/Data_Entry_2017.csv/3) is also available on kaggle. 
### Prerequisite
---
- `pip install tensorflow`
- `pip install keras`
- `pip install sklearn` 
- `pip install pillow`
- `pip install opencv`
- `pip install numpy`
- `pip install pandas`

### Model Topology
---

 1. **Topology of a simple CNN**
<p align="center">
  <img src="https://github.com/rdamehta/Capstone/blob/master/Presentation%20Files/Typical_cnn.png" 
       width="650" height="200">
  In this project the Simple CNN topology consisted of: 
  
    Conv2d 
    Pooling
    Conv2d
    Pooling
    Conv2d
    Flatten to Dense
    Dropout
    Dense(outputs)
  
   2. **MobileNet Topology**: mobilenets were designed to be used on Android and iOS platforms. The full MobileNets network has 30 layers.
  <img src="https://github.com/rdamehta/Capstone/blob/master/Presentation%20Files/mobilenet.png"
       width="650" height="200">
  <img src="https://github.com/rdamehta/Capstone/blob/master/Presentation%20Files/mobile_net_table.png" width="400" height="400">


  3.  **InceptionV3 architecture** 
  
  <img src = "https://github.com/rdamehta/Capstone/blob/master/Presentation%20Files/inceptionv3.png"
       width="650" height="200">
      
    
</p>



### Model Comparison and Results
---
The images were preprocessed using opencv by grayscaling, resizing, and normalizing images to 128 x 128 x 1, 256 x 256 x 1, and  256 x 256 x 3 channel images.

Convolutional Neural Network Topologies compared:
- Simple Naive Model as described above
- MobileNet as Baselayer
- InceptionV3 as Base Layer

Results:
<p align="center">
  <img src="https://github.com/rdamehta/Capstone/blob/master/Presentation%20Files/comparisonmatrix.PNG" >
</p>



### Final Thoughts and Future Consideration
---

As of now InceptionV3 does the best job at predicting abnormal xrays with an AUC ROC of .62. Transfer significantly improved the predictive abilites over a simple CNN topology. It's interesting to note the false positives and false negatives of each model. Depending on the clinical scenario one could argue having more false negatives is problematic and more insiduous when trying to warrant further investigation.

Finally it's well documented that there are serious issues with the dataset. [This blog](https://lukeoakdenrayner.wordpress.com/2017/12/18/the-chestxray14-dataset-problems/) discusses how this dataset is not labeled correctly. In fact Stanford’s famous paper [CheXNet: Radiologist-Level Pneumonia Detection on Chest X-Rays with Deep Learning](https://stanfordmlgroup.github.io/projects/chexnet/) used the same ChestXnet database, but had  panel of radiologists read over them and relabel them to ensure accuracy. Despite this shortcoming there is still utility in using the dataset, least of which in demonstrating the importance of good data.

