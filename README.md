# Gas Plume Detection - ACE Cleaning Pipeline

**Abigail Basener**  
**12/8/2025**

## Overview
This project takes in 3 images (an RGB view, an ACE detection map output, and a ground truth) and performs cleaning on the detection map. Then it performs detection on the cleaned map to find blobs in the image.

This is meant to be used with satellite images that have had ACE detection done on them for methane, with the ideal outcome of the code filtering out unwanted detections and leaving only detections coming from a leak.

## Files
- **main.ipynb** - Production pipeline *(recommended starting point)*
- **pipeline.ipynb** - Development version with step-by-step breakdown and intermediate visualizations
- **image_analysis.ipynb** - Experimental/historical testing *(uses glycans dataset as well)*

### Datasets
- **CleanImages** - Holds the 3 images (the RGB, ACE map, ground truth) for processing. There are 7 different sets to test different types of detection maps.
- **Data** - Not in use
- **GLYCAN** - Old data for possible glycan analysis before the final choice was made *(Only used for image_analysis.ipynb)*

## Settings
In the main file, all the parameters for the methods are listed in one block to allow easy testing of different values. The final output settings are at the run function, such as the image number or turning on/off the cloud and noise cleaning.

In the pipeline file, there are the same parameters, but they are with the block doing the step, not all at the top.

## Dependencies
Will need: numpy, matplotlib, pillow, scipy, scikit-image, opencv-python

Install with:
```bash
pip install numpy matplotlib pillow scipy scikit-image opencv-python
