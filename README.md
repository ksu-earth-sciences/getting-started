# Getting Started

- First Look inside of the Setup_Tutorial folder to find the Setup files. Those files will go over in detail on what needs installed and how to install them.
- If you wish, you can go through the tutorial to get the hang of it

## Overview

### Table of contents
#### Alignment
- Opening Images
- Check for existing warp matricies
- Unwarp and Align (OpenCV method for RedEdge3/M/MX/Dual and original Altum)
- Crop Aligned Images and Create aligned capture stack
- Alignment and pan-sharpning for RedEdge-P and Altum-PT
- Save warp matrices
- Multispectral band histogram
- Visualize Aligned Images
- Image Enhancement
- Stack Export
- NDVI Computation
- Plant Classification
- NDRE Computation
- Thermal Imagery
- Red vs NIR Reflectance
- Print warp_matricies for usage elsewhere, such as Batch Processing
#### Alignment 10 Band
- *Same as Alignment, but instead explaining with 10 Band*

#### Alignment Big Relatives
- Passive Image Alignment
    - Opening Images
- Alignment - Big Relatives
- Visualize Aligned Images
- Image Enhancement
- Rendered Image output
- Stack Export
- Notes on Alignment and Stack Usage
- NDVI Computation
- Plant Classification
- NDRE Computation
- Thermal Imagery
#### Batch Processing
- Example
- Load Images into ImageSet
- Capture map
- Define which warp mathod to use
- Align images and save each captire to a layered TIFF file
- Write EXIF data to stacks
#### Batch Processing 10 Band
- Example 
- Load Images into ImageSet
- Define which warp method to use
- Align images and save each capture to a layered tiff file
- Extract MetaData from Captures list and save to log.csv
- Use Exiftool from the command line to write metadata to images
#### Captures
- More Capture visualization functions
#### Images
- Image Histogram
- Captures
#### ImageSets
- Examples
- Load a directory of images into an ImageSet
- Import Capture data into Pandas DataFrame
- Mapping capture locations using MapboxGL
- Plotting capture metadata
- Separating ground and flight images
- Automatically extracting radiances of panel images
- Plotting DLS Irradiances
#### Panels
- Examples

### What You will need installed
- Look into the file named "micasense_conda_env.yml". This file lists all of the dependencies you will need for the environment to work 
- Many are installed on Brew (MAC) or through windows
- You will have to install python and pythons package manager pip
- Other questions may be answered 
  
## This code should work in jupiter notebook when you are done
```python
import cv2  # openCV
import exiftool
import os, glob
import numpy as np
import pyzbar.pyzbar as pyzbar
import matplotlib.pyplot as plt
import mapboxgl

print()
print("Successfully imported all required libraries.")
print()

if os.name == 'nt':
    if os.environ.get('exiftoolpath') is None:
        print("Set the 'exiftoolpath' environment variable as described above")
    else:
        if not os.path.isfile(os.environ.get('exiftoolpath')):
            print("The provided exiftool path isn't a file, check the settings")

try:
    with exiftool.ExifTool(os.environ.get('exiftoolpath')) as exift:
        print('Successfully executed exiftool.')
except Exception as e:
    print("Exiftool isn't working. Double check that you've followed the instructions above.")
    print("The exception text below may help to find the source of the problem:")
    print()
    print(e)
```


