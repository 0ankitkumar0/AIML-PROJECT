# AIML-PROJECT
# Pedestrian Detection Using Histograms of Oriented Gradients (HOG)

## Overview
This project implements a pedestrian detection system using the Histogram of Oriented Gradients (HOG) method combined with a Support Vector Machine (SVM) for classification. The approach is rooted in computer vision and is highly effective for human detection tasks.

![](/readme_visuals/detected_pedestrians.png)

## Project Description
Pedestrian detection is a fundamental aspect of computer vision. This project focuses on demonstrating the efficiency and implementation of the Histogram of Oriented Gradients (HOG) technique for detecting pedestrians, particularly those who are completely visible and standing up. 

### Histogram of Oriented Gradients (HOG)

The HOG descriptor is grounded in the understanding of image gradients and their orientations. It's designed to capture the local object appearance and shape within an image by the distribution of intensity gradients or edge directions.

1. **Gradient Calculation**: The key to HOG is the use of gradients. The gradient of an image at each pixel represents the direction of the fastest increase in intensity. For a pixel at (x, y), the gradient components $G_x$ and $G_y$ are given by:

   $$G_x = \frac{\partial I}{\partial x}, \quad G_y = \frac{\partial I}{\partial y}$$

   where $I$ represents the image intensity. Typically, these partial derivatives are computed using the Sobel operator, which uses convolution with specific kernels.

2. **Orientation Binning**: After computing the gradients, the next step is to create histograms of gradient orientations for localized portions of the image. This involves dividing the image into small connected regions (cells) and accumulating a histogram of gradient directions or edge orientations for the pixels within each cell.

3. **Histogram Computation**: The histograms are computed over the cells of the image. For each cell, the gradient orientations are discretized into a number of predefined bins. The contribution of each pixel to the histogram is weighted by its gradient magnitude.

4. **Block Normalization**: The histograms are normalized over larger regions (blocks) to improve accuracy. This normalization is crucial as it renders the descriptor invariant to changes in illumination or shadowing.

### Support Vector Machine (SVM)

SVM operates on the principle of finding a hyperplane that best divides a dataset into classes.

1. **Optimal Hyperplane**: In the context of SVM, a hyperplane is a line that linearly separates the classes. The optimal hyperplane is the one that maximizes the margin between the classes. The margin is defined as the distance between the hyperplane and the nearest data point from either class.

2. **Mathematical Formulation**: The decision function of a linear SVM is given by:

   $$f(x) = \text{sign}(w^T x + b)$$

   where $w$ is the normal to the hyperplane, $x$ is the input feature vector, $b$ is the bias, and $\text{sign}$ is the sign function.

3. **Kernel Trick**: For non-linearly separable data, SVM employs the kernel trick. A kernel function transforms the input data into a higher-dimensional space where a linear separator is sufficient. Common kernels include polynomial and radial basis function (RBF).

4. **Soft Margin and Regularization**: To handle non-separable cases and to prevent overfitting, SVM introduces a slack variable $\xi$ and a regularization parameter $C$ in its optimization problem:

   $$\min_{w, b, \xi} \frac{1}{2} \|w\|^2 + C \sum_{i=1}^{n} \xi_i$$

   subject to the constraints that each data point $x_i$ is classified correctly, within a margin error $\xi_i$.

This advanced mathematical background provides a deeper understanding of the principles and algorithms underlying the HOG descriptor and SVM classifier. The mathematical rigor and complexity are suitable for an audience with a strong background in machine learning and computer vision.


## Technological Overview
This project utilizes several key technologies and libraries, which are integral to its implementation:

1. **Python**: The primary programming language used for implementing the project.
2. **OpenCV (Open Source Computer Vision Library)**: A powerful library used for various image processing and computer vision tasks, including the implementation of HOG.
3. **NumPy**: A fundamental package for scientific computing with Python, used for efficient operations on multi-dimensional arrays.
4. **Matplotlib**: A plotting library for Python and its numerical mathematics extension NumPy. It provides an object-oriented API for embedding plots into applications.

## Project Workflow
The workflow of the project is structured as follows:

1. **Initial Setup**: Importing necessary libraries like OpenCV, NumPy, and Matplotlib.
2. **Data Visualization**: Utilizing Matplotlib to plot histograms and visualize data, aiding in understanding the distribution of features.
3. **Image Processing for HOG**: Preparing images and using the Sobel operator to calculate gradients. This is essential for understanding the orientation and magnitude of image gradients.
4. **HOG Descriptor Initialization**: Setting up the HOG descriptor, which is crucial for extracting features from images.
5. **SVM Detector Setup**: Initializing the SVM detector with the HOG descriptor for pedestrian detection.
6. **Video Processing**: Loading a video stream and processing it frame by frame to detect pedestrians.
7. **Pedestrian Detection**: Applying the HOG descriptor and SVM to each frame for detecting pedestrians.
8. **Result Visualization**: Drawing bounding boxes around detected pedestrians and displaying the results using Matplotlib.
9. **Video Analysis Conclusion**: Releasing video resources post-analysis.

## Code Overview
The codebase is structured into several key sections, each fulfilling a specific role in the pedestrian detection pipeline:

- **Library Imports**: Importing essential libraries (OpenCV, NumPy, Matplotlib) necessary for the project.
- **Data Visualization**: Utilizing Matplotlib for plotting histograms and visualizing data, which is crucial in understanding feature distributions.
- **Feature Calculation and HOG Preparation**: Implementing gradient calculations using the Sobel operator and preparing for HOG feature extraction.
- **HOG Descriptor and SVM Detector**: Initializing the HOG descriptor for feature extraction and the SVM detector for pedestrian classification.
- **Video Frame Processing**: Loading and processing video frames to apply pedestrian detection.
- **Detection and Result Visualization**: Applying HOG and SVM to detect pedestrians in video frames and visualizing the results with bounding boxes.

## Usage
To run this project, follow these steps:

1. Clone the repository to your local machine.
2. Ensure that Python and all the required libraries (OpenCV, NumPy, Matplotlib) are installed.
3. Navigate to the project directory and open the Jupyter Notebook (`Pedestrian_Detection_Using_HOG.ipynb`).
4. Run the Jupyter Notebook cells in sequence to execute the pedestrian detection process.
