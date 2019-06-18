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

Start small, and take baby steps.

The key point is to test every step of your workflow with small images. These are easier to troubleshoot and take less to time to process. Only transition to large data files once you are confident that your test examples are working smoothly and robustly.

First

+ Make sure you've worked through the introductory tutorials

Once you've done that

+ Take one of your new images, let's assume it's called real_data_1.png

+ Crop data_1.png, so that it contains tens of fibers - and save it with a simple name, such as test_1.png

+ Now try to segment test_1.png into blobs

  + Use [this example](../creating-a-new-classifier/segment-a-test-image-into-blobs/segment-a-test-image-into-blobs.html) if you need help
  
  + If you didn't get adquate blobs
    + try adjusting the `saturation_percent` parameter in your configuration file and repeat the initial segmentation
    
  + Once you can identify blobs in test_1.png, repeat the process with:
    + test_2.png, a bigger cropped version of real_data_1.png that contains hundreds of fibers
    
  + If that still looks okay, try to segment real_data_1.png into blobs
    + again, adjust `saturation_percent` if you're not happy with any of these steps
    
+ Once you've segmented real_data_1.png adequately
  + use it to [make a new classifier](../creating-a-new-classifier/creating-a-new-classifier.html)
  
+ Then, as illustrated in [analyze-a-larger-image](../analyze-a-larger-image/analyze-a-larger_image.html), user your new classifier to analyze:
  + test_1.png
  + test_2.png
  + real_data_1.png in sequence
  
+ If you're not happy with the fiber refinement step in these analyses, try adjusting `sigma` in `<refine_fibers_parameters>`
  + low sigma (e.g. 1) will allow the fiber outlines to grow close to the cell boundaries
  + higher sigmas (e.g. 5) will keep the fiber outlines further from the boundaries, but may produce fewer 'connected fibers'

+ If that works, set up the [batch process](../process-many-images-in-sequence/process-many-images-in-sequence.html) and cross your fingers!
