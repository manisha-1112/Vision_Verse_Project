# VisionVerse – Image Processing Project
# Electrical Engineers’ Association | IIT Kanpur

## Overview
- VisionVerse is an image processing project developed under the Electrical Engineers’ Association at IIT Kanpur.
- The objective was to explore and implement advanced computer vision techniques using OpenCV (CV2) in Python.
- The project involved applying multiple filtering, edge detection, and segmentation algorithms on real-world images to enhance, denoise, and extract visual features effectively.
- It provided practical experience with classical computer vision pipelines and core image processing fundamentals.

##  Objectives
- Learn and apply both linear and non-linear image filtering techniques for noise reduction and edge preservation.
- Implement advanced edge detection algorithms such as Laplacian, Canny, and Hough transforms.
- Perform image segmentation using unsupervised and automatic thresholding methods (K-Means Clustering and Otsu’s Binarization).
- Understand how classical computer vision methods process images before deep learning era architectures.

## Implementation Details
- All implementations were done using **Python (OpenCV, NumPy, Matplotlib)**.
- The workflow consisted of:
  1. Image Preprocessing (grayscale conversion, resizing, histogram equalization)
  2. Linear & Non-linear Filtering
  3. Edge Detection
  4. Segmentation and Region Extraction
  5. Visualization and Result Comparison

## Techniques Implemented
- **Gaussian Filter:** Applied `cv2.GaussianBlur(img, (5,5), 0)` to reduce high-frequency noise by smoothing pixel intensity.
- **Median Filter:** Used `cv2.medianBlur(img, 5)` to remove salt-and-pepper noise while preserving edges.
- **Bilateral Filter:** Implemented `cv2.bilateralFilter(img, 9, 75, 75)` for edge-preserving smoothing and fine noise removal.
- **High-Pass Filter:** Enhanced sharpness by subtracting blurred image from original using `cv2.addWeighted(img, 1.5, blur, -0.5, 0)`.

- **Laplacian Edge Detection:** Detected intensity gradients using `cv2.Laplacian(img, cv2.CV_64F)` after Gaussian blur for noise suppression.
- **Canny Edge Detection:** Generated thin and continuous edges with `cv2.Canny(img, 100, 200)` using gradient-based edge linking.
- **Hough Line Transform:** Detected geometric features with `cv2.HoughLinesP(edges, 1, np.pi/180, 80, minLineLength=50, maxLineGap=10)` and visualized using `cv2.line()`.

- **Otsu’s Segmentation:** Automatically calculated optimal threshold with `cv2.threshold(gray, 0, 255, cv2.THRESH_BINARY + cv2.THRESH_OTSU)` to separate foreground and background.
- **K-Means Clustering:** Clustered pixels by intensity/color using:
    Z = img.reshape((-1,3)).astype(np.float32)
    cv2.kmeans(Z, K=3, None, criteria, 10, cv2.KMEANS_RANDOM_CENTERS)
  Reconstructed segmented image using centroid colors.

##  Results
- Produced clean and visually enhanced images by applying noise filters and sharpening.
- Extracted clear and continuous object edges using Canny and Laplacian operators.
- Detected structural shapes (lines and circles) with the Hough Transform.
- Achieved meaningful region segmentation and color quantization using K-Means and Otsu thresholding.

##  Key Learnings
- Understood practical differences between linear and non-linear filters.
- Gained experience in balancing denoising and edge preservation for better visual clarity.
- Learned the mathematical and algorithmic flow of classical vision algorithms.
- Strengthened understanding of how traditional image processing complements modern CNN-based computer vision models.

##  Tools and Libraries
- Python 3.10+
- OpenCV (cv2)
- NumPy
- Matplotlib

##  Repository Structure
.
├── Assignment1.ipynb        # Basic filtering techniques
├── Assignment2.ipynb        # Edge detection implementations
├── Assignment3.ipynb        # Hough transforms and visualization
├── Assignment4.ipynb        # Image segmentation using K-Means & Otsu
├── Assignment5.ipynb        # Combined project pipeline
├── README.md                # Project documentation
└── sample_images/           # Example input and output images

##  Summary
- Developed a complete classical computer vision pipeline for denoising, edge detection, and segmentation.
- Implemented and compared multiple algorithms to understand trade-offs between accuracy, sharpness, and noise control.
- Enhanced hands-on understanding of OpenCV and traditional image analysis workflows.
