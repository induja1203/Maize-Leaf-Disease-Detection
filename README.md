Maize Leaf Disease Detection using Deep Learning :

Project Overview :

This project focuses on detecting and classifying maize (corn) leaf diseases using a deep learning approach inspired by YOLO architecture and enhanced with an attention mechanism.

The model identifies four classes:

* Common Rust
  
* Gray Leaf Spot
  
* Blight
  
* Healthy
  
The goal is to assist in early disease detection for improving crop health and agricultural productivity.

Key Features :

* Custom CNN inspired by YOLO detection framework
  
* Integrated \*\*Triple Attention mechanism\*\* for better feature learning
  
* Bounding box prediction for disease localization
  
* Multi-class classification
  
* Evaluation using accuracy, precision, recall, F1-score, and confusion matrix

Model Architecture :

Base Model: Custom CNN (YOLO-inspired architecture)

Designed for object detection + classification

Predicts:

*Bounding box coordinates

*Objectness score

*Class probabilities

Backbone (Feature Extraction)

*Convolutional Layers (Conv2D + BatchNorm + ReLU)

*Progressive feature extraction at multiple scales

*Integrated Triple Attention Mechanism:

   Channel Attention

   Spatial Attention

   Enhances important feature regions

Improves the model’s ability to focus on disease-affected areas of leaves

Neck (Feature Processing)

Feature refinement through deeper convolution layers

Maintains spatial information for localization

Head (Prediction Layer)

Fully Connected Layers

Outputs:

Bounding box coordinates (x, y, w, h)

Objectness score

Class probabilities (4 classes)

Activation Functions

ReLU (hidden layers)

Sigmoid (objectness score)

Softmax (class probabilities)

Loss Function (YOLO-style Loss)

Combination of:

Objectness Loss → Binary Cross-Entropy

Bounding Box Loss → Smooth L1 Loss

Classification Loss → Cross-Entropy

Optimizer

Adam Optimizer

Input & Output

Input: RGB leaf image (resized to 416 × 416)

Output: Multiple bounding boxes with class predictions

Key Advantage

The integration of Triple Attention allows the model to:

Focus on relevant disease regions

Improve classification accuracy

Enhance detection performance compared to standard CNNs

Technologies Used :

* Python
   
* PyTorch
  
* OpenCV
  
* NumPy
  
* Matplotlib
  
* Scikit-learn

Dataset :

The dataset was annotated using Roboflow and follows YOLO format.Dataset is not included in this repository due to size limitations.

Dataset Preparation :

1\. Download dataset from Roboflow or Kaggle further verify whether the dataset  is annotated or not if not kindly annotate using roboflow.

2\. Upload the zip file inside the colab.

3\. Run the code to extract automatically but i have used by mounting google drive, you can refer the notebook.

import zipfile

import os

zip\_path = "dataset/preprocessed\_dataset.zip"

extract\_path = "dataset/"

if os.path.exists(zip\_path):

&#x20;   with zipfile.ZipFile(zip\_path, 'r') as zip\_ref:

&#x20;       zip\_ref.extractall(extract\_path)

&#x20;   print("Dataset extracted successfully")

else:

&#x20;   print("Dataset zip not found.")

Training :

The model is trained using Custom YOLO-style loss function:

* Objectness Loss
  
* Bounding Box Loss
  
* Classification Loss

Evaluation Metrics :

* Accuracy
  
* Precision
  
* Recall
  
* F1 Score
  
* Confusion Matrix

Sample Output :

Bounding boxes are drawn on infected regions. Class labels are displayed on detected areas. Refer Notebook

How to Run ?

1\. Clone or download the repository.

2\. Open terminal/command prompt in the project folder.

3\.Upload the dataset

4\. Run the program: Maize\_Detection.ipynb

Future Improvements :

* Use full YOLOv9 architecture
  
* Deploy as web/mobile app
  
* Real-time detection using camera

Conclusion :

* This project demonstrates the application of deep learning techniques for automated maize leaf disease detection.
  
* A custom CNN model inspired by YOLO was developed to perform both classification and localization tasks effectively.
  
* The integration of a Triple Attention mechanism improved the model’s ability to focus on important features, leading to better performance in identifying disease patterns.
  
* The model was evaluated using standard metrics such as accuracy, precision, recall, and F1-score, providing a comprehensive understanding of its performance.
  
* Overall, this project highlights the potential of combining object detection frameworks with attention mechanisms for solving real-world agricultural problems. It can be further extended for real-time deployment and applied to other crop disease detection tasks.





