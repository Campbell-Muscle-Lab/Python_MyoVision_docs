---
layout: page
title: Creating a new classifier
description: Web-based help for Python_MyoVision
---

### Overview

Each time you change something that impacts your raw data images, or how MyoVision will analyze the cell boundaries, you need to create a new classifier. Examples of reasons to do this include:
+ changing a setting on the microscope
+ using a different stain
+ working with a different type of muscle (for example, plantaris verus soleus, or human versus mouse)
+ changing `percent_saturation` in `<image_to_label_parameters>` in a configuration file

Creating the classifier, involves three steps:
+ Segment a test image into test blobs
+ Manually classify each blob as one of:
  + a plausible fiber (code 1)
  + potentially connected fibers (code 2)
  + something else, for example, interstitial space (code 3)
+ Training the classifier

This page leads you through an example workflow.

### Workflow

+ [Segment a test image into test blobs](segment-a-test-image-into-test-blobs/segment-a-test-image-into-test-blobs.html)
+ [Manually classify blobs](manually-classify-blobs/manually-classify-blobs.html)
+ [Train the classifier](train-the-classifier/train-the-classifier.html)

Once you have created a new classifier, it's a good idea to test it.

+ [Testing your new classifier](test-your-new-classifier/test-your-new-classifier.html)
