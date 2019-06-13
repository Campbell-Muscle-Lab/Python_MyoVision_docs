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
  
If those don't work, it's unlikely that anything else will work. You could ask somebody who knows about computers to help you, and if that doesn't work, consider coping your work to a new directory (in case you need to come back to), delete the MyoVision code, and starting again with a [clean install](../../how-to-install-myovision/how-to-install-myovision.html).

+ Try a simpler version of your task
  + If you are trying to [analyze 30 image files](../../process-many-images-in-sequence/process-many-images-in-sequence.html)
    + analyze just 1 instead
    + once that's working, adjust your configuration file by adding more tasks
  + If you are trying to analyze a very big image
    + crop the image so that you just have 30 or 40 fibers
    + make sure you can analyze the small image first

If you're still stuck, check whether somebody has alerted us to the same problem

+ Go to the [Python_MyoVision respository](https://github.com/Campbell-Muscle-Lab/Python-MyoVision)
  + Click on the Issues tab

If so, we know about it, and are probably working on it.