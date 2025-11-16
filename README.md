FAKE IMAGE DETECTION USING MACHINE LEARNING

This repository contains the implementation of a machine learning system designed to detect forged or manipulated images, commonly known as deepfakes.The project was submitted in partial fulfillment of the requirements for the Bachelor of Technology in Computer Science and Engineering.

Project Overview:

Image forgery and deepfake generation have become significant threats in the digital era. With millions of manipulated images circulating daily, traditional human-based and forensic detection techniques are no longer adequate.

This project presents a robust solution that integrates:

Forensic image analysis
Error Level Analysis (ELA)
Deep Learning-based classification using Convolutional Neural Networks (CNNs)
The final model successfully distinguishes Real and Fake images using an 18-layer proprietary CNN architecture, achieving a testing accuracy of 98.77%.

Problem Statement:

Modern digital editing tools (Photoshop, GIMP, Deepfake generators, etc.) make image manipulation seamless and accessible. This leads to:

Fraudulent image-based evidence in legal scenarios
Misleading propaganda on social networks
Widespread cybercrime and misinformation
Difficulty for humans to identify fake vs real photos
Enormous scale: 80+ million images shared on Instagram daily
Traditional expert-driven forensic methods cannot scale to real-world volume and complexity.
Hence, an automated, AI-driven solution is essential.

Proposed Solution:

The detection system follows a multi-phase approach combining preprocessing, forensic techniques, and deep learning:

Image Analysis and Pre-processing
Metadata Analysis

Extract tags like “Photoshop”, “Adobe”, “GIMP”.
Used only as supporting evidence — metadata can be tampered with.

Error Level Analysis (ELA)
ELA highlights compression discrepancies to reveal manipulated regions.

Process:

Save image at 90–95% JPEG quality
Compare resaved image with original
Brighten difference to highlight inconsistent areas
Feed the ELA image into CNN
Manipulated areas degrade differently → useful for feature extraction.

Data Pre-processing:

Resizing (e.g., 224×224 for transfer learning, 256×256 for custom CNN)
Augmentation:
Rescale
Rotation, shear
Zoom
Width/height shift
Brightness adjustment
Horizontal & vertical flip
Improves data diversity and prevents overfitting.

Deep Learning Implementation:

Two types of models were used:
Proprietary Model
18-Layer CNN architecture
Components: Conv2D, Pooling, Batch Normalization, Dropout, Fully Connected layers
Testing Accuracy: 98.77%

Dataset Details:

A custom dataset of 13,000 images was prepared:
Real Images: “140k Real and Fake Faces” (Kaggle)
Fake Images: DeepFake-generated dataset using MTCNN
Train/Test Split: 75% training (10,000 images), 25% testing (3,000 images)

Execution Environment:

Frameworks: TensorFlow, Keras, Pillow, NumPy, Scikit-learn, Matplotlib
Tools: Jupyter Notebook, Google Colab, MATLAB
Hardware: GPU-supported setup
Key Hyperparameters:
Input: 256×256
Epochs: 20
Optimizer: Adam
Loss: Binary Crossentropy
Activation: Sigmoid

Conclusion:

This project demonstrates that deep learning models—especially custom-built CNNs—can effectively detect manipulated images, including deepfakes, with high accuracy.
The combination of Error Level Analysis and Deep CNN architectures provides a powerful method for real-world fake image detection.

This system can be extended to:

Social media monitoring
Cybercrime investigation
Authenticity verification systems
Legal forensic analysis
