## Face Swapping Project

**Table of Contents**

* [Introduction](#introduction)
* [Requirements](#requirements)
* [Installation](#installation)
* [Process Explanation](#process-explanation)
    * [Extract Face Landmarks](#extract-face-landmarks)
    * [Delaunay Triangulation](#delaunay-triangulation)
    * [Triangle Warping](#triangle-warping)
    * [Seamless Cloning](#seamless-cloning)
* [Usage ](#usage)
* [Results ](#results)

* [License](#license)


## Introduction

This project implements a face swapping algorithm that seamlessly overlays a source face onto a target face. The process involves several key steps:

* **Face landmark detection:** Identifying key points on both faces (eyes, nose, mouth) to guide alignment and blending.
* **Delaunay triangulation:** Creating a mesh of triangles across the face using these landmarks, ensuring smooth transitions during warping.
* **Triangle warping:** Adjusting each triangle from the source face to perfectly match its corresponding triangle on the target face.
* **Seamless cloning:** Blending the warped triangles onto the target image, removing any visible seams for a natural-looking result.

## Requirements

* Python 3.x
* OpenCV
* Numpy
* Dlib or Mediapipe for face landmark detection (choose one)

## Process Explanation  

### 1. Extract Face Landmarks
The first step in the process is to extract facial landmarks from both the source and target images. These landmarks are specific points on the face (like the corners of the eyes, nose, and mouth) that are used to align and blend the faces.

### 2. Delaunay Triangulation
After extracting the landmarks, the next step is to perform Delaunay triangulation on these points. This technique divides the face into a set of triangles, ensuring that no point is inside the circumcircle of any triangle. This step is crucial because it allows us to map small triangular regions from the source face to the target face, making the transition smooth.

### 3. Triangle Warping
Once the triangles are defined, each triangle from the source image is warped to its corresponding triangle in the target image. This warping process involves affine transformations, ensuring that the shape of each triangle matches exactly.

### 4. Seamless Cloning
After warping the triangles, they are blended onto the target image using seamless cloning. This technique allows for smooth transitions between the swapped face and the target image, removing any visible seams. This final step is crucial for making the face swap look realistic.

## Usage
To use this project, you need to provide the source and target images. The process will involve extracting landmarks, performing triangulation, warping the triangles, and finally, blending them onto the target face.

## Results
The results are realistic face-swapped images where the source face seamlessly integrates with the target image. Here are some examples:

Before:


After:

## Installation

1. Clone the repository:

```bash
git clone [https://github.com/yourusername/faceswap_project.git](https://github.com/yourusername/faceswap_project.git)
