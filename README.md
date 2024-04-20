# CyberPotholes - A Synthetic Labelled Pothole Depthmap Dataset
This study proposes a novel approach in the exploration of automatically generating synthetic datasets to aid in pothole defect management for road maintenance using smart technologies of the 4th Industrial Revolution. Here, pothole defect templates (features of interest) are created in designated bounding boxes before program runtime, preventing the need for complex bounding box fitting operations during runtime.

The dataset herein will be made public after the review process is finished.

## Primary Reference Data Collection
The 3D modelled pothole templates used to build the dataset are based on real world potholes to ground the process, avoiding complete abstraction. Therefore, RGB images taken of potholes were selected from the following primary and secondary sources:
1. A freely available Kaggle dataset, courtesy of [Sachin Patel](https://www.kaggle.com/datasets/sachinpatel21/pothole-image-dataset) (12 images).
2. Screenshots of frames from a video taken on USYD's Parramatta Road Footbridge (9 images).
3. Images taken from various locations in Western Sydney (3 images).
All primary data was collected using a Pixel 3a XL phone camera.
Hence, a total of 24 reference RGB images taken of pothole defects in the field were chosen in total.

![image](https://github.com/Kiran-KC-01/CyberPotholes/assets/167006792/8ced4733-0b45-4d5b-8b94-d3dfe2054b5d)

## Dataset Layout  
The dataset within this repository is organised into depthmap images and their corresponding labels split into training, validation, and testing subsets. As shown in the following folder structure:

```
└───dataset
    ├───images
    │   ├───test
    │   ├───train
    │   └───val
    └───labels
        ├───test
        ├───train
        └───val
```

This structure was chosen due to its convenience in being able to immediately be used in Machine Learning applications in a Google Colabs environment upon upload.

The dataset contains the following:
### 1. Depthmap images: 
Found in the subfolders under "images". PNG images depicting a birds eye depthmap scan taken of a simulated road with 1 to 6 pothole defects ("test" split more likely to have >4 defects). The grayscale shading of a defect depicts its distance from camera, with the intensity increasing in direct proportion to distance. Each defect can belong to the "medium" or "high" severity classes, defined as the perpendicular depth from the lowest point in the crater to the road surface according to the scale below:
![image](https://github.com/Kiran-KC-01/CyberPotholes/assets/167006792/26eaa5c6-3d7d-46e4-9b2b-b275b643d636)

The lower and upper parameters set limits to the possible depths that constitute a severity class.
![image](https://github.com/Kiran-KC-01/CyberPotholes/assets/167006792/40d703fa-5c39-4526-a578-3bb948578e01)


### 2. Label files: 
Found in the subfolders under "labels". These are .txt files containing the bounding box and class information of each pothole defect in their corresponding images on separate lines (1 line per defect). The class is represented by an integer value, with "1" and "0" representing "high" and "medium" severity pothole defects, respectively. Bounding box information consists of its center and dimensions. The information is arranged like so:
![image](https://github.com/Kiran-KC-01/CyberPotholes/assets/167006792/63e162f8-684e-48bf-b571-f1ee34e6778b)
All bounding box dimensions are given as percentages, "width" and "height" are bounding box width and height relative to the image width and height, respectively.

### 3. Geometric Information: 
Found in the file "potholeImageData.csv". This file contains selected metadata of each pothole defect across the entire dataset, identified by image index and folder subset. This metadata comprises pothole depth (m), estimated area (m<sup>2</sup>), estimated volume (m<sup>3</sup>), and its coordinates.

## Download Link
Due to its large filesize, please find below a google drive link to download the dataset as a .zip archive:

https://drive.google.com/file/d/1KWEgiOPMm2UVHl0dQiXFtN4Ud4AVCOn_/view?usp=drive_link

## Citation
If you use this dataset, please consider citing:

K.C. K., Balamurali M., (2023). Cyberpotholes Dataset. University of Sydney. Link to dataset.
