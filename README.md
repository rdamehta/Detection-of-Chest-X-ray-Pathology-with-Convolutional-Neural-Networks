# Capstone: Chest X-ray Classifier using the NIH Chest X-ray Dataset made public fall/winer of 2017

## sample X-rays

## Current Progress:
Framing the problem as one that is solvable with binary classification. Currently the model classifies Anterior-Posterior and Posterior-Anterior Chest X-rays as 'No Findings' or Abnormal with Findings. 

Currently testing on CNN architecture consisting of 3 convolutional Layers, Dense layer, dropout layer, Dense layer. A very simple topology that my laptop with 16gb and a nvidea 940mx can handle. 

Grayscaling, resizing, and normalizing images to 128 x 128 and 256 x 256 using openCV and comparing with 256x256x3 channel images. This was done to fit everything in RAM.

Convolutional Neural Network Topologies compared:
- Simple Naive Model as described above
- MobileNet as Baselayer
- InceptionV3 as Base Layer

3 Different images inputs vs 3 different topologies.

As of now InceptionV3 does the best job at predicting abnormal xrays with an AUC ROC of .62. Transfer significantly improved the predictive abilites over a simple CNN topology.

## Future Considerations:
- Try other CNN topologies published in Literature
- Latest research is showing very deep CNNs perform very well at image recognition and object detection. Dense121 is an very deep CNN
- Try to detect individual pathologies aka mutlticlass multioutput task

