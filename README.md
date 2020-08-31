# Tesseract-OCR-in-google-colab.

# [IMAGE TO TEXT ]()

OCR from Image using Pytesseract .ipynb

Automatically generated by Colaboratory.

Original file is located at
    https://colab.research.google.com/drive/1qP2V83dcJSSdLm8stIpa3BWz9tt-6lN3

Made by [Govind Singh](https://github.com/adiboy17).

 Published August 31,2020

 --------------------------------------

In this tutorial you will learn how to extract text and numbers from a scanned image and convert a PDF document to PNG image using Python libraries such as [wand](https://pypi.org/project/Wand/), [pytesseract](https://pypi.org/project/pytesseract/), [cv2](https://pypi.org/project/opencv-python/), and [PIL](https://pypi.org/project/PIL/).

--------------------------------------
# Learning objectives
--------------------------------------

Upon completing this tutorial the reader will understand how to:

Build a document scanner (based on the prerequisite).
Enhance the document scanner to extract text and numbers.


# Prerequisites
------------------------------------
This is not beginner’s tutorial and requires knowledge of Python, Open CV & Natural Language Processing. This tutorial builds on a tutorial written by pyimagesearch contributor Adrian Rosebrock, it details How to Build a Kick-Ass Mobile Document Scanner in Just 5 Minutes. It is recommended to read through that tutorial to understand how to scan documents by detecting edges, finding contour and applying transformations.

#Estimated time
---------------------------------------
Completing this tutorial should take about 30 minutes.

#Steps

# 1.Install pytesseract and tesseract-OCR in google colab.


!sudo apt install tesseract-ocr

!pip install pytesseract

# 2.Import librarie

import pytesseract
import shutil
import os
import random
try:
 from PIL import Image
except ImportError:
 import Image

# 3. Upload image to the Colab We can manually upload the image by clicking on file- upload but we can also use the following code for uploading the image to colab.

from google.colab import files
uploaded = files.upload()

# 4. User image_to_string function of pytesseract library which takes an image as an argument and returns a string. We can either directly print it or store this string in one variable.

extractedInformation = pytesseract.image_to_string(Image.open('imgtext.png'))

print(extractedInformation)
