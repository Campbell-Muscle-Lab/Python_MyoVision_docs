---
layout: page
title: Segment a test image into test blobs
description: Web-based help for Python_MyoVision
---

### Segment a test image into test blobs

1. Open a command prompt and change the directory to that containing your Python code
   + It's probably  
`c:\users\your_username_here\GitHub\Python_Myovision\Python_code
   + If you're stuck, check this [introductory example](../../analyze-a-small-image/analyze-a-small-image.html)

1. Type  
`python py_vision.py find_blobs "..\demos\example_C\configuration_data\configuration_data.xml"`  
and press enter

1. Within a few seconds, you should see lots of status updates in the command window

1. Once the program has finished, look in `..\demos\example_C\results`. You should see:
   + annotated_overlay.png - an image file showing labeled blobs
   + blob_metrics.xlsx - an Excel file showing metrics for each labeled blob
   + a folder called blobs, which contains >800 individual images
