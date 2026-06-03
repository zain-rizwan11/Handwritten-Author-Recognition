# Handwritten-Author-Recognition

A deep learning-based handwriting analysis system that identifies the author of a handwritten document from an input image. The model is trained on the CVL Handwriting Dataset and uses a Convolutional Neural Network (CNN) to learn writer-specific handwriting characteristics.

#📌 Overview

Handwriting styles vary significantly between individuals and can be used as a biometric trait for writer identification. This project implements a CNN-based classification model capable of distinguishing between multiple authors based solely on scanned handwriting samples.

The system accepts a handwritten image as input and predicts the most likely author from the set of authors used during training.

#🚀 Features
Multi-class handwritten author classification
Supports hundreds of unique writers
Automatic image preprocessing and normalization
CNN-based feature extraction and classification
Model persistence using Keras
Label encoder serialization for inference
Author prediction on unseen handwriting samples
Training performance visualization using accuracy and loss curves


#🛠️ Technologies Used
Python
TensorFlow / Keras
OpenCV
NumPy
Scikit-learn
Matplotlib
Pickle


#📂 Dataset

The project uses the CVL Handwriting Database, which contains handwritten text samples from multiple writers.

Dataset structure:

cvl-database-cropped/
├── 0001-1-cropped.tif
├── 0001-2-cropped.tif
├── 0002-1-cropped.tif
├── 0002-2-cropped.tif
└── ...

The author ID is extracted from the filename and used as the classification label.

#🏗️ Model Architecture

The model consists of:

4 Convolutional Layers
Batch Normalization
Max Pooling Layers
Dropout Regularization
Fully Connected Dense Layer
Softmax Output Layer

#🔄 Data Preprocessing

Before training, each image undergoes:

Grayscale conversion
Resizing to 224 × 224 pixels
Pixel normalization (0–1 range)
Label encoding
One-hot encoding of author labels

#📈 Evaluation

Training progress is monitored using:

Training Accuracy
Validation Accuracy
Training Loss
Validation Loss

Performance graphs are generated after training for visual analysis.

#💾 Saving the Model

The trained model is saved as:

model.save('cvl_author_classifier.keras')

The label encoder is also stored:

pickle.dump(label_encoder, open('label_encoder.pkl', 'wb'))
🔍 Predicting an Author

Example:

image_path = "sample_handwriting.tif"
predicted_author = predict_author(image_path)

print("Predicted Author:", predicted_author)

The system preprocesses the image, performs inference using the trained CNN, and returns the predicted author ID.

#📁 Project Structure
(NOTE: some files (i.e dataset, .keras file) may be missing due to its large size)
Handwritten-Author-Identification/
│
├── dataset/
│
├── train.py
├── predict.py
├── cvl_author_classifier.keras
├── label_encoder.pkl
│
├── results/
│   ├── accuracy_plot.png
│   └── loss_plot.png
│
└── README.md

#🎯 Applications

Writer Identification
Handwriting Biometrics
Forensic Document Analysis
Signature and Document Verification
Historical Manuscript Classification
Security and Authentication Systems

#📚 Future Improvements

Transfer Learning using ResNet or EfficientNet
Writer Verification (same/different author)
Handwritten Text Recognition Integration
Data Augmentation for improved generalization
Web-based deployment using Flask or FastAPI
Real-time author prediction interface

#👨‍💻 Author

Zain Rizwan

Computer Science Student @ FAST NUCES khi | AI & Machine Learning Enthusiast
