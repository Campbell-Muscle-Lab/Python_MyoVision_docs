---
layout: page
title: Train the classifier
description: Web-based help for Python_MyoVision
---


### Train the classifier

1. Open a command prompt and change the directory to that containing your Python code
   + It's probably  
`c:\users\your_username_here\GitHub\Python_Myovision\Python_code`
   + If you're stuck, check this [introductory example](../../analyze-a-small-image/analyze-a-small-image.html)

1. Type  
`python py_vision.py train_classifier "..\demos\example_C\configuration_data\train_classifier.xml"`  
and press enter

1. Within a few seconds, you should see a status update in the command window

1. Training the classifier may take a few minutes, but if all goes well, you should see a final status update similar to  
`Saving classifier model to ..\demos\example_C\classification_model\classification_model.svc`

1. That's basically it. You have just created a new classifier system and saved it as a file called `classification_model.svc` in `..\demos\example_C\classification_model`
