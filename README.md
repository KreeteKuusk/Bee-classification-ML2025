# Bee-detection-ML2025
This repository presents a machine learning pipeline for automatic classification of worker and drone bees from video frames. The workflow focuses on handling severe class imbalance, large-scale image preprocessing, and comparative evaluation of modern object detection architectures, with YOLOv10 selected for final experimentation.

# Repository Structure

The repository is organized into two main directories:

Model_selection
This directory contains comparative experiments with multiple object detection architectures, including YOLOv8, YOLOv10, YOLOv12, and RT-DETR. These experiments are designed to evaluate baseline performance and guide model choice under controlled preprocessing and augmentation settings.

project_beedetection
This directory contains the full detection pipeline built on YOLOv10. It includes high-resolution image preprocessing, systematic image tiling, dataset augmentation and balancing, manual dataset curation, and final model training and evaluation using a larger domain-specific dataset.

## Model Selection
To evaluate model suitability, four object detection architectures were trained and compared: YOLOv8, YOLOv10, YOLOv12, and RT-DETR. Experiments were conducted using a publicly available dataset from Roboflow. All images were resized to 640 × 640 pixels using stretching prior to training. Data augmentation generated two additional variants per image, including grayscale transformation applied to 15% of the samples and random noise affecting up to 1.96% of pixels. The dataset was split into training, validation, and test sets using a 40/5/5 ratio. The dataset exhibits a strong class imbalance, with a drone-to-worker bee ratio of 34.3:1, posing a significant challenge for detection performance.

## project_beedetection
Based on the model selection results, YOLOv10 was chosen for further development. To improve data diversity and scale, a more extensive dataset was sourced from the Mississippi State University GRI Publications database. This dataset consists of high-resolution imagery requiring additional preprocessing, including systematic image tiling and manual dataset curation. Multiple training runs were conducted on both imbalanced and balanced versions of the dataset to evaluate the effect of class balancing on model performance.

Dataset source:
https://scholarsjunction.msstate.edu/gri-publications/4/