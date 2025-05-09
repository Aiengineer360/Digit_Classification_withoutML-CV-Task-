# Digit Classification using Heuristic Features

## Overview

This project tackles the Kaggle competition ["S-2025 No ML Digit Classification (Asgmt 1)"](https://www.kaggle.com/competitions/s-2025-no-ml-digit-classification-asgmt-1) which challenges participants to classify handwritten digits (0-9) from the MNIST dataset using only low-level heuristic features - no machine learning or computer vision libraries allowed.

## Problem Statement

The task is to:
- Process 28x28 grayscale handwritten digit images
- Classify digits (0-9) using only basic image processing techniques
- Forbidden techniques:
  - Machine learning algorithms
  - Computer vision libraries (like OpenCV)
- Allowed approaches:
  - Pixel counting
  - Histogram-based thresholding
  - Image cropping
  - Other heuristic feature extraction methods

## Solution Approach

### Key Steps:

1. **Image Preprocessing**
   - Applied binary thresholding (value=100) to convert grayscale images to black and white
   - Visual verification of thresholding effect

2. **Feature Extraction**
   - Calculated two fundamental statistical features for each image:
     - Mean pixel intensity
     - Variance of pixel intensities
   - These features capture basic image characteristics without using advanced techniques

3. **Classification Method**
   - Implemented a simple nearest neighbor classifier using Euclidean distance
   - For each test image, finds the most similar training image based on mean and variance
   - Uses the label of the closest training image as the prediction

4. **Validation**
   - Achieved 86.27% accuracy on the validation set
   - Demonstrated effectiveness of simple heuristic features

### Implementation Details

- **Thresholding**: Converted images to binary (black/white) to simplify feature extraction
- **Feature Calculation**: 
  - Mean: Average pixel intensity
  - Variance: Measure of pixel intensity variation
- **Distance Metric**: Euclidean distance between feature vectors
- **Prediction**: Nearest neighbor based on feature similarity

## File Structure

- `train.csv`: Training set with labels
- `validate.csv`: Validation set with labels
- `test.csv`: Test set for final predictions
- `submission.csv`: Generated predictions for test set
- `Digit_classification_by_mean_variance.ipynb`: Main notebook with implementation

## Results

The simple heuristic approach achieved:
- **86.27% accuracy** on the validation set
- Demonstrates that basic image statistics can effectively classify digits
- Performance could potentially be improved with additional heuristic features

## How to Use

1. Run the notebook `Digit_classification_by_mean_variance.ipynb`
2. The notebook will:
   - Load and preprocess the data
   - Calculate features
   - Make predictions
   - Generate submission file
3. Final predictions are saved in `submission.csv`

## Competition Note

This solution adheres strictly to competition rules by:
- Using only basic image processing
- Avoiding machine learning algorithms
- Not using any computer vision libraries
- Relying solely on heuristic feature extraction and simple distance-based classification
