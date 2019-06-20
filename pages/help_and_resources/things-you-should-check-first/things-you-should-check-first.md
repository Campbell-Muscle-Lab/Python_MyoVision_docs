---
layout: page
title: Things you should check first
description: Web-based help for Python_MyoVision
---

Okay, something has gone wrong, and you're not quite sure what to do.

Here are some good steps.
  
+ Go back and run the demos
  + [Analyze-a-small-image](pages/analyze-a-small-image/analyze-a-small-image.html)
  + [Analyze-a-bigger-image](pages/analyze-a-bigger-image/analyze-a-bigger-image.html)
  
If those don't work, it's unlikely that anything else will work, so you need to fix this first. Good things to try here are:
  
+ Check if there are updates to Python and the packages
  + See the last update step on the [install Python page](../../how-to-install-myovision/install-python-using-anaconda/install-python-using-anaconda.html)
  + try the demos
  
+ Check if the Python_MyoVision program has been updated
  + open the Python_MyoVision repository in GitHub Desktop and check for updates
  + pull them to your desktop if there are
  + retry your demos
  
+ If that doesn't help, consider
  + deleting the entire Python_MyoVision folder
  + starting again with a [clean install](../../how-to-install-myovision/how-to-install-myovision.html)
    + this should fix the problem if your files got disorganized 
  
If the demos work, but you are running into other problems
  
+ Try a simpler version of your task
  + If you are trying to [analyze 30 image files](../../process-many-images-in-sequence/process-many-images-in-sequence.html)
    + analyze just 1 instead
    + once that's working, adjust your configuration file by adding more tasks
  + If you are trying to [analyze a very big image](../../analyze-a-bigger-image/analyze-a-bigger-image.html)
    + crop the image so that you just have 30 or 40 fibers
    + make sure you can analyze the small image first
  + Remember that Python_MyoVision [dumps image files as it goes](../../what-myovision-did/what-myovision-did.html)
    + use these to track the source of your problem
    + for example, if you can't see robust edges in the Frangi filter image, the program won't be able to perform a robust initial segmentation.
      + in this case, reading the documentation, will help you to see that changing the `percent_saturation` parameter in your configuration file might help.
  
If you're still stuck, check whether somebody has alerted us to the same problem

+ Go to the [Python_MyoVision respository](https://github.com/Campbell-Muscle-Lab/Python_MyoVision)
  + Click on the Issues tab

If so, we know about it, and are probably working on it.