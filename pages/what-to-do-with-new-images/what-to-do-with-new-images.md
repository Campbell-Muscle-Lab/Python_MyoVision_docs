---
layout: page
title: What to do with new images
description: Web-based help for Python_MyoVision
---

### Overview

Congratulations - you've just spent months running an experiment, harvesting muscles, sectioning your samples, staining the slides, and collecting your images. You have 150 images, and each is 100 MB.

You might be tempted to load everything into a configuration file, press go, and walk away.

In practice, that's unlikely to work. Even if it does, there's a high probability that you will end up with results that don't make sense, or don't match what you expected.

### A better approach

Start small, and take baby steps

+ Make sure you've worked through the introductory tutorials

Once you've done that

+ Take one of your new images

+ Crop it, so that it contains tens of fibers - and save it with a simple name, such as test_1.png

+ Now try to segment your simple image into blobs
  + Use [this example](../creating-a-new-classifier/segment-a-test-image-into-blobs/segment-a-test-image-into-blobs.html) if you need help
  
  + If your initial segmentation looks okay
    + [Make a new classifier](../creating-a-new-classifier/creating-a-new-classifier.html)
    + then use that classifer to analyze the image, as in [this example](../analyze-a-small-image/analyze-a-small-image.html)
  
  + If your initial segmentation looks dodgy, try:
    + adjusting the `saturation_percent` parameter in your configuration file
    + once that looks better, try the classification steps outlined above
    
  + If the segmentation found fibers, but you're not happy with the refinement step
    + try adjusting `sigma` in `<refine_fibers_parameters>`
      + low sigma (e.g. 1) will allow the fiber outlines to grow close to the cell boundaries
      + higher sigmas (e.g. 5) will keep the fiber outlines further from the boundaries, but may produce fewer 'connected fibers'
  
  + don't move on, until you are happy with the analsis of the small image
  
+ Now repeat the process with a bigger version of your test image (perhaps one containing a few hundred fibers)
  + Don't move on, until you are confident that works
  
+ Now try it with a full-scale image

+ If that works, set up the [batch process](../process-many-images-in-sequence/process-many-images-in-sequence.html) and cross your fingers!




Okay, something has gone wrong, you've worked through [the trouble-shooting tips](../things-you-should-check-first/things-you-should-check-first.html), and you've come to the conclusion that there is a problem with the code.

+ Go to the [Python_MyoVision respository](https://github.com/Campbell-Muscle-Lab/Python-MyoVision)

+ Click on the Issues tab

+ Click on the Green "New issue" button
