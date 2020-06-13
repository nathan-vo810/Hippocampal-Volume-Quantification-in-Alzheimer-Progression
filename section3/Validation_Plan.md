# Validation Plan

## 1. General Information

### Intended Use: 

Assisting radiologist in measuring the volume of Hippocampal area in patient's brain.

### Indications for Use:

It is well used for both male and female patient. It is used for MRI images. 

### Device Limitations:

Require high-power processing GPU card to run the algorithm.

## 2. Dataset

### Training Data
The data we are using is the "Hippocampus" dataset from the [Medical Decathlon competition](http://medicaldecathlon.com/#tasks). This dataset is stored as a collection of NIFTI files, with one file per volume, and one file per corresponding segmentation mask. The original images here are T2 MRI scans of the full brain. In this dataset we are using cropped volumes where only the region around the hippocampus has been cut out.

### Labeling Training Data
The images in the training are labeled by the following convention:
	- The Anterior part of the Hippocampus is labeled as 1
	- The Posterior part of the Hippocampus is labeled as 2
	- All other part (the background) is labeled as 0

## 3. Algorithm Performance

### Metrics
Two metrics are used to measured the performance of the algorithm:
	- Dice Similarity Coefficient
	- Jaccard Similarity Coefficient

### Performance
The algorithm can achieve a Dice Similarity Coefficient of around 0.90 and Jaccard Similarity Coefficient of around 0.82

### Real-world Performance 
The real-world ground truth can be established by acquiring silver standard of radiologist reading.

## 4. Real-world Inference
- The algorithm will perform well on T2 MRI scans of the full brain. 
- The algorithm cannot perform on CT scans or any other format.
- The algorithm cannot be used to measure volume of any other body parts except the hippocampus of the brain.  